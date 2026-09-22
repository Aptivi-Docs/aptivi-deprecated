---
description: How does it work?
---

# ⚒️ How it works

LineNumbers fetches the projects from the solution given to the constructor. It then fetches all the code files according to the project type:

* C# files (`.cs`)
* Visual Basic (`.vb`)

LineNumbers uses the code file array to get the line numbers of a file and adds the length to both the individual project total lines and the solution total lines.

Then, it adds the line numbers by project to the two arrays:

* Line numbers of each code file found in a solution
  * `LineNumbersByCodeFiles`
* Line numbers of each code file found in each project in a solution
  * `LineNumbersByCodeFilesByProject`

Finally, LineNumbers installs the remaining values to their arrays.
