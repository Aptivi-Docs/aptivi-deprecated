---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `Dictify` namespace in any piece of code you want to use the library, as in: `using Dictify;`

Just use the `DictionaryManager` class that contains:

* `GetWordInfo(string)`
* `GetWordInfoAsync(string)`

You can then use the resulting array to iterate through possible words and get the values from them.

{% hint style="info" %}
If you're going to use this library on web projects or in situations that require you to use the asynchronous version, use the `GetWordInfoAsync`.
{% endhint %}
