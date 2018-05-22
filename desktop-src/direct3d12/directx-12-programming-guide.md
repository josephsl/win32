---
title: Direct3D 12 Programming Guide
description: Direct3D�12 provides an API and platform that allows apps to take advantage of the graphics and computing capabilities of PCs equipped with one or more Direct3D�12-compatible GPUs.
ms.assetid: '16F78A6B-74C4-4ED1-809F-FE6DE157F368'
---

# Direct3D 12 Programming Guide

Direct3D�12 provides an API and platform that allows apps to take advantage of the graphics and computing capabilities of PCs equipped with one or more Direct3D�12-compatible GPUs.

## In this section



| Topic                                                                                                       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [What is Direct3D 12?](what-is-directx-12-.md)<br/>                                                  | DirectX 12 introduces the next version of Direct3D, the 3D graphics API at the heart of DirectX. This version of Direct3D is faster and more efficient than any previous version. Direct3D�12 enables richer scenes, more objects, more complex effects, and full utilization of modern GPU hardware. <br/>                                                                                                                                                                                                                                                                                                          |
| [New Releases](new-releases.md)<br/>                                                                 | Describes the most significant new documentation available with the latest SDK release.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [Understanding Direct3D 12](directx-12-getting-started.md)<br/>                                      | To write 3D games and apps for Windows�10 and Windows�10 Mobile, you must understand the basics of the Direct3D�12 technology, and how to prepare to use it in your games and apps.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [Work Submission in Direct3D 12](command-queues-and-command-lists.md)<br/>                           | To improve the CPU efficiency of Direct3D apps, Direct3D�12 no longer supports an immediate context associated with a device. Instead, apps record and then submit *command lists*, which contain drawing and resource management calls. These command lists can be submitted from multiple threads to one or more command queues, which manage the execution of the commands. This fundamental change increases single-threaded efficiency by allowing apps to pre-compute rendering work for later re-use, and it takes advantage of multi-core systems by spreading rendering work across multiple threads. <br/> |
| [Resource Binding in Direct3D 12](resource-binding.md)<br/>                                          | Binding is the process of linking resource objects to the shaders of the graphics pipeline. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [Memory Management in Direct3D 12](memory-management.md)<br/>                                        | Moving to D3D12 involves doing proper synchronization and management of memory residency. Managing memory residency means even more synchronization must be done. This section covers memory management strategies, and suballocation within heaps and buffers. <br/>                                                                                                                                                                                                                                                                                                                                                |
| [Multi-Engine and Multi-Adapter Synchronization](mulit-engine-and-multi-gpu-synchronization.md)<br/> | Provides an overview and lists APIs relevant to multi-engine (the 3D, compute, and copy engines), and multi-adapter.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| [Rendering](rendering.md)<br/>                                                                       | This section contains information about rendering features new to Direct3D�12 (and Direct3D 11.3).<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| [Counters, Queries and Performance Measurement](performance-measurement.md)<br/>                     | The following sections describe features for use in performance testing and improvement, such as queries, counters, timing, and predication.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [Working with Direct3D 11, Direct3D 10 and Direct2D](direct3d-12-interop.md)<br/>                    | This section covers interop techniques with earlier versions of Direct3D and Direct2D, the Direct3D 11on12 API, and porting guidelines from Direct3D 11 to Direct3D 12.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| [Working Samples](working-samples.md)<br/>                                                           | Working samples are available for download, showing the usage of a number of features of Direct3D 12.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| [D3D12 Code Walk-Throughs](d3d12-code-walk-throughs.md)<br/>                                         | This section provides code for sample scenarios. Many of the walk-throughs provide details on what coding is required to be added to a basic sample, to avoid repeating the basic component code for each scenario.<br/>                                                                                                                                                                                                                                                                                                                                                                                             |
| [Understanding the D3D12 Debug Layer](understanding-the-d3d12-debug-layer.md)<br/>                   | Describes how to make best use of the D3D12 Debug Layer.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |



�

## Related topics

<dl> <dt>

[Direct3D 12 Graphics](direct3d-12-graphics.md)
</dt> <dt>

[Direct3D 12 Reference](direct3d-12-reference.md)
</dt> <dt>

[DirectX advanced learning video tutorials](https://www.youtube.com/channel/UCiaX2B8XiXR70jaN7NK-FpA)
</dt> </dl>

�

�




