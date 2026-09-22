---
description: Your network!
---

# 🌍 Network

This lists information about the network cards that are parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name            |
| ------- | ---------------------- |
| Linux   | `006#Network`          |
| Windows | `Win32_NetworkAdapter` |
| macOS   | `SPNetworkDataType`    |

You can call the module either by enumerating through the entire dictionary of the network cards, or you can use the card name directly as follows:

```csharp
HardwareInfo.Network["Realtek PCIe GBE Family Controller"].<property>
```

which `<property>` is:

| Property      | Type   | Description         |
| ------------- | ------ | ------------------- |
| Name          | String | Network card name   |
| Driver        | String | Driver used         |
| DriverVersion | String | Driver version used |
| Duplex        | String | Network duplex      |
| Speed         | String | Network speed       |
| State         | String | Network state       |
| MacAddress    | String | MAC Address         |
| DeviceID      | String | Device ID           |
| BusID         | String | Device  ID          |
| ChipID        | String | Device chip ID      |

{% hint style="warning" %}
**Compatibility notes:**

* Network duplex type and bus ID are not supported yet on Windows.
* Unfortunately, for macOS users, the majority of the properties are not supported yet.
{% endhint %}
