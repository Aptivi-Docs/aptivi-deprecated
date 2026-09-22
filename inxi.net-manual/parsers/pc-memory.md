---
description: Random Access Memory (RAM)
---

# 📄 PC Memory

This lists information about the PC memory that is parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name               |
| ------- | ------------------------- |
| Linux   | `011#Info` > `002#Memory` |
| Windows | `Win32_OperatingSystem`   |
| macOS   | `SPHardwareDataType`      |

You can call the module as follows:

```csharp
HardwareInfo.RAM.<property>
```

which `<property>` is:

| Property    | Type   | Description      |
| ----------- | ------ | ---------------- |
| TotalMemory | String | Total memory1    |
| UsedMemory  | String | Used memory1 3   |
| FreeMemory  | String | Free memory1 2 3 |

{% hint style="info" %}
Memory is automatically GiB in Inxi on Unix systems, and is in bytes on Windows systems.
{% endhint %}

{% hint style="warning" %}
**Compatibility notes:**

* Free memory is not implemented yet on Linux.
* Used memory and free memory properties are not implemented yet on macOS.
{% endhint %}
