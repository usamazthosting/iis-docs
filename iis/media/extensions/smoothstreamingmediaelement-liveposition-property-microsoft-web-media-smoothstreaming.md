﻿---
title: SmoothStreamingMediaElement.LivePosition Property  (Microsoft.Web.Media.SmoothStreaming)
TOCTitle: LivePosition Property
ms:assetid: P:Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePosition
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.smoothstreaming.smoothstreamingmediaelement.liveposition(v=VS.90)
ms:contentKeyID: 23961093
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_LivePosition
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Media.SmoothStreaming.dll
api_name:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_LivePosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePosition
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# LivePosition Property

Gets the position that is nearest to the live stream that a client can seek to.

**Namespace:**  [Microsoft.Web.Media.SmoothStreaming](microsoft-web-media-smoothstreaming-namespace_1.md)  
**Assembly:**  Microsoft.Web.Media.SmoothStreaming (in Microsoft.Web.Media.SmoothStreaming.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyLivePositionAsDouble
'Usage
DiminstanceAsSmoothStreamingMediaElementDimvalueAsDoublevalue = instance.LivePosition
```

``` csharp
publicdoubleLivePosition { get; }
```

``` c++
public:
propertydoubleLivePosition {
    doubleget ();
}
```

``` jscript
function getLivePosition () : double
```

#### Property Value

Type: [System. . :: . .Double](https://msdn.microsoft.com/en-us/library/643eft0t\(v=vs.90\))  
The position.  

## Version Information

#### Silverlight

Supported in: 4  

#### Silverlight for Windows Phone

Supported in: Windows Phone OS 7.0  

## Permissions

  - Full trust for the immediate caller. This member cannot be used by partially trusted code. For more information, see [Using Libraries from Partially Trusted Code](https://msdn.microsoft.com/en-us/library/8skskf63\(v=vs.90\)).

## See Also

#### Reference

[SmoothStreamingMediaElement Class](smoothstreamingmediaelement-class-microsoft-web-media-smoothstreaming_1.md)

[Microsoft.Web.Media.SmoothStreaming Namespace](microsoft-web-media-smoothstreaming-namespace_1.md)
