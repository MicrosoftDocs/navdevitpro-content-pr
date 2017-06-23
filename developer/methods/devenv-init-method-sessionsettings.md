---
title: "INIT Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# INIT Method
Creates an instance of a SessionsSettings object that is populated with the client user's personalization settings (such as Profile ID and Company) that are currently stored in the database.

## Syntax  

```  
SessionSettings.INIT
```  

## Remarks  
The method gets the data from the following fields in system table **2000000073 User Personalization**: App ID, Company, Language ID, Locale ID, Profile ID, Scope, and Time Zone.

After you call the INIT method, you can change the values in the object by using the SessionSettings methods that correspond to the fields in the User Personalization table.


## Example  
This example uses the INIT method to get the current client user's personalization settings, change the company, and then send the request to the client to start a new session that uses the new settings.

```  
  MySessionSettings.INIT
  MySessionSettings.COMPANY('CRONUS International Ltd.');
  MySessionSettings.REQUESTSESSIONUPDATE(true);  
```  

This example requires the following SessionSettings data type variable.
```
var
  MySessionSettings : SessionSettings;
```  

## See Also  
[REQUESTSESSIONUPDATE method](devenv-requestsessionupdate-method.md)  
