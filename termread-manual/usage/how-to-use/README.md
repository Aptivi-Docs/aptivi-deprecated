---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `TermRead` namespace in any piece of code you want to use the library, as in: `using TermRead.Reader;`

Just use the `TermReader` class that contains:

* `Read()`
* `Read(string)`
* `Read(string, string, bool, bool)`
* `ReadPassword()`
* `ReadPassword(string)`

Each one of these functions creates a reader state, `TermReaderState`, that contains essential information about the current reader state, including, but not limited to:

* Current text
* Input prompt text
* Current text position
* Kill buffer

Any key will append the selected characters to the current text input, and `RETURN` will accept the input. For more information about key bindings, go to the below page.

{% content-ref url="keybindings.md" %}
[keybindings.md](keybindings.md)
{% endcontent-ref %}
