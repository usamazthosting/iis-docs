---
title: "IHttpContext::NotifyCustomNotification Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7ed6a0f-5a56-2420-5c1d-16364a5bda73
caps.latest.revision: 19
author: "shirhatti"
manager: "wpickett"
---
# IHttpContext::NotifyCustomNotification Method
Raises a custom request-level notification.  
  
## Syntax  
  
```cpp  
virtual HRESULT NotifyCustomNotification(  
   ICustomNotificationProvider* pCustomOutput,  
   BOOL* pfCompletionExpected  
) = 0;  
```  
  
#### Parameters  
 `pCustomOutput`  
 A pointer to an [ICustomNotificationProvider](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icustomnotificationprovider-interface.md).  
  
 `pfCompletionExpected`  
 `true` if asynchronous completion is expected; otherwise, `false`.  
  
## Return Value  
 An `HRESULT`. Possible values include, but are not limited to, those in the following table.  
  
|Value|Description|  
|-----------|-----------------|  
|S_OK|Indicates that the operation was successful.|  
|ERROR_NOT_ENOUGH_MEMORY|Indicates that there is insufficient memory to perform the operation.|  
  
## Remarks  
 The `NotifyCustomNotification` method raises the custom notification that is specified by the `ICustomNotificationProvider` interface in the `pCustomOutput` parameter.  
  
 Your module must register for the [RQ_CUSTOM_NOTIFICATION](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) notification, and your module must contain a [CHttpModule::OnCustomRequestNotification](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-oncustomrequestnotification-method.md) method to process the custom notification. To raise the custom notification, your module must first create the instance of your custom `ICustomNotificationProvider` interface and pass that interface to the `NotifyCustomNotification` method for the current request context.  
  
## Example  
 The following code example demonstrates how to create an HTTP module that performs the following tasks:  
  
1.  Registers for the [RQ_BEGIN_REQUEST](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) and `RQ_CUSTOM_NOTIFICATION` notifications.  
  
2.  Creates a [CHttpModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-class.md) class that contains [OnBeginRequest](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-onbeginrequest-method.md) and [OnCustomRequestNotification](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-oncustomrequestnotification-method.md) methods.  
  
    1.  The `OnBeginRequest` method writes to the Event Viewer an event that specifies the current notification. The method then creates an instance of an `ICustomNotificationProvider` interface and raises the custom notification by using the `NotifyCustomNotification` method.  
  
    2.  The `OnCustomRequestNotification` method uses the [ICustomNotificationProvider::QueryNotificationType](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icustomnotificationprovider-querynotificationtype-method.md) method to retrieve the unique identifier for the custom notification. If the unique identifier matches, the `OnCustomRequestNotification` method writes to the Event Viewer an event that specifies that the custom notification was raised.  
  
3.  Removes the `CHttpModule` class from memory and then exits.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpContextNotifyCustomNotification#1](IHttpContextNotifyCustomNotification#1)]  -->  
  
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
 [ICustomNotificationProvider Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/icustomnotificationprovider-interface.md)   
 [IHttpContext Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-interface.md)   
 [IHttpServer::NotifyCustomNotification Method](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpserver-notifycustomnotification-method.md)