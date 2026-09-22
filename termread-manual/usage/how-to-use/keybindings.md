---
description: Press any key!
---

# ⌨️ Keybindings

TermRead implements the following keybindings to interact with the input:

| Keybinding          | Action                                               |
| ------------------- | ---------------------------------------------------- |
| `ENTER`             | Accepts input                                        |
| `Ctrl`+`C`          | Cancels reading (if `TreatCtrlCAsInput` is enabled)  |
| `Ctrl`+`A` / `HOME` | Beginning of line                                    |
| `Ctrl`+`E` / `END`  | End of line                                          |
| `Ctrl`+`B` / `←`    | Backward one character                               |
| `Ctrl`+`F` / `→`    | Forward one character                                |
| `BACKSPACE`         | Remove one character from the left                   |
| `UP ARROW`          | Get the older input                                  |
| `DOWN ARROW`        | Get the newer input                                  |
| `DELETE`            | Remove one character in current position             |
| `Alt`+`B`           | One word backwards                                   |
| `Alt`+`F`           | One word forwards                                    |
| `TAB`               | Next auto-completion entry                           |
| `SHIFT`+`TAB`       | Previous auto-completion entry                       |
| `CTRL`+`U`          | Cut to the start of the line                         |
| `CTRL`+`K`          | Cut to the end of the line                           |
| `CTRL`+`W`          | Cut to the end of the previous word                  |
| `ALT`+`D`           | Cut to the end of the next word                      |
| `CTRL`+`Y`          | Yank the cut content                                 |
| `CTRL`+`Y`          | Yank the cut content                                 |
| `Alt`+`L`           | Make word lowercase                                  |
| `Alt`+`U`           | Make word uppercase                                  |
| `Alt`+`C`           | Make character uppercase and move to the end of word |
| `Alt`+`V`           | Make character lowercase and move to the end of word |

{% hint style="warning" %}
**Warning:** Some of the keys conflict with the terminal emulator keybindings.
{% endhint %}
