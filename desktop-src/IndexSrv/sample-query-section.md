---
title: Sample Query Section
description: Sample Query Section
ms.assetid: 'cadd3d59-f9f3-4fb1-849b-ff4f5b223e2f'
---

# Sample Query Section

> [!Note]  
> Indexing Service is no longer supported as of Windows XP and is unavailable for use as of Windows 8. Instead, use [Windows Search](https://msdn.microsoft.com/library/windows/desktop/aa965362) for client side search and [Microsoft Search Server Express]( http://go.microsoft.com/fwlink/p/?linkid=258445) for server side search.

 

Begin by writing a \[Query\] tag, and then add a set of parameters. The following example assumes that you have taken these steps:

-   Created a virtual directory called Scripts.
-   Given this directory Script permission.
-   Put Simple.idq and Template.htx into the Scripts directory.

Here is a simple .idq file:

``` syntax
[Query]
CiScope=/
CiColumns=FileName
CiRestriction=#filename *
CiTemplate=/Scripts/Template.htx
```

The preceding four parameters are required. In many cases, one or more parameters will be passed down from a form. Here is a very simple form:

``` syntax
<FORM ACTION="/scripts/simple.idq" METHOD="GET">
Query : <INPUT TYPE="TEXT" NAME="Restriction" SIZE="60" MAXLENGTH="100" VALUE="">
<INPUT TYPE="SUBMIT" VALUE="Execute Query">
</FORM>
```

This form can work with the following .idq file to pass parameters from the user:

``` syntax
[Query]
CiScope=/
CiColumns=FileName
CiRestriction=%Restriction%
CiTemplate=/Scripts/Template.htx
```

The [CiRestriction](variables-in-forms-and-in-idq-files.md#-idxs-cirestriction-var) parameter specifies the query string. In addition to the four required parameters, there are many optional parameters you can add, such as [CiSort](variables-in-forms-and-in-idq-files.md#-idxs-cisort-var) and [CiForceUseCi](variables-in-forms-and-in-idq-files.md#-idxs-ciforceuseci-var). For details, see the full list of parameters in Variables in Forms and in .Idq Files.

 

 



