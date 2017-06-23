---
title: "LANGUAGEID Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# LANGUAGEID Method
Gets or sets the company in a SessionSettings object.  

## Syntax  

```  
[CurrLanguageId :=] SessionSettings.LANGUAGEID([NewLanguageId])  
```  

#### Parameters  
*NewLanguageId*  
Type: Integer  

Specifies the langaue ID to set in the SessionSettings object.  

## Return Value  
Type: Integer  

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
