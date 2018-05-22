---
Description: 'The CAMEvent class is a wrapper for manual-reset and auto-reset events.'
ms.assetid: '228b4e51-afc5-4cb6-b225-309013713983'
title: CAMEvent class
---

# CAMEvent class

![camevent class hierarchy](images/util06.png)

The **CAMEvent** class is a wrapper for manual-reset and auto-reset events.

This class provides a convenient way to manage events, rather than calling functions such as [**CreateEvent**](https://msdn.microsoft.com/library/windows/desktop/ms682396), [**WaitForSingleObject**](https://msdn.microsoft.com/library/windows/desktop/ms687032), and [**ResetEvent**](https://msdn.microsoft.com/library/windows/desktop/ms685081).



| Protected Member Variables                          | Description                                                     |
|-----------------------------------------------------|-----------------------------------------------------------------|
| [**m\_hEvent**](camevent-m-hevent.md)              | Event handle.                                                   |
| Public Methods                                      | Description                                                     |
| [**CAMEvent**](camevent-camevent.md)               | Constructor method.                                             |
| [**~CAMEvent**](camevent--camevent.md)             | Destructor method.                                              |
| [**Check**](camevent-check.md)                     | Checks whether the event is set, without blocking.              |
| [**Reset**](camevent-reset.md)                     | Sets the state of the event to nonsignaled.                     |
| [**Set**](camevent-set.md)                         | Signals the event.                                              |
| [**Wait**](camevent-wait.md)                       | Blocks until the event is signaled, or until a time-out occurs. |
| Operators                                           | Description                                                     |
| [**operator HANDLE**](camevent-operator-handle.md) | Retrieves the event handle.                                     |



�

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Wxutil.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



�

�



