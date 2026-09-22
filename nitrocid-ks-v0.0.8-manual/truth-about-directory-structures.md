# Goodbye, directory structure parsing

We have let KS parse the entire directory structure since the actual file system was implemented on 0.0.5.14, which is a pre-release version of 0.0.6. The `InitFS()` (previously `Init()`) function involved initializing the file structure by parsing the entire Home directory and all its subdirectories and files.

We thought this is good, but over time, its usage (not the entire FS, but its structures) starts to decrease. Examples are listed below:

* You have `SetCurrDir()` that doesn't use the FS structure list to see if the folder exists or not
* You have `copy` command that uses `{Directory|File}.Exists()` to check for directory or file existence
* You have `md` command that uses `Directory.Exists()` to check for directory existence
* You have `read` command that uses `File.Exists()` to check for file existence

Also, the filesystem structures are initialized every startup and every directory change. This causes additional load on the hard drive, especially on the first cold startup, making startup times longer than usual. The problem gets worse if your filesystem is too big and contains many directories and files, as it scans the entire directory, files, the subdirectories, and what's inside them. If this happens, then it's like you're telling the hard drive to read the entire directory structure.

We have fears of hard drives thrashing, especially the SSDs where they have read and write limits and if exceeded, would no longer work properly, so we have to put an end to the directory structure parsing function. If this happens, the below happens:

* Hard drive usage will be decreased
* Faster start-up times
* Faster directory change
* Increases the lifespan of both hard drives and SSDs

It will be removed in the next version.
