---
description: How do we use this application?
---

# 💻 How to use

RuntimeTrim must be launched with arguments providing paths to the build output of any project that contains the `runtimes` folder. For example, if you're running Linux and you're trying to trim the `runtimes` folder off Nitrocid's build output folder (`/home/user/ksbin`), you'd be executing RuntimeTrim like this:

```shell-session
$ dotnet RuntimeTrim.dll /home/user/ksbin
```

Once done, you'll find that the build output is now significantly smaller than before, depending on how many library files are there in the runtimes folder.
