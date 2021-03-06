---
UID: NF:netwakesource.NetWakeSourceGetAdapter
title: NetWakeSourceGetAdapter function (netwakesource.h)
author: windows-driver-content
description: The NetWakeSourceGetAdapter method gets the net adapter for a wake-on-LAN (WoL) source.
tech.root: netvista
ms.assetid: 75706f44-2e82-420d-a435-73ee32e5090a
ms.author: windowsdriverdev
ms.date: 10/07/2019
ms.topic: function
f1_keywords:
 - "netwakesource/NetWakeSourceGetAdapter"
ms.keywords: NetWakeSourceGetAdapter
req.header: netwakesource.h
req.include-header:
req.target-type:
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
- NetWakeSourceGetAdapter
product: 
- Windows
targetos: Windows
ms.custom: Vb
---

# NetWakeSourceGetAdapter function


## -description

The **NetWakeSourceGetAdapter** method gets the net adapter for a wake-on-LAN (WoL) source.

## -parameters

### -param WakeSource

The NETWAKESOURCE object that represents the source of the wake-up event.

## -returns

Returns the NETADAPTER object that represents the net adapter for this wake source.

## -remarks

Client drivers that have one network adapter per device do not need to call this optional method. Call **NetWakeSourceGetAdapter** if your device has more than one net adapter object per device, such as in a [MBBCx client driver](https://docs.microsoft.com/windows-hardware/drivers/netcx/mobile-broadband-mbb-wdf-class-extension-mbbcx).

The client driver must only call **NetWakeSourceGetAdapter** during a power transition, typically from its *[EVT_WDF_DEVICE_ARM_WAKE_FROM_SX](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)*, *[EVT_WDF_DEVICE_ARM_WAKE_FROM_S0](../wdfdevice/nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)*, or *[EVT_NET_DEVICE_PREVIEW_WAKE_SOURCE](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)* callback function. Otherwise, the call results in a system bugcheck.

## -see-also

[Configuring power management](https://docs.microsoft.com/windows-hardware/drivers/netcx/configuring-power-management)

[**NetWakeSourceListGetElement**]