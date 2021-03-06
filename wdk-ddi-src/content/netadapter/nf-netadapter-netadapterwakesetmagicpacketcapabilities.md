---
UID: NF:netadapter.NetAdapterWakeSetMagicPacketCapabilities
title: NetAdapterWakeSetMagicPacketCapabilities function (netadapter.h)
author: windows-driver-content
description: The NetAdapterWakeSetMagicPacketCapabilities method sets a net adapter's magic packet wake on LAN (WoL) capabilities.
tech.root: netvista
ms.assetid: 43c226cd-11a2-4250-95d3-be9e2986acc2
ms.author: windowsdriverdev
ms.date: 10/25/2019
ms.topic: function
f1_keywords:
 - "netadapter/NetAdapterWakeSetMagicPacketCapabilities"
ms.keywords: NetAdapterWakeSetMagicPacketCapabilities
req.header: netadapter.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: The next version of Windows 10
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib: netadaptercxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- netadaptercxstub.lib
api_name: 
- NetAdapterWakeSetMagicPacketCapabilities
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetAdapterWakeSetMagicPacketCapabilities function


## -description

The **NetAdapterWakeSetMagicPacketCapabilities** method sets a net adapter's magic packet wake on LAN (WoL) capabilities.

## -parameters

### -param Adapter

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities

A pointer to a client driver-allocated and initialized [**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_magic_packet_capabilities.md) structure.

## -returns

This method does not return a value.

## -remarks

Client drivers must call [**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_magic_packet_capabilities_init.md) to initialize the **NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES** structure, then set the structure's members appropriately before calling this method. Client drivers typically call this method from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this method before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_magic_packet_capabilities.md)

[**NET_ADAPTER_WAKE_MAGIC_PACKET_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_magic_packet_capabilities_init.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)