---
description: Parts of drive
---

# 🍕 Drive partitions

There are two types of partitions supported by Inxi.NET.

### Drive partitions

This lists information about the partitions of a hard drive that are parsed by Inxi. You can use the below properties to learn more about its information.

You can call the module either by enumerating through the entire dictionary of the partitions, or you can use their names directly as follows:

```csharp
HardwareInfo.HDD["TOSHIBA DT01ACA100"].Partitions["<partition>"].<property>
```

which `<partition>` is either:

* the `/dev` path for a partition, such as `/dev/sda1`, `/dev/mmcblk0p4`, or `/dev/nvme1n2`, on Linux systems, or
* the physical partition indicator in this format: `Physical partition in <Model> (<DiskIndex>) : <PartitionIndex>` on Windows systems

and `<property>` is:

| Property   | Type   | Description          |
| ---------- | ------ | -------------------- |
| ID         | String | Partition ID         |
| FileSystem | String | Partition filesystem |
| Size       | String | Partition size       |
| Used       | String | Used partition size  |

{% hint style="info" %}
Partition size is automatically GiB in Inxi on Unix systems, and is in bytes on Windows systems.
{% endhint %}

### Logical partitions

{% hint style="warning" %}
This is not available for non-Windows systems.
{% endhint %}

Inxi.NET has an additional option where you can provide logical partitions. They're found on `LogicalParts` module which you can either call by enumerating through the entire dictionary of the partitions, or you can use their names directly as follows:

```csharp
HardwareInfo.LogicalParts["Logical partition <ID>"].<property>
```

which `<property>` is:

| Property   | Type   | Description                  |
| ---------- | ------ | ---------------------------- |
| Letter     | String | Partition Letter             |
| FileSystem | String | Partition filesystem         |
| Size       | String | Partition size in bytes      |
| Used       | String | Used partition size in bytes |
