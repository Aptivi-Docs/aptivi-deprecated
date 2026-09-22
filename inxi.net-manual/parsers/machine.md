---
description: Your computer!
---

# 💻 Machine

This lists information about the machine that is parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name                                                              |
| ------- | ------------------------------------------------------------------------ |
| Linux   | `001#Machine`                                                            |
| Windows | <p><code>Win32_ComputerSystem</code><br><code>Win32_BaseBoard</code></p> |
| macOS   | `SPHardwareDataType`                                                     |

You can call the module as follows:

```csharp
HardwareInfo.Machine.<property>
```

which `<property>` is:

| Property         | Type   | Description                      |
| ---------------- | ------ | -------------------------------- |
| Type             | String | Machine type (Desktop or Laptop) |
| Product          | String | Machine product name             |
| System           | String | Machine system name              |
| Chassis          | String | Machine chassis                  |
| MoboManufacturer | String | Motherboard manufacturer         |
| MoboModel        | String | Motherboard model                |

{% hint style="warning" %}
**Compatibility notes:**

* Machine chassis is not supported yet on Windows.
{% endhint %}
