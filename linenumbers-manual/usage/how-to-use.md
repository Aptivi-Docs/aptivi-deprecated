---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `LineNumbers.Core` namespace in any piece of code you want to use the library, as in: `using LineNumbers.Core;`

In order to get line information, just invoke the `LinesInfo` constructor when assigning a new variable that holds line information. For example,

```csharp
var LinesInfo = new LinesInfo("path/to/project.sln");
```

This will process your solution file with the help of the `Microsoft.CodeAnalysis` library that contains necessary functions. Alternatively, you can use your existing `MSBuildWorkspace` to fetch a `Solution` from it.

```csharp
var LinesInfo = new LinesInfo(Solution);
```

Line numbers are implemented below:

* Line numbers of a solution
  * `SolutionLineNumber`
* Line numbers of each project in a solution
  * `LineNumbersByProject`
* Line numbers of each code file found in a solution
  * `LineNumbersByCodeFiles`
* Line numbers of each code file found in each project in a solution
  * `LineNumbersByCodeFilesByProject`
