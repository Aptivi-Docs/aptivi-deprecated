---
description: In case you want to set things up
---

# ⚙️ Reader Settings

The reader has some global settings you can set for each call to Read() or any other derivative functions. They get read each time you call this function or you activate a keybinding that uses one of these settings.

Here are the available settings that you can set:

* `PasswordMaskChar`
  * Sets the password masking character.
* `HistoryEnabled`
  * Whether the history is enabled or not.
* `LeftMargin`
  * Sets the left margin of the input.
* `RightMargin`
  * Sets the right margin of the input.
* `Suggestions`
  * Sets a function that you could use to return an array of strings containing auto completion data.
* `SuggestionsDelimiters`
  * Delimiters to split the current input within a function that returns a list of suggestions.
* `TreatCtrlCAsInput`
  * Whether to treat `Ctrl` + `C` as input or not. If enabled, TermRead will process this keybinding as aborting the current input.
