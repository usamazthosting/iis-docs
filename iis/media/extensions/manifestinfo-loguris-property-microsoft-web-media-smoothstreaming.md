﻿---
title: ManifestInfo.LogUris Property  (Microsoft.Web.Media.SmoothStreaming)
TOCTitle: LogUris Property
ms:assetid: P:Microsoft.Web.Media.SmoothStreaming.ManifestInfo.LogUris
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.smoothstreaming.manifestinfo.loguris(v=VS.90)
ms:contentKeyID: 31469301
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.SmoothStreaming.ManifestInfo.get_LogUris
- Microsoft.Web.Media.SmoothStreaming.ManifestInfo.LogUris
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Media.SmoothStreaming.dll
api_name:
- Microsoft.Web.Media.SmoothStreaming.ManifestInfo.get_LogUris
- Microsoft.Web.Media.SmoothStreaming.ManifestInfo.LogUris
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# LogUris Property

Gets the list of logging Uri objects.

**Namespace:**  [Microsoft.Web.Media.SmoothStreaming](microsoft-web-media-smoothstreaming-namespace_1.md)  
**Assembly:**  Microsoft.Web.Media.SmoothStreaming (in Microsoft.Web.Media.SmoothStreaming.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyLogUrisAsIList(OfUri)
'Usage
DiminstanceAsManifestInfoDimvalueAsIList(OfUri)

value = instance.LogUris
```

``` csharp
publicIList<Uri> LogUris { get; }
```

``` c++
public:
propertyIList<Uri^>^ LogUris {
    IList<Uri^>^ get ();
}
```

``` jscript
function getLogUris () : IList<Uri>
```

#### Property Value

Type: [System.Collections.Generic. . :: . .IList](https://msdn.microsoft.com/en-us/library/5y536ey6\(v=vs.90\))\< (Of \< ( \<'[Uri](https://msdn.microsoft.com/en-us/library/txt7706a\(v=vs.90\))\> ) \> ) \>  
An IList of Uri objects.  

## Version Information

#### Silverlight

Supported in: 4  

#### Silverlight for Windows Phone

Supported in: Windows Phone OS 7.0  

## Permissions

  - Full trust for the immediate caller. This member cannot be used by partially trusted code. For more information, see [Using Libraries from Partially Trusted Code](https://msdn.microsoft.com/en-us/library/8skskf63\(v=vs.90\)).

## See Also

#### Reference

[ManifestInfo Class](manifestinfo-class-microsoft-web-media-smoothstreaming_1.md)

[Microsoft.Web.Media.SmoothStreaming Namespace](microsoft-web-media-smoothstreaming-namespace_1.md)
