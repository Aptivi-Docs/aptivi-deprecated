---
description: How does it work?
---

# ⚒️ How it works

After this function gets called, it'll generate a list of files based on the following conditions:

* If extensions are specified, it'll only attempt to add files ending in one of these extensions to the list of files to be processed
* If extensions are not specified, it'll add all the files to the list.

Then, NameNumerizer attempts to append the numbers to the start of the file name in this format:

```
##. FileName.ext
```

where:

* `##`: the file number that is padded left to the number of digits for the last file, for example, it'll be `001` if the list contains `100 < n < 1000` files.
* `FileName`: The usual file name
* `.ext`: The usual file extension

NameNumerizer repeats the operation for all the files to be processed.
