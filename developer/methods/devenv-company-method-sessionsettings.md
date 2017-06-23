---
title: "Company Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# COMPANY Method
Gets or sets the company in a SessionSettings object.  

## Syntax  

```  
[CurrCompanyName :=] SessionSettings.COMPANY([NewCompanyName])  
```  

#### Parameters  
*NewCompanyName*  
Type: Text  

Specifies the name of the company in the SessionSettings object.  

## Property Value/Return Value  
Type: Text  

The name of the company that is in the SessionSettings object.  

## Example  This example changes the company that is stored in a SessionsSettings object, and then sends the request to the client to start a new session that uses the new company.

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
