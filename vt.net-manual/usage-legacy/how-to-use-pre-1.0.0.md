---
description: How do you use it?
---

# 🖥️ How to use (pre-1.0.0)

{% hint style="warning" %}
We highly recommend using version 1.0.0 of VT.NET to get the most out of its features. We support using version 0.2.0.1 or lower until **February 22nd, 2024**.

[Click here](../usage/how-to-use/) to learn more.
{% endhint %}

Using this library is very simple! Just use the `VT.NET` namespace in any piece of code you want to use the library, as in: `using VT.NET;`

This library is categorized to four different classes to select your operation mode:

* `Filters`: filters the VT sequences from the text
* `Matches`: matches the VT sequences from the text
* `Queries`: queries the VT sequences from the text
* `Splits`: splits the VT sequences from the text

Each of these classes may be referenced statically in your application. Once done, you should be able to call the functions inside them, each with the specific filter for each VT sequence type:

* All VT sequences
* CSI sequences
* OSC sequences
* ESC sequences
* APC sequences
* DCS sequences
* PM sequences
* C1 sequences
