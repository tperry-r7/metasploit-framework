---
title: HTTP and HTTPS communications in Meterpreter and Metasploit Stagers
version: [] //Metasploit versions this applies to.
---

This article will go over the differences between WinInet and WinHTTP in Windows and the issues that can arise with Meterpreter and Metasploit.

## Windows HTTP APIs

The Windows API comes with two ways to talk via HTTP/S; [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) and [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx). The APIs are consumed similarly; many of the functions in each have the same interface.

### WinInet API

The [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) API is designed for use in desktop applications. It provides all the features required by applications to use HTTP/S while delegating much of the responsibility of handling implementation detail to the underlying API and OS. The [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) API can result in some user interface elements appearing if not handled correctly.

[WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) comes with limitations, one of which is that it's close to impossible to do any custom validation, parsing, or handling of SSL communications. One of the needs of Metasploit users is to be able to enable a [Paranoid Mode](https://github.com/rapid7/metasploit-framework/wiki/Meterpreter-Paranoid-Mode) that forces Meterpreter to only talk with the appropriate endpoint. The goal of [Paranoid Mode](https://github.com/rapid7/metasploit-framework/wiki/Meterpreter-Paranoid-Mode) is to prevent shells from being hijacked by unauthorized users. One of the ways to prevent shells from being hijacked is the verification of the SHA1 hash of the SSL certificate that Meterpreter reads from the server. If this hash doesn't match the one that Meterpreter is configured with, Meterpreter will shut down. [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) doesn't make this process possible without a lot of custom work.

### WinHTTP API

For applications such as this, [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) is the preferred option by Microsoft. This API is designed to work under a service and provides a greater number of ways to interact with communications made over HTTP/S. With this API, it was trivial to implement the SHA1 hash verification and force Meterpreter to shut down when a MITM is detected.

For a full comparison of the feature differences, please see [WinINet vs. WinHTTP](https://docs.microsoft.com/en-us/windows/win32/wininet/wininet-vs-winhttp?redirectedfrom=MSDN) in Microsoft documentation.
## Meterpreter's implementation

Meterpreter now makes use of [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) by default so that the new features are accommodated, but unfortunately, this doesn't come for free. The [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) API does not make any use of the current user's Internet Explorer configuration settings, where the [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) API does. This means that if the current user has a proxy configured, extra code needs to be added to make use of the current Internet Explorer settings in [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx). Meterpreter has been modified to do this; however, there is still one limitation that is in place.

As indicated in a [blog post on MSDN](http://blogs.msdn.com/b/httpcontext/archive/2012/02/21/changes-in-winhttp-on-windows-7-and-onwards-wrto-http-1-0.aspx):

> WinHTTP strictly requires HTTP/1.1 compliance for keeping the
> connection alive and HTTP Keep-Alives are not supported in HTTP/1.0
> protocol. HTTP Keep-Alive feature was introduced in the HTTP/1.1
> protocol as per RFC 2616. The server or the proxy which expects the
> keep-alive should also implement the protocol correctly. WinHTTP on
> Windows 7, Windows 2008 R2 are strict in terms of security wrto
> protocol compliance. The ideal solution is to change the server/proxy
> to use the right protocol and be RFC compliant.

What this means is that from Windows 7 and onwards, the underlying [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) implementation requires proper HTTP/1.1 support from any proxies used. If a proxy uses HTTP/1.0, such as Squid 2.7, and requires Keep-Alive support, such as NTLM authentication, then [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) will refuse to talk to it. Instead of downgrading, it will expect a purely RFC-compliant implementation and instead will return a 407 error to the client. For Meterpreter to work, [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) can't be used.

[Extra work](https://github.com/rapid7/metasploit-payloads/pull/5) has been done to force Meterpreter to fall back to [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) when this happens. Given that [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) doesn't do certificate hash verification, this means that the user of Meterpreter loses the ability to use paranoid mode. Meterpreter does not fallback to [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) if paranoid mode was enabled, as the intention of the user is clearly to avoid MITM.

Meterpreter will use [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) where it can. If it can't, it will fall back to [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) unless paranoid mode is enabled.

## Metasploit HTTP and HTTPS Stagers

Metasploit users have long since known about the reverse_http and reverse_https stagers, and have made good use of them over time. What many don't know is that these stagers use the [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) API, which means that they don't get SSL certificate validation (so no paranoid mode).

New stagers were required to provide support for paranoid mode inside the stager. Without the new stagers, downloading Meterpreter was prevented in MITM attacks(Man In The Middle).

`reverse_winhttp` and `reverse_winhttps` are implementations of stagers that make use of [WinHTTP.](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) reverse_winhttps provides support for paranoid mode. They both come with the same implicit limitation as Meterpreter itself in that they may not be able to provide proxy support thanks to the strict RFC compliance described in the previous section. The big difference here is that the stager does not have a fallback implementation like Meterpreter does since it would make the stager way too big. If an older proxy is in place that doesn't confirm to HTTP/1.1, the stager will fail.

## Combining stagers with Meterpreter

It's important to note that the implementations of communications inside the stagers are completely separate from those inside Meterpreter. If you use windows/meterpreter/reverse_https, then the stager will use [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx), and Meterpreter will use [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx). It isn't possible to "hand over" communications from the stager to Meterpreter in this case, and it wouldn't make sense anyway because HTTP/S is stateless. This is the most common set up because many people don't realize that the reverse_winhttp/s payloads exist!

Before the [WinInet fallback](https://github.com/rapid7/metasploit-payloads/pull/5) work, those people hitting the HTTP/1.0 proxy issue would find themselves with the following scenario:

1.  They would exploit a Windows 7 (or later) target in some way, whether it be via a browser exploit, or through a social engineering attack.
2.  The payload that was executed was meterpreter/reverse_https, and so the initial connection would come via [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx).
3.  [WinInet](https://msdn.microsoft.com/en-us/library/windows/desktop/aa383630%28v=vs.85%29.aspx) would successfully use the current user's proxy configuration and the initial connection back to Metasploit would be successful.
4.  The stager would download the second stage (metsrv), and reflectively load it so that Meterpreter could take over.
5.  Meterpreter would attempt to connect again to Metasploit, this time using [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx).
6.  The proxy would return HTTP/1.0 responses, resulting in [WinHTTP](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382925%28v=vs.85%29.aspx) refusing to function.
7.  The Meterpreter session would be considered "dead" by Metasploit as a result of the lack of successful communications after staging.

You can see examples of these issues in #5462 and #5626. If you see similar issues, it's because your current Meterpreter binaries don't have the fallback option.

Original Submission by [OJ](https://github.com/OJ) / [@TheColonial](https://twitter.com/TheColonial)

Last updated on June 9, 2020 by @tperry-r7