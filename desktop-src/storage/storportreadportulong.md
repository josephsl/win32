---
title: StorPortReadPortUlong routine
description: The StorPortReadPortUlong routine reads a value from a specified port address.
ms.assetid: 'b04ef64a-cf1f-4de5-acb3-e57687f64719'
keywords: ["StorPortReadPortUlong routine Storage Devices"]
topic_type:
- apiref
api_name:
- StorPortReadPortUlong
api_location:
- Storport.lib
- Storport.dll
api_type:
- LibDef
---

# StorPortReadPortUlong routine

The **StorPortReadPortUlong** routine reads a value from a specified port address.

## Syntax


```C++
STORPORT_API ULONG StorPortReadPortUlong(
  _In_�PVOID �HwDeviceExtension,
  _In_�PULONG Port
);
```



## Parameters

<dl> <dt>

*HwDeviceExtension* \[in\]
</dt> <dd>

Pointer to the hardware device extension.

</dd> <dt>

*Port* \[in\]
</dt> <dd>

Pointer to the address from which to read.

</dd> </dl>

## Return value

**StorPortReadPortUlong** returns a data item of length **sizeof**(ULONG).

## Remarks

For more information, see the [**ScsiPortReadPortUlong**](scsiportreadportulong.md) routine. For a buffered version of this routine see [**StorPortReadPortBufferUlong**](storportreadportbufferulong.md).

## Requirements



|                            |                                                                                                                                         |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>[Universal](http://go.microsoft.com/fwlink/p/?linkid=531356)</dt> </dl> |
| Header<br/>          | <dl> <dt>Storport.h (include Storport.h)</dt> </dl>                              |
| Library<br/>         | <dl> <dt>Storport.lib</dt> </dl>                                                 |



## See also

<dl> <dt>

[**ScsiPortReadPortBufferUlong**](scsiportreadportbufferulong.md)
</dt> <dt>

[**StorPortReadPortUlong**](storportreadportulong.md)
</dt> </dl>

�

�

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20StorPortReadPortUlong%20routine%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





