---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `Addresstigator` namespace in any piece of code you want to use the library, as in: `using Addresstigator;`

Just use the `Tools` class that contains:

* `GetIspConfig(string, bool)`

This function downloads the relevant information for the specified mail address from the ISP database and processes it before returning the client configuration. Mail clients can use this configuration to set up automatic mail server configuration detection akin to Mozilla Thunderbird.
