---
title: "OpenWindow Method"
ms.custom: na
ms.date: 09/22/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 1f26922f-f83c-4065-a195-70cd3619b39c
caps.latest.revision: 0
manager: edupont
---

# OpenWindow Method
This method is used to open a new browser window which navigates to the specified URL. The benefit of using this function instead of using the native browser function, is that this function also works when using the control add-in in an app, for example on a phone. If you are using the native browser function in an app the behavior varies between the different platforms (Windows, iOS, Android).

## Method Signature  
 `void Microsoft.Dynamics.NAV.OpenWindow(url)`  
  
## Parameters  
  
|Parameter|Description|  
|---------|-----------|  
|url      |Type: String <br /><br /> A string that contains the URL for the new browser window to navigate to.|  
  
  
## See Also  
 [Extending Any Microsoft Dynamics NAV Client Using Control Add-ins](Extending-Any-Microsoft-Dynamics-NAV-Client-Using-Control-Add-ins.md)   
 [InvokeExtensibilityMethod Method](InvokeExtensibilityMethod-Method.md)   
 [GetImageResource Method](GetImageResource-Method.md)   
 [GetEnvironment Method](GetEnvironment-Method.md)  
 [Asynchronous Considerations](Asynchronous-Considerations.md)