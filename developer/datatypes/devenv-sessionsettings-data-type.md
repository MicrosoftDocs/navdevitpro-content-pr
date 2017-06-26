---
title: "SessionSettings Data Type"
ms.custom: na
ms.date: 06/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 2b9d7dad-f05c-4f93-a167-8a9fa036ed28
caps.latest.revision: 2
author: SusanneWindfeldPedersen
---
# SessionSettings Data Type
The SessionSettings data type is a complex data type for passing user personalization settings for a client session as an object. The object can properties that correspond to the fields in the system table **2000000073 User Personalization**, including: App ID, Company, Language ID, Locale ID, Profile ID, Scope, and Time Zone.

Using the AL methods of the SessionSettings data type, you can set the user personalization settings for the current client session. The data type and its methods were specifically designed for managing the My Settings page in the web client.  For example, the SessionSettings data type and methods are used on the .

This data type is not supported in extensions.

Any SessionSettings methods that are called in an OData or SOAP web service call are ignored.

## Methods
The following methods are supported for the SessionSettings data type:

[REQUESTSESSIONUPDATE method](../methods/devenv-requestsessionupdate-method.md)   
[INIT method](../methods/devenv-init-method.md)   



## See Also  
[AL Data Types](devenv-al-data-types.md)  