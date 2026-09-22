---
description: How to build on Windows
---

# 🪟 Building on Windows

To build RuntimeTrim on Windows, you must be running a supported version of Windows. We recommend that you run Windows 10 or later.

### Using Visual Studio 2019+

1. Download and install Visual Studio
2. Once installed, open Visual Studio and click on `Clone Repository`
3. In the repository location field, write `https://github.com/Aptivi/RuntimeTrim.git`
4. Press `Clone`. The clone may need to take a few minutes depending on your Internet connection.
5. Press `Solution Explorer` » `Switch Views` and double click on `RuntimeTrim.sln`
6. Press `Start` or press `Build` » `Build Solution` to build
7. Navigate to the build output folder, `KSBuild`, and double click on the `RuntimeTrim.exe` file

### Using the command-line

If you prefer using the command-line, follow these steps:

1. Open `Git Bash` on your work directory
2. Execute `git clone https://github.com/Aptivi/RuntimeTrim.git`
3. Navigate to the cloned repository, `RuntimeTrim`
4. Execute `dotnet restore` and `dotnet build`
5. After building is done, run `dotnet run` on `RuntimeTrim/RuntimeTrim.csproj`
