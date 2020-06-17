% Payload Debugging
% Metasploit Versions 4,5

When debugging Metasploit Framework payloads, it's important to identify on
which side the issue is that needs to be examined. It's possible and common to
debug both sides (the framework side and the target side )but the process to
configure each is unique.

## Terminology

**Framework Side** -- What is referred to as the "framework side" within this
article is the host on which the Metasploit Framework is running. The code on
this side is generally Ruby and debugging usually involves inspecting the
various modules and libraries provided by Metasploit.

**Target Side** -- What is referred to as the "target side" within this article
is the host on which the payload is being executed. In the context of an
exploit module, this would be the `RHOST`. Debugging the target side is very
dependent on which payload is being inspected. For example, the Windows native
Meterpreter requires a custom build process and more complex errors may require
a native debugger to be used such as WinDBG.

## General Notes

If a payload fails to execute, first try to identify if it is an issue specific
to the payload, or the way in which it is executed. If (for example) both
Meterpreter and Shell payloads are failing, the issue could be with the exploit
module that delivered them.

If a Meterpreter session is not being fully established, it's possibly due to an
issue with the stager component rather than Meterpreter itself. To test this,
try to switch to a different staged payload such as a shell or VNC
configuration.

## Framework Side

### General Meterpreter API Architecture

When a post module invokes a method that leverages the running Meterpreter
instance, it uses a method defined in Ruby within the
`lib/rex/post/meterpreter/extensions` directory. This function typically
processes the arguments and turns them into one or more TLVs to be dispatched by
the core Meterpreter code. These TLVs are then placed within a
transport-specific protocol and transmitted to Meterpreter.

## Target Side (`windows/meterpreter`)

Debugging the Windows native Meterpreter requires building from source with a
specific set of options. The [README.md][1] file outlines these steps but to
summarize, it involves using Visual Studio, opening the project and selecting
the debug configuration.

With this configuration in place, various information will be logged by the
Meterpreter process using the Windows API function [`OutputDebugStringA`][2]. To
receive this output, it's necessary to have a debugger such as WinDBG attached
to the process in which the Meterpreter is running (use the `getpid` command to
view the current process ID).

## Target Side (`python/meterpreter`)

The Python Meterpreter can generate debugging output by setting the following
datastore options:

| Datastore Option         | Value   | Description                        |
| ------------------------ | ------- | ---------------------------------- |
| `PythonMeterpreterDebug` | `true`  | Enable generating debug output     |
| `MeterpreterTryToFork`   | `false` | Keep the process in the foreground |

With these two options set, the payload can be executed from the command line
and diagnostic information will be displayed. To interact with and debug the
payload, use Python's included `pdb` module. Write the stager output to a file,
then start it with the debugger attached using the command
`python -m pdb meterpreter.py`. For a more fully-featured debugging CLI, use the
third-party IPython variant `ipdb`.

## Target Side (Mettle Meterpreter)

The Mettle Meterpreter can generate debugging output by setting the following
datastore options:

| Datastore Option        | Value   | Description                        |
| ----------------------- | ------- | ---------------------------------- |
| `MeterpreterDebugLevel` | `3`     | Increase the level of output       |
| `PrependFork`           | `false` | Keep the process in the foreground |

With these two options set, the payload can be executed from the command line
and diagnostic information will be displayed. To interactively debug the
payload (inspect the state, memory, set breakpoints etc.) use a native debugger
for the specific platform on which it is running (e.g. use `gdb` when debugging
on the Linux platform).

[1]: https://github.com/rapid7/metasploit-payloads/tree/master/c/meterpreter
[2]: https://docs.microsoft.com/en-us/windows/win32/api/debugapi/nf-debugapi-outputdebugstringa
