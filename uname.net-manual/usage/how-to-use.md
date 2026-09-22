---
description: How do you use this?
---

# 🖥️ How to use

Using this library is very simple! Just use the `UnameNET` namespace in any piece of code you want to use the library, as in: `using UnameNET;`

Just use the `UnameManager` class that contains:

* `GetUname(UnameTypes)`

This function queries information about your kernel and its basic information, like your system architecture and your kernel version, based on the passed `uname` flags. Currently, it supports all the portable flags in `UnameTypes`:︎

* Kernel name (`UnameTypes.KernelName`)
* Kernel release (`UnameTypes.KernelRelease`)
* Kernel version (`UnameTypes.KernelVersion`)
* Network host name (`UnameTypes.NetworkNode`)
* Machine architecture (`UnameTypes.Machine`)
* Operating system (`UnameTypes.OperatingSystem`)
