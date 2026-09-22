---
description: How does it work?
---

# ⚒️ How it works

When `GetUname` gets called, it first checks to see if uname exists in the following paths:

* `/bin/uname`
* `/usr/bin/uname`
* `/system/xbin/uname` (Android)

If it exists, it translates the passed flags to their respective arguments for the above `uname` program:

* Kernel name (`UnameTypes.KernelName`)
  * `-s`
* Kernel release (`UnameTypes.KernelRelease`)
  * `-r`
* Kernel version (`UnameTypes.KernelVersion`)
  * `-v`
* Network host name (`UnameTypes.NetworkNode`)
  * `-n`
* Machine architecture (`UnameTypes.Machine`)
  * `-m`
* Operating system (`UnameTypes.OperatingSystem`)
  * `-o`

The library then proceeds to call the application with the specified arguments. As soon as `uname` finishes outputting the specified system info type, it returns the output as a string.

For more information about the `uname` command, refer to [the manual page](https://linux.die.net/man/1/uname).
