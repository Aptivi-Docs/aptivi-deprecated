---
description: Battery low. Charge now!
---

# 🔋 Battery

This lists information about the batteries that are parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name             |
| ------- | ----------------------- |
| Linux   | `004#Graphics`          |
| Windows | `Win32_VideoController` |
| macOS   | `N/A`                   |

You can call the module either by enumerating through the entire list of batteries, or you can use the index of the battery directly as follows:

```csharp
HardwareInfo.Battery[0].<property>
```

which `<property>` is:

| Property  | Type    | Description               |
| --------- | ------- | ------------------------- |
| Name      | String  | Battery name              |
| Charge    | Integer | Battery charge in percent |
| Condition | String  | Battery charge condition  |
| Volts     | String  | Battery voltage           |
| Model     | String  | Battery model             |
| Status    | String  | Battery status            |

{% hint style="warning" %}
**Compatibility notes:**

* Battery info is not supported yet on macOS
{% endhint %}
