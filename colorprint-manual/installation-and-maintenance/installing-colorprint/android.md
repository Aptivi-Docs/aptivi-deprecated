---
description: ColorPrint on your phone!
---

# 📲 Android

The tricky part is getting ColorPrint to run on Android phones and tablets, especially those that run the latest version of Android.

## Installation

To install ColorPrint on your phone or tablet, install the following dependencies:

* [Termux](https://termux.dev/en/)
* [Ubuntu PRoot](https://wiki.termux.com/wiki/PRoot#Installing_Linux_distributions)

Ensure that your Android version is compatible with Termux. You need at least 8 GB of free storage and Android 7.0 or higher.

Once you're done, follow the steps:

1. Install Termux
2. Install `proot-distro` using the following command:
   * `pkg install proot-distro`
3. Install the Ubuntu proot
   * `proot-distro install ubuntu`
4. Log in to the Ubuntu proot
   * `proot-distro login ubuntu`
5. Ensure that you've updated the package cache
   * `apt update`
   * `apt dist-upgrade`
6. Install the .NET 6.0 runtime
   * `apt install dotnet-runtime-6.0`
7. Install `wget` to download the latest release from [this page](https://github.com/Aptivi/ColorPrint/releases).
   * `apt install wget`
   * `wget https://github.com/Aptivi/ColorPrint/releases/download/vx.x.x/vx.x.x-Core.rar`
8. Install `unrar` (from multiverse) to extract the files
   * `apt install unrar`
   * `unrar vx.x.x-Core.rar`
9. Execute `dotnet ColorPrint.dll`
