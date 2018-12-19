﻿---
title: TaskStatus.PercentComplete Property  (Microsoft.Web.Media.TransformManager)
TOCTitle: PercentComplete Property
ms:assetid: P:Microsoft.Web.Media.TransformManager.TaskStatus.PercentComplete
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.taskstatus.percentcomplete(v=VS.90)
ms:contentKeyID: 35520698
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.TaskStatus.get_PercentComplete
- Microsoft.Web.Media.TransformManager.TaskStatus.PercentComplete
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.Common.dll
api_name:
- Microsoft.Web.Media.TransformManager.TaskStatus.get_PercentComplete
- Microsoft.Web.Media.TransformManager.TaskStatus.PercentComplete
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# PercentComplete Property

Gets the percentage of task completion.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.Common (in Microsoft.Web.Media.TransformManager.Common.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyPercentCompleteAsIntegerGet
'Usage
DiminstanceAsTaskStatusDimvalueAsIntegervalue = instance.PercentComplete
```

``` csharp
publicintPercentComplete { get; }
```

``` c++
public:
virtualpropertyintPercentComplete {
    intget () sealed;
}
```

``` fsharp
abstractPercentComplete : intoverridePercentComplete : int
```

``` jscript
finalfunction getPercentComplete () : int
```

#### Property Value

Type: [System. . :: . .Int32](https://msdn.microsoft.com/en-us/library/td2s409d\(v=vs.90\))  
The percentage completed.  

#### Implements

[ITaskStatus. . :: . .PercentComplete](itaskstatus-percentcomplete-property-microsoft-web-media-transformmanager.md)  

## Remarks

The percentage can be used to report progress to the UI.

## See Also

#### Reference

[TaskStatus Class](taskstatus-class-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
