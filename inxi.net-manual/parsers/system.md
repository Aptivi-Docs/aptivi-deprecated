---
description: Your operating system
---

# 🖥️ System

This lists information about the system that is parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name             |
| ------- | ----------------------- |
| Linux   | `000#System`            |
| Windows | `Win32_OperatingSystem` |
| macOS   | `SPSoftwareDataType`    |

You can call the module as follows:

```csharp
HardwareInfo.System.<property>
```

which `<property>` is:

| Property       | Type    | Description                                          |
| -------------- | ------- | ---------------------------------------------------- |
| Hostname       | String  | Host name                                            |
| SystemVersion  | String  | Unix/BSD kernel version or Windows NT kernel version |
| SystemBits     | Integer | System bits2                                         |
| SystemDistro   | String  | System name                                          |
| DesktopManager | String  | Desktop manager                                      |
| WindowManager  | String  | Window manager                                       |
| DisplayManager | String  | Display manager                                      |

{% hint style="warning" %}
**Compatibility notes:**

* Desktop and display managers are not supported yet on Windows.
* System bit width, DE, WM, and DM are not supported yet on macOS.
{% endhint %}
