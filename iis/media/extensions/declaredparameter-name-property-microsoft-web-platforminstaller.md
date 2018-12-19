﻿---
title: DeclaredParameter.Name Property  (Microsoft.Web.PlatformInstaller)
TOCTitle: Name Property
ms:assetid: P:Microsoft.Web.PlatformInstaller.DeclaredParameter.Name
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.platforminstaller.declaredparameter.name(v=VS.90)
ms:contentKeyID: 22049550
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.PlatformInstaller.DeclaredParameter.Name
- Microsoft.Web.PlatformInstaller.DeclaredParameter.get_Name
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.PlatformInstaller.dll
api_name:
- Microsoft.Web.PlatformInstaller.DeclaredParameter.get_Name
- Microsoft.Web.PlatformInstaller.DeclaredParameter.Name
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# Name Property

Gets the name of the parameter.

**Namespace:**  [Microsoft.Web.PlatformInstaller](microsoft-web-platforminstaller-namespace.md)  
**Assembly:**  Microsoft.Web.PlatformInstaller (in Microsoft.Web.PlatformInstaller.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyNameAsStringGet
'Usage
DiminstanceAsDeclaredParameterDimvalueAsStringvalue = instance.Name
```

``` csharp
publicstringName { get; }
```

``` c++
public:
propertyString^ Name {
    String^ get ();
}
```

``` jscript
function getName () : String
```

#### Property Value

Type: String  
A string that represents the name of the parameter.  

## Permissions

  - Full trust for the immediate caller. This member cannot be used by partially trusted code. For more information, see <https://msdn.microsoft.com/en-us/library/8skskf63(v=vs.90)>.

## See Also

#### Reference

[DeclaredParameter Class](declaredparameter-class-microsoft-web-platforminstaller.md)

[DeclaredParameter Members](declaredparameter-members-microsoft-web-platforminstaller.md)

[Microsoft.Web.PlatformInstaller Namespace](microsoft-web-platforminstaller-namespace.md)
