---
description: Hard drives, SSDs, and NVMe chips
---

# 🗃️ Hard Drive

This lists information about the hard drives that are parsed by Inxi. You can use the below properties to learn more about its information.

Module name according to each operating system:

| OS      | Module name                                                                                               |
| ------- | --------------------------------------------------------------------------------------------------------- |
| Linux   | `007#Drives`                                                                                              |
| Windows | <p><code>Win32_DiskDrive</code><br><code>Win32_DiskPartition</code><br><code>Win32_LogicalDisk</code></p> |
| macOS   | `SPStorageDataType`                                                                                       |

You can call the module either by enumerating through the entire dictionary of the hard drives, or you can use their names directly as follows:

```csharp
HardwareInfo.HDD["TOSHIBA DT01ACA100"].<property>
```

which `<property>` is:

| Property   | Type                               | Description         |
| ---------- | ---------------------------------- | ------------------- |
| ID         | String                             | Drive ID            |
| Size       | String                             | Drive size          |
| Model      | String                             | Drive model         |
| Vendor     | String                             | Drive vendor        |
| Speed      | String                             | Drive speed         |
| Serial     | String                             | Drive serial number |
| Partitions | Dictionary of string and Partition | Drive partitions    |

{% hint style="info" %}
Drive size is automatically GiB in Inxi on Unix systems, and is in bytes on Windows systems.
{% endhint %}

{% hint style="warning" %}
**Compatibility notes:**

* Drive speed property is not implemented yet on Windows
* Drive speed and vendor properties are not supported yet on macOS
{% endhint %}
