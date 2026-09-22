---
description: Your computer's brain!
---

# 🧠 Processor

This lists information about the processors that are parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name          |
| ------- | -------------------- |
| Linux   | `003#CPU`            |
| Windows | `Win32_Processor`    |
| macOS   | `SPHardwareDataType` |

You can call the module either by enumerating through the entire dictionary of the processors, or you can use their names directly as follows:

```csharp
HardwareInfo.CPU["Intel(R) Core(TM) i7-8700 @ 3.20GHz"].<property>
```

which `<property>` is:

| Property  | Type    | Description                 |
| --------- | ------- | --------------------------- |
| Name      | String  | CPU name                    |
| Topology  | String  | CPU topology                |
| Type      | String  | CPU type                    |
| Bits      | Integer | CPU bits (32-bit or 64-bit) |
| Milestone | String  | CPU milestone               |
| Flags     | String  | CPU flags                   |
| L2        | String  | L2 cache size               |
| L3        | Integer | L3 cache size               |
| Rev       | String  | CPU rev                     |
| BogoMips  | Integer | CPU bogomips                |
| Speed     | String  | CPU speed                   |

{% hint style="warning" %}
**Compatibility notes:**

* CPU milestone, topology, and bogomips are not implemented yet on Windows
* L3 cache size is not implemented yet on Linux
* L2 cache size and CPU speed are only supported on macOS
{% endhint %}
