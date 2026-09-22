---
description: How do you use it?
---

# 🖥️ How to use

VT.NET provides several filtering and manipulation tools which allow you to perform these operations on strings that contain escape sequences under the `VT.NET.Tools` namespace. Currently, these tools are provided:

| Function                         | Description                                                                            |
| -------------------------------- | -------------------------------------------------------------------------------------- |
| FilterVTSequences()              | Filters all of the VT sequences                                                        |
| MatchVTSequences()               | Matches all of the VT sequences                                                        |
| IsMatchVTSequences()             | Does the string contain all of the VT sequences or a VT sequence of any type?          |
| IsMatchVTSequencesSpecific()     | Does the string contain all of the VT sequences or a VT sequence of any specific type? |
| SplitVTSequences()               | Splits all of the VT sequences                                                         |
| DetermineTypeFromText()          | Determines the VT sequence type from the given text                                    |
| GetSequenceFilterRegexFromType() | Gets the sequence filter regular expression from the provided VT sequence type         |

Place the `using VT.NET.Tools;` directive at the top of the file that you want to call these functions in. You need to put the class name `VtSequenceTools` before the function name mentioned above so that it looks like this:

<pre class="language-csharp"><code class="lang-csharp">char BellChar = Convert.ToChar(0x7);
char EscapeChar = Convert.ToChar(0x1b);
char StringTerminator = Convert.ToChar(0x9c);
string vtSequence1 = $"{EscapeChar}[38;5;43m";
<strong>string filtered = VtSequenceTools.FilterVTSequences($"Hello!{vtSequence1}");
</strong><strong>Console.WriteLine(filtered);
</strong></code></pre>
