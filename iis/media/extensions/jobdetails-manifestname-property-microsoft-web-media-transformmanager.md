﻿---
title: JobDetails.ManifestName Property  (Microsoft.Web.Media.TransformManager)
TOCTitle: ManifestName Property
ms:assetid: P:Microsoft.Web.Media.TransformManager.JobDetails.ManifestName
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.jobdetails.manifestname(v=VS.90)
ms:contentKeyID: 35520874
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.JobDetails.get_ManifestName
- Microsoft.Web.Media.TransformManager.JobDetails.set_ManifestName
- Microsoft.Web.Media.TransformManager.JobDetails.ManifestName
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.Common.dll
api_name:
- Microsoft.Web.Media.TransformManager.JobDetails.get_ManifestName
- Microsoft.Web.Media.TransformManager.JobDetails.ManifestName
- Microsoft.Web.Media.TransformManager.JobDetails.set_ManifestName
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# ManifestName Property

Gets or sets the name of the manifest file that defines this job.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.Common (in Microsoft.Web.Media.TransformManager.Common.dll)

## Syntax

``` vb
'Declaration
<DataMemberAttribute> _
PublicPropertyManifestNameAsStringGetSet
'Usage
DiminstanceAsJobDetailsDimvalueAsStringvalue = instance.ManifestName

instance.ManifestName = value
```

``` csharp
[DataMemberAttribute]
publicstringManifestName { get; set; }
```

``` c++
[DataMemberAttribute]
public:
propertyString^ ManifestName {
    String^ get ();
    voidset (String^ value);
}
```

``` fsharp
[<DataMemberAttribute>]
memberManifestName : stringwithget, set
```

``` jscript
function getManifestName () : Stringfunction setManifestName (value : String)
```

#### Property Value

Type: [System. . :: . .String](https://msdn.microsoft.com/en-us/library/s1wwdcbf\(v=vs.90\))  
The name of the manifest file that defines this job.  

## See Also

#### Reference

[JobDetails Class](jobdetails-class-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
