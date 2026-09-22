# Beep Synths

Beep synths are scripted files that has their own lines of frequencies and times in millseconds, as well as the comments. They usually start with the signature of `KS-BSynth`.

Let's see how they are formed.

## Formation of scripted files

The file could be any extension that are interpreted as text files (txt files). First off, it should start with the abovementioned signature.

Now, after pressing ENTER, you can make your own chapters, synths, etc. However, the below format should be used in the example below:

```
<freq>, <ms>
323, 64
323, 750
424, 87
```

The comments may also be added to the beep synth files to represent chapters, verses, etc. However, it doesn't support in-line comments yet. They are written in this format:

```
-<message>
- <message>
```

An example of a sane synth file that has two chapters:

```
KS-BSynth

- Chapter 1
323, 64
323, 750
424, 87

- Chapter 2
400, 500
800, 1000
400, 500
800, 1000
```

To play such synth files, you must run Kernel Simulator, and instruct it to play the synth file using the `bsynth` command with proper filename.

## More Examples?

They are not ready yet, so the `KSBeepSynths` repository is not available yet. We will make it available soon.
