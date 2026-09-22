---
description: How does it work?
---

# ⚒️ How it works

VT.NET contains several techniques on how to work with the VT sequences contained in the text.

## Techniques

There are currently four types of operations.

### Filters

Found in `VtSequenceTools.FilterVTSequences()`, when this function is called, the library selects the appropriate regular expression for the sequence type and replaces the found sequences with blanks. You can optionally replace it with something, like a text, a syntax, or even another VT sequence.

### Matches

Found in `VtSequenceTools.MatchVTSequences()`, when this function is called, the library selects the appropriate regular expression for the sequence type and gets all the matched regular expressions. You can then wrap the values in the `for` or the `foreach` loop to get match information for each matched sequence.

### Queries

Found in `VtSequenceTools.IsMatchVTSequences()`, when this function is called, the library selects the appropriate regular expression for the sequence type and checks the text to see if any part of the text is a VT sequence.

Additionally, it contains `IsMatchVTSequencesSpecific()`, which helps to check the text for any specific VT sequence type.

### Splits

Found in `VtSequenceTools.SplitVTSequences()`, when this function is called, the library selects the appropriate regular expression for the sequence type and splits the text with the matched VT sequences as delimiters.

## Regex of VT expressions

Each type of VT sequences listed below by the `VtSequenceRegexes` class are supported by VT.NET for the above operations.

* CSI sequences (`CSISequences`)
  * `(\x9B|\x1B\[)[0-?]*[ -\/]*[@-~]`
* OSC sequences (`OSCSequences`)
  * `(\x9D|\x1B\]).+(\x07|\x9c)`
* ESC sequences (`ESCSequences`)
  * ``\x1b [F-Nf-n]|\x1b#[3-8]|\x1b%[@Gg]|\x1b[()*+][A-Za-z0-9=`<>]|\x1b[()*+]""[>4?]|\x1b[()*+]%[0-6=]|\x1b[()*+]&[4-5]|\x1b[-.\/][ABFHLM]|\x1b[6-9Fcl-o=>\|\}~]``
* APC sequences (`APCSequences`)
  * `(\x9f|\x1b_).+\x9c`
* DCS sequences (`DCSSequences`)
  * `(\x90|\x1bP).+\x9c`
* PM sequences (`PMSequences`)
  * `(\x9e|\x1b\^).+\x9c`
* C1 sequences (`C1Sequences`)
  * `\x1b[DEHMNOVWXYZ78]`
* All VT sequences (`AllVTSequences`)
