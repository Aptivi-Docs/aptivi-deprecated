---
description: How do you use this?
---

# 🖥️ How to use

Using this library is very simple! Just use the `Yunikodo` namespace in any piece of code you want to use the library, as in: `using Yunikodo;`

Just use the `UnicodeQuery` class that contains:

* `QueryChar(char)`
* `QueryChar(int)`
* `QueryChar(char, UnicodeQueryType)`
* `QueryChar(int, UnicodeQueryType)`

You can control which database Yunikodo uses using the `UnicodeQueryType` enumeration:

* Simple: Simple Unicode characters without the Unihan characters and their info
* Full: All characters
