---
description: Music and Sound
---

# 🎷 Sound

This lists information about the sound cards that are parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name         |
| ------- | ------------------- |
| Linux   | `005#Audio`         |
| Windows | `Win32_SoundDevice` |
| macOS   | `SPAudioDataType`   |

You can call the module either by enumerating through the entire dictionary of the sound cards, or you can use their names directly as follows:

```csharp
HardwareInfo.Sound["Creative X-Fi Audio Processor (WDM)"].<property>
```

which `<property>` is:

| Property | Type   | Description       |
| -------- | ------ | ----------------- |
| Name     | String | Sound card name   |
| Vendor   | String | Sound card vendor |
| Driver   | String | Sound card driver |
| BusID    | String | Device ID         |
| ChipID   | String | Device ID         |

{% hint style="warning" %}
**Compatibility notes:**

* Bus ID is not supported yet on Windows.
* Bus ID and chip ID properties are not supported yet on macOS.
{% endhint %}
