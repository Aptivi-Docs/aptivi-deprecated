---
description: How to build on Windows
---

# 🪟 Building on Windows

To build NuGlobal on Windows, you must be running a supported version of Windows. We recommend that you run Windows 10 or later.

1. Download and install Rust from the [official website](https://www.rust-lang.org/tools/install)
2. Download and install [MSYS2](https://www.msys2.org/)
3.  Open the MSYS2 terminal, and execute

    ```shell-session
    $ git clone https://github.com/Aptivi/nuglobal
    $ cd nuglobal
    $ make
    ```

You'll find the binaries under the `target` folder.
