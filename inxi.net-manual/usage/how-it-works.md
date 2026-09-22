---
description: How does it work?
---

# ⚒️ How it works

Inxi.NET first checks for the platform to know what parser should be called. If the target platform is Unix, it searches for the three files in your system:

* `/usr/bin/inxi`
* `/usr/bin/cpanel_json_xs`
* `/usr/bin/json_xs`

Then, it creates a new instance of `HardwareInfo` that checks to see if the system is Unix. If this is satisfied, the Inxi program is executed and the JSON output is fetched.

Then, Inxi.NET parses the hardware types according to the selected hardware types.

If you're running Windows, your logical partitions will get parsed. Logical partitions are not available on Unix, so you'll have to rely on the disk information instead.

As soon as all the hardware gets parsed, the resulting hardware for each type will get added to the list. Finally, Inxi.NET installs all the lists to the class instance for you to use.

Each parser has its own hardware type, so choose one of the parsers from the left sidebar to get started.
