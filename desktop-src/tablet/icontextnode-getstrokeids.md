---
Description: 'Retrieves an array of identifiers for the strokes within the IContextNode object.'
ms.assetid: '2420afec-6859-449b-92d8-0f4327281852'
title: 'IContextNode::GetStrokeIds method'
---

# IContextNode::GetStrokeIds method

Retrieves an array of identifiers for the strokes within the [**IContextNode**](icontextnode.md) object.

## Syntax


```C++
HRESULT GetStrokeIds(
  [in, out]�ULONG *pulStrokeIdsCount,
  [out]�����LONG �**pplStrokes
);
```



## Parameters

<dl> <dt>

*pulStrokeIdsCount* \[in, out\]
</dt> <dd>

The number of strokes. The value that is passed in is not used.

</dd> <dt>

*pplStrokes* \[out\]
</dt> <dd>

A pointer to the array of stroke identifiers for this [**IContextNode**](icontextnode.md) object.

</dd> </dl>

## Return value

For a description of the return values, see [Classes and Interfaces - Ink Analysis](classes-and-interfaces---ink-analysis.md).

## Remarks

> \[!Caution\]  
> To avoid a memory leak, use [**CoTaskMemFree**](https://msdn.microsoft.com/library/windows/desktop/ms680722) to release the memory from \**pplStrokes* when you no longer need the information.

�

## Requirements



|                                     |                                                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP Tablet PC Edition \[desktop apps only\]<br/>                                                 |
| Minimum supported server<br/> | None supported<br/>                                                                                     |
| Header<br/>                   | <dl> <dt>IACom.h (also requires IACom\_i.c)</dt> </dl> |
| DLL<br/>                      | <dl> <dt>IACom.dll</dt> </dl>                          |



## See also

<dl> <dt>

[**IContextNode**](icontextnode.md)
</dt> <dt>

[**IContextNode::GetStrokeId**](icontextnode-getstrokeid.md)
</dt> <dt>

[**IContextNode::GetStrokeCount**](icontextnode-getstrokecount.md)
</dt> <dt>

[Ink Analysis Reference](ink-analysis-reference.md)
</dt> </dl>

�

�



