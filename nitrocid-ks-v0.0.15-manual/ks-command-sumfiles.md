# sumfiles command

## Summary

Calculates the sum of files

## Description

Calculating the hash sum of files is important, because it lets users verify if the file is corrupt or not. It calculates the sum of files in a directory using either the MD5, SHA1, or SHA256 algorithms.

## Command usage

* sumfiles (MD5/SHA1/SHA256) (directory) \[outputFile]

## Examples

* sumfiles MD5 Pictures: Calculates the MD5 sum of the Pictures directory.
* sumfiles SHA256 "Operating Systems" Sums.txt: Calculates the SHA256 sum of the "Operating Systems" directory and outputs them to Sums.txt in the current working directory
