% Installing Metasploit

There are several ways to install Metasploit Framework.

## Metasploit Installer

The installer is the official way to install Metasploit, which can be downloaded from [metasploit.com](http://metasploit.com). This is the easiest way to set up Metasploit, but not recommended for open source development purposes.

Installers for Windows and Linux can be found on the [Metasploit Framework wiki](https://GitHub.com/rapid7/metasploit-framework/wiki/Nightly-Installers).

To finish setup use our official setup guide, [Setting up a Metasploit developer environment.](setting-up-metasploit-dev-enviroment.html)

## MSF-Installer from Omnibus

Omnibus is Metasploit's solution to having an easy to install Metasploit Framework without the painful manual environment setup process. Its mostly for end-users, not quite suitable for development right out of the box.

The GitHub repository for Omnibus is:

[https://GitHub.com/rapid7/metasploit-omnibus](https://GitHub.com/rapid7/metasploit-omnibus)

## Vulnerable target

If you want a vulnerable target while using Metasploit, you can use:

* [Metasploitable3](https://github.com/rapid7/metasploitable3) - The newest version of Metasploitable. It's recommended to use Metasploitable3.
* [Metasploitabe2](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/) - A Linux box with over 100 vulnerabilities. Some can be easily exploited by Metasploit. Some not so straight forward.

## Kali

Kali is a Debian-based Linux distro for penetration testing, a remake of Backtrack Linux. Metasploit is packaged in Kali, and it's the most convenient way for community users to start using the product without the hassle of going through the installation themselves.

Updates don't come directly from Rapid7, instead, the update cycles are managed by Offensive Security.

Kali can be downloaded at:
[https://www.kali.org/downloads/](https://www.kali.org/downloads/)

