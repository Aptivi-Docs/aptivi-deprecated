---
description: How does it work?
---

# ⚒️ How it works

When RuntimeTrim is run on a build output directory, it first checks for the `runtimes` folder for existence.

If RuntimeTrim detects that this folder exists, it attempts to get the runtime identifier (RID) graph from the current RID based on the current operating system and architecture.

It then makes a list of all the architecture-based folders to be kept and the second list, which is called a blacklist, of the remaining folders to be removed. RuntimeTrim then deletes every single folder listed in the "blacklist."
