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
Gets or sets the language ID property in a SessionSettings object.  

## Syntax  

```  
[CurrLanguageId :=] SessionSettings.LANGUAGEID([NewLanguageId])  
```  

#### Parameters  
*NewLanguageId*  
Type: Integer  

Specifies the language ID to set in the SessionSettings object. The value must be a valid Windows language ID, wich is typically a 4-digit value such as 1033 for English or 1030 for Danish; otherwise 1033 will be used.

## Return Value  
Type: Integer  

The langauge ID that is set in the SessionSettings object.  

## Remarks  
The langauge ID in the SessionSettings object corresponds to the Locale ID field in system table **2000000073 User Personalization** for the client session user.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data, and then uses the LANGUAGEID method to change the language ID to '1030'. Finally, the REQUESTSESSIONUPDATE method sends a request to the client to abandon the current client session and start a new session that uses the new language. This example requires a SessionSettings data type variable.

```
var
  MySessionSettings : SessionSettings;
  begin
    MySessionSettings.INIT
    MySessionSettings.LANGUAGE(1030);
    MySessionSettings.REQUESTSESSIONUPDATE(false);
  end;  
```  

## See Also  
[REQUESTSESSIONUPDATE method](devenv-requestsessionupdate-method.md)  
