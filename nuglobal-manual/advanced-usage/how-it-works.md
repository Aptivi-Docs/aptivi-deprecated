---
description: How does it work?
---

# ⚒️ How it works

When any command is executed, the command handler executes the command code, which calls the package handler, `ng_package_handler`, that takes appropriate action. Based on the following cases, it'll do its job.

The package paths are resolved to the following directories:

* Systemwide paths
  * Windows: `%ALLUSERSPROFILE%/NuGlobal/Packages/<Group>`
  * Linux: `/usr/share/ng/packages/<group>`
* Userwide paths
  * Windows: `%USERPROFILE%/AppData/Local/NuGlobal/Packages/<Group>`
  * Linux: `$HOME/.config/ng/packages/<group>`

{% hint style="info" %}
In case the first userwide path can't be used on Linux, NuGlobal will fall back to `/tmp/.config/ng/packages/<group>`.
{% endhint %}

### Installation

`ng_install_package` attempts to install any NuGet package file to the group folder by copying the `nupkg` file from the source to the group folder.

### Uninstallation

`ng_uninstall_package` attempts to remove any NuGet package file from the group folder.

### Listing

`ng_list_packages` lists all the NuGet packages found in the group.

### Initialization

`ng_init_packages` initializes the NuGet feed on the target by copying all the NuGet package files to a new folder, which is the group name, in the target directory and makes a `NuGet.config` file containing the necessary information.
