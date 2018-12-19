﻿---
title: IManagementService.InitializeService Method  (Microsoft.Web.Media.TransformManager)
TOCTitle: InitializeService Method
ms:assetid: M:Microsoft.Web.Media.TransformManager.IManagementService.InitializeService(Microsoft.Web.Media.TransformManager.Credential)
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.imanagementservice.initializeservice(v=VS.90)
ms:contentKeyID: 35520967
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.IManagementService.InitializeService
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.ServiceLibrary.dll
api_name:
- Microsoft.Web.Media.TransformManager.IManagementService.InitializeService
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# InitializeService Method

Initializes the IIS Transform Manager service using the specified service credential.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.ServiceLibrary (in Microsoft.Web.Media.TransformManager.ServiceLibrary.dll)

## Syntax

``` vb
'Declaration
<OperationContractAttribute> _
FunctionInitializeService ( _
    serviceCredentialAsCredential _
) AsBoolean
'Usage
DiminstanceAsIManagementServiceDimserviceCredentialAsCredentialDimreturnValueAsBooleanreturnValue = instance.InitializeService(serviceCredential)
```

``` csharp
[OperationContractAttribute]
boolInitializeService(
    CredentialserviceCredential
)
```

``` c++
[OperationContractAttribute]
boolInitializeService(
    Credential^ serviceCredential
)
```

``` fsharp
[<OperationContractAttribute>]
abstractInitializeService : 
        serviceCredential:Credential->bool
```

``` jscript
functionInitializeService(
    serviceCredential : Credential
) : boolean
```

#### Parameters

  - serviceCredential  
    Type: [Microsoft.Web.Media.TransformManager. . :: . .Credential](credential-class-microsoft-web-media-transformmanager.md)  
    The [Credential](credential-class-microsoft-web-media-transformmanager.md) object that will allow the service to be run.  

#### Return Value

Type: [System. . :: . .Boolean](https://msdn.microsoft.com/en-us/library/a28wyd50\(v=vs.90\))  
true if initialization succeeds; otherwise, false.  

## See Also

#### Reference

[IManagementService Interface](imanagementservice-interface-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
