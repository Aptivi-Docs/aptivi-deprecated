# 0.0.8-Development

### What is 0.0.8?

0.0.8 is not like 0.0.7, and is not a service pack for 0.0.7, but will be different from all the versions. It includes even bigger changes than 0.0.4, and is not backwards-compatible with the previous versions.

The Ubuntu PPA in Launchpad is planned to come, but requires shortening the .exe files for easy launch to `KS.exe` instead of `Kernel Simulator.exe` and requires a launch script, which will be called `startks`.

### The Limitations of Early Development Stage

We can't ship this version in `Chocolatey Gallery`, `NuGet.org`, and `GitHub Package Registry`, because it is currently in early development stage. Also, we will localize strings slowly beginning from the beginning of 2020, so you will see lots of `! Needs localization !` error before the new strings in versions built before 2020.

This version is highly experimental and could cause bugs, failures, and all kinds of missing error handling. However, issues and pull requests for this experimental version will be accepted under the circumstances specified in [the list.](https://github.com/EoflaOE/Kernel-Simulator/blob/master/CONTRIBUTING.md)

Also, development versions don't provide all the features and bug fixes unlike the finished version. There may be deprecated things somewhere.

So, always test this version with caution, and if you would like to be on the safe zone, see the [Releases](https://github.com/EoflaOE/Kernel-Simulator/releases).

### Great feature, called notifications

Notification feature is the long-awaited feature which is included with the 0.0.8 version. Currently, they are not being used, but they will be in the next development commits. It behaves like Android, because it shows notifications for few seconds, then goes to the next one.

### This is what we're waiting for, KS 0.0.8 RC1!

After months of development, we have switched from Milestone 3 to KS 0.0.8 RC1. That means that we have localized all new strings, and are making final touches to the final version of 0.0.8. However, it may have bugs and issues, so report all the issues to the Issues section.

We still can't ship this version in `Chocolatey Gallery`, `NuGet.org`, and `GitHub Package Registry`, because the final release is not made yet.
