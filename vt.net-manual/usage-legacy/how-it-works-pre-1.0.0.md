---
description: How does it work?
---

# ⚒️ How it works (pre-1.0.0)

{% hint style="warning" %}
We highly recommend using version 1.0.0 of VT.NET to get the most out of its features. We support using version 0.2.0.1 or lower until **February 22nd, 2024**.

[Click here](../usage/how-to-use/) to learn more.
{% endhint %}

VT.NET contains several techniques on how to work with the VT sequences contained in the text.

## Techniques

There are currently four types of operations.

### Filters

Found in `VT.NET.Filters`, when any of its functions is called, the library selects the appropriate regular expression for the sequence type and replaces the found sequences with blanks. You can optionally replace it with something, like a text, a syntax, or even another VT sequence.

### Matches

Found in `VT.NET.Matches`, when any of its functions is called, the library selects the appropriate regular expression for the sequence type and gets all the matched regular expressions. You can then wrap the values in the `for` or the `foreach` loop to get match information for each matched sequence.

### Queries

Found in `VT.NET.Queries`, when any of its functions is called, the library selects the appropriate regular expression for the sequence type and checks the text to see if any part of the text is a VT sequence.

### Splits

Found in `VT.NET.Splits`, when any of its functions is called, the library selects the appropriate regular expression for the sequence type and splits the text with the matched VT sequences as delimiters.

## Regex of VT expressions

Each type of VT sequences listed below by the `RegexVTExpressions` class are supported by VT.NET for the above operations.

* All VT sequences (`AllVTSequences`)
  * ``(\x9D|\x1B\]).+(\x07|\x9c)|\x1b [F-Nf-n]|\x1b#[3-8]|\x1b%[@Gg]|\x1b[()*+][A-Za-z0-9=`<>]|\x1b[()*+]""[>4?]|\x1b[()*+]%[0-6=]|\x1b[()*+]&[4-5]|\x1b[-.\/][ABFHLM]|\x1b[6-9Fcl-o=>\|\}~]|(\x9f|\x1b_).+\x9c|(\x90|\x1bP).+\x9c|(\x9B|\x1B\[)[0-?]*[ -\/]*[@-~]|(\x9e|\x1b\^).+\x9c|\x1b[DEHMNOVWXYZ78]``
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

All these expressions can be accessed using the `RegexVTExpressions` class.
