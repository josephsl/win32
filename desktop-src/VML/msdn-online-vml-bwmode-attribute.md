---
title: VML BWMode Attribute
description: VML BWMode Attribute
ms.assetid: '929daebb-c402-46a0-9abc-b91c4ebda7fa'
---

# VML BWMode Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Determines how a shape will render for black-and-white output devices. Read/write. [VgBlackWhiteMode](msdn-online-vml-vgblackwhitemode.md).

**Applies To**

[Shape](shape-element--vml.md)

**Tag Syntax**

&lt;v: *element* o:bwmode=" *expression* "&gt;

**Remarks**

When a shape is printed on a black-and-white printer or displayed in a black-and-white view in an application, several options are possible. For more information about the values of this attribute, see the [VgBlackWhiteMode](msdn-online-vml-vgblackwhitemode.md) topic. The default value is **auto**.

If **auto** is specified, [BWNormal](msdn-online-vml-bwnormal-attribute.md) is used to determine the behavior for normal black-and-white output, and [BWPure](msdn-online-vml-bwpure-attribute.md) is used to determine the behavior for pure black-and-white output.

*Microsoft Office Extensions Attribute*

**Example**

The black-and-white mode of the shape is **auto**.


```HTML
   <v:rect id="myrect" fillcolor="red" o:bwmode="auto"
     style="top:1;left:1;width:20;height:20"/>
```



 

 



