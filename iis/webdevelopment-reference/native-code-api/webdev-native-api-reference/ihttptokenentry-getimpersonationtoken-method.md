---
title: "IHttpTokenEntry::GetImpersonationToken Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c02033ef-5f32-4c95-4a15-b19c885741c9
caps.latest.revision: 31
author: "shirhatti"
manager: "wpickett"
---
# IHttpTokenEntry::GetImpersonationToken Method
Returns the impersonation token for a user.  
  
## Syntax  
  
```cpp  
virtual HANDLE GetImpersonationToken(  
   VOID  
) = 0;  
```  
  
#### Parameters  
 This method takes no parameters.  
  
## Return Value  
 A `HANDLE` that represents the impersonation token for a user. May be NULL.  
  
## Remarks  
 An impersonation token is a handle that defines the security context of the user that is making a request. This token allows the server to impersonate a user during a request so that access to system resources is based upon the access rules for that user.  
  
 During impersonation, both the primary token returned from the [GetPrimaryToken](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpuser-getprimarytoken-method.md) method and the impersonation token returned from the `GetImpersonationToken` method are used. This may either expand or contract the user privileges based upon security rules for that user.  
  
 [CGlobalModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/cglobalmodule-class.md) derived classes that register for [GL_CACHE_OPERATION](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) events receive an [ICacheProvider](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icacheprovider-interface.md) pointer as a parameter on the [CGlobalModule::OnGlobalCacheOperation](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/cglobalmodule-onglobalcacheoperation-method.md)`virtual` method. You can retrieve an [IHttpCacheSpecificData](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcachespecificdata-interface.md) pointer by calling the [ICacheProvider::GetCacheRecord](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icacheprovider-getcacherecord-method.md) method and, in some cases, you can downcast this `IHttpCacheSpecificData` pointer to an [IHttpTokenEntry](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttptokenentry-interface.md) pointer. You can then retrieve the impersonation token handle by calling the `GetImpersonationToken` method.  
  
 For more information on downcast rules, see [ICacheProvider::GetCacheRecord](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icacheprovider-getcacherecord-method.md).  
  
## Notes for Implementers  
 `IHttpTokenEntry` implementers are responsible for resource management with this data; therefore, `IHttpTokenEntry` implementers must call the [CloseHandle](http://go.microsoft.com/fwlink/?LinkId=60019) function on the handle when it is no longer needed.  
  
## Notes for Callers  
 `IHttpTokenEntry` implementers are responsible for resource management with this data; therefore, `IHttpTokenEntry` clients must not call `CloseHandle` on the returned handle when this data is no longer needed. Furthermore, clients must not change the state of the memory that this handle references, because an access violation will be thrown or the data will become invalid.  
  
## Example  
 The following code example demonstrates how to create a global module that listens for `GL_CACHE_OPERATION` and [GL_CACHE_CLEANUP](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) events and then writes the `IHttpTokenEntry` information to the Event Viewer.  
  
> [!CAUTION]
>  [!INCLUDE[iisver](../../../wmi-provider/includes/iisver-md.md)] generates a large number of events in the Event Viewer. To avoid a log overflow error in a production environment, you should generally avoid writing cache information to the event log. For demonstration purposes, this code example writes an entry to the Event Viewer in debug mode only.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpTokenEntry#2](IHttpTokenEntry#2)]  -->  
  
 The above code writes a new event to the Event Viewer, where the Data box contains a string similar to the following.  
  
```  
IHttpTokenEntry::GetImpersonationToken: valid  
```  
  
 Your module must export the [RegisterModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/pfn-registermodule-function.md) function. You can export this function by creating a module definition (.def) file for your project, or you can compile the module by using the `/EXPORT:RegisterModule` switch. For more information, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 You can optionally compile the code by using the `__stdcall (/Gz)` calling convention instead of explicitly declaring the calling convention for each function.  
  
## Requirements  
  
|Type|Description|  
|----------|-----------------|  
|Client|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winvista](../../../wmi-provider/includes/winvista-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[win7](../../../wmi-provider/includes/win7-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[win8](../../../wmi-provider/includes/win8-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[win10](../../../wmi-provider/includes/win10-md.md)]|  
|Server|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winsrv2008](../../../wmi-provider/includes/winsrv2008-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[winsrv2008r2](../../../wmi-provider/includes/winsrv2008r2-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[winsrv2012](../../../wmi-provider/includes/winsrv2012-md.md)]<br />-   [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)] on [!INCLUDE[winsrv2012r2](../../../wmi-provider/includes/winsrv2012r2-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[winsrv2016](../../../wmi-provider/includes/winsrv2016-md.md)]|  
|Product|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)], [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)], [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)], [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)], [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)]<br />-   [!INCLUDE[iisexp75](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp75-md.md)], [!INCLUDE[iisexp80](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp80-md.md)], [!INCLUDE[iisexp100](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp100-md.md)]|  
|Header|Httpserv.h|  
  
## See Also  
 [IHttpTokenEntry Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttptokenentry-interface.md)   
 [IHttpTokenEntry::GetPrimaryToken Method](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttptokenentry-getprimarytoken-method.md)   
 [IHttpTokenEntry::GetSid Method](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttptokenentry-getsid-method.md)