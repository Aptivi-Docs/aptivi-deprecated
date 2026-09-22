---
description: Can I build a VT sequence?
---

# 🧰 VT Sequence Builder

VT.NET offers a Builder namespace that contains building blocks for building a VT sequence for your console applications.

It starts with `VtSequenceBasicChars` which allows you to get a variety of starting-point characters for your VT sequence in case you want to manually build the sequence yourself. Here are the available characters:

* `BEL (\x07 - CTRL+G - BellChar)`
* `BS (\x08 - CTRL+H - BackspaceChar)`
* `CR (\x0D - CTRL+M - CarriageReturnChar)`
* `ENQ (\x05 - CTRL+E - ReturnTerminalStatusChar)`
* `FF (\x0C - CTRL+L - FormFeedChar)`
* `LF (\x0A - CTRL+J - LineFeedChar)`
* `SI (\x0F - CTRL+O - StandardCharacterSetChar)`
* `SO (\x0E - CTRL+N - AlternateCharacterSetChar)`
* `SP (" " - SPACE - SpaceChar)`
* `TAB (\x09 - CTRL+I - HorizontalTabChar)`
* `VT (\x0B - CTRL+K - VerticalTabChar)`
* `ESC (\x1B - VerticalTabChar)`
* `ST (\x9C - VerticalTabChar)`

Each type of VT sequence contain their own class files that stores both the regex match information about specific actions and sequence generation functions based on the given action and argument. Here are a list of supported sequence types:

* APC sequences
  * Application program command
* C1 sequences
  * 8-bit control characters
* CSI sequences
  * Controls beginning with control sequence introducer
* DCS sequences
  * Device control
* ESC sequences
  * Controls beginning with ESC
* OSC sequences
  * Operating system command sequences
* PM sequences
  * Privacy message

To learn more about these sequences, visit the below page:

{% embed url="https://invisible-island.net/xterm/ctlseqs/ctlseqs.html" %}
