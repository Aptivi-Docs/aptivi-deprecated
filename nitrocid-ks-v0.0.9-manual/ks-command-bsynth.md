# bsynth command

## Summary

Initiates the series of beeps that are written in a file.

## Description

This command allows you to play the series of beeps in the synth file. It supports comments under this format: `- <message>`. All scripted synth files should start with KS-BSynth and have their frequencies and time separated with the comma and the space.

This is used to create beep music. Comments will make chapter separating easier. For more information, consult `Beep Synths`.

## Command usage

* bsynth (file)

## Examples

* bsynth Sequence.txt: Plays everything found in Sequence.txt
