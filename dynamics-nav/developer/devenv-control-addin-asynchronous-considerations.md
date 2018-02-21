---
title: "Asynchronous Considerations for Control Add-ins"
ms.custom: na
ms.date: 10/04/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6c90376e-b86e-406d-880d-3cc905bf6527
author: SusanneWindfeldPedersen
---

# Asynchronous Considerations
When writing control add-ins that work on all display targets, you have to consider some limitations regarding asynchronous communication. The limitations come from the nature of the asynchronous communication between the clients and the [!INCLUDE[nav_server](includes/nav_server_md.md)]. All calls between the AL code running on the [!INCLUDE[nav_server](includes/nav_server_md.md)] and the script method running in the Web browser are asynchronous. This means that methods in the control add-in interface must be of type void and property methods should not be used.  
  
+ To transfer a result from an AL trigger to the calling script method, just add a method to the control add-in interface that the AL trigger can invoke to send the result to the script.  
  
+ To transfer a result from a script method to an AL trigger, just add an event to the control add-in interface that the script method can use to invoke a AL trigger that receives the result.  
  
## See Also  
[InvokeExtensibilityMethod Method](methods/devenv-invokeextensibility-method.md)   
[GetImageResource Method](methods/devenv-getimageresource-method.md)