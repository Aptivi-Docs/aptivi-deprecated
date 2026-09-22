---
description: Basic Input/Output System (BIOS)
---

# 📀 BIOS

This lists information about BIOS that is parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name   |
| ------- | ------------- |
| Linux   | `001#Machine` |
| Windows | `Win32_BIOS`  |
| macOS   | `N/A`         |

You can call the module as follows:

```csharp
HardwareInfo.BIOS.<property>
```

which `<property>` is:

| Property | Type   | Description       |
| -------- | ------ | ----------------- |
| BIOS     | String | BIOS name         |
| Date     | String | BIOS release date |
| Version  | String | BIOS version      |

{% hint style="warning" %}
**Compatibility info:**

* BIOS information is not implemented in macOS.
{% endhint %}
