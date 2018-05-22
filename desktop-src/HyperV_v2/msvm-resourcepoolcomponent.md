---
Description: 'Represents a resource pool element of the Microsoft Windows Hyper-V platform.'
ms.assetid: 'DF48E8A6-240F-44E9-9DA3-1E6694396F10'
title: 'Msvm\_ResourcePoolComponent class'
---

# Msvm\_ResourcePoolComponent class

Represents a resource pool element of the Microsoft Windows Hyper-V platform.

The following syntax is simplified Managed Object Format (MOF) code, and it includes all of the inherited properties.

## Syntax

``` syntax
class Msvm_ResourcePoolComponent : Msvm_VirtualizationComponent
{
  string� CLSID;
  uint32� Context = 1;
  boolean Enabled = True;
  string� Name;
  string� AllocationCapabilitiesClassName;
  string� ResourcePoolClassName;
  string� ResourcePoolSettingDataClassName = "Msvm_ResourcePoolSettingData";
  string� PhysicalDeviceClassName;
  string� WmiFactoryCLSID;
  uint8�� MaxParentPools = 0;
};
```

## Members

The **Msvm\_ResourcePoolComponent** class has these types of members:

-   [Properties](#properties)

### Properties

The **Msvm\_ResourcePoolComponent** class has these properties.

<dl> <dt>

**AllocationCapabilitiesClassName**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The name of the class derived from [**CIM\_AllocationCapabilities**](https://msdn.microsoft.com/library/mt130273) that describes the allocation capabilities of this resource pool.

</dd> <dt>

**CLSID**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

A **GUID** that represents the class identifier of the service's COM object. This property is inherited from [**Msvm\_VirtualizationComponent**](msvm-virtualizationcomponent.md).

</dd> <dt>

**Context**
</dt> <dd> <dl> <dt>

Data type: **uint32**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The context in which the newly created object will run. This value is passed in the *dwClsContext* parameter to **CoCreateInstance**. This property is inherited from [**Msvm\_VirtualizationComponent**](msvm-virtualizationcomponent.md), and it is always set to 1.

</dd> <dt>

**Enabled**
</dt> <dd> <dl> <dt>

Data type: **boolean**
</dt> <dt>

Access type: Read-only
</dt> </dl>

**True** if this instance is enabled and can be used to complete client requests; otherwise, **False**. This property is inherited from [**Msvm\_VirtualizationComponent**](msvm-virtualizationcomponent.md), and it is always set to **True**.

</dd> <dt>

**MaxParentPools**
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The maximum number of parent resource pools that a child pool supports.

</dd> <dt>

**Name**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: **Key**
</dt> </dl>

A language-neutral string that uniquely identifies the element. The following format is suggested to prevent naming conflicts: "vendor\|component\|version". For example, this name represents version 1.0 of the Microsoft Emulated Network Port Component: "Microsoft\|EmulatedNetworkPortComponent\|V1.0". This property is inherited from [**Msvm\_VirtualizationComponent**](msvm-virtualizationcomponent.md).

</dd> <dt>

**PhysicalDeviceClassName**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The name of the class derived from [**CIM\_LogicalDevice**](https://msdn.microsoft.com/library/aa387884) that implements the physical device from which this pool allocates resources. This property can be **Null** if the virtual device class allocated from this pool is the same as the physical device class.

</dd> <dt>

**ResourcePoolClassName**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The name of the class derived from [**CIM\_ResourcePool**](https://msdn.microsoft.com/library/cc136903) that implements the resource pool.

</dd> <dt>

**ResourcePoolSettingDataClassName**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

The name of the class derived from [**CIM\_SettingData**](https://msdn.microsoft.com/library/cc136911) that describes the non-allocation related settings of the resource pool.

</dd> <dt>

**WmiFactoryCLSID**
</dt> <dd> <dl> <dt>

Data type: **string**
</dt> <dt>

Access type: Read-only
</dt> </dl>

A **GUID** that represents the class identifier of the component's WMI object factory.

</dd> </dl>

## Remarks

Access to the **Msvm\_ResourcePoolComponent** class might be restricted by UAC Filtering. For more information, see [User Account Control and WMI](https://msdn.microsoft.com/library/aa826699).

## Requirements



|                                     |                                                                                                         |
|-------------------------------------|---------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�8 \[desktop apps only\]<br/>                                                              |
| Minimum supported server<br/> | Windows Server�2012 \[desktop apps only\]<br/>                                                    |
| End of client support<br/>    | Windows�8.1<br/>                                                                                  |
| End of server support<br/>    | Windows Server�2012�R2<br/>                                                                       |
| Namespace<br/>                | Root\\Virtualization\\V2<br/>                                                                     |
| MOF<br/>                      | <dl> <dt>WindowsVirtualization.V2.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Vmms.exe</dt> </dl>                     |



## See also

<dl> <dt>

[**Msvm\_VirtualizationComponent**](https://msdn.microsoft.com/library/windows/desktop/hh850250)
</dt> <dt>

[**Msvm\_VirtualizationComponent**](msvm-virtualizationcomponent.md)
</dt> </dl>

�

�



