---
title: "PROFILEAPPID Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# PROFILEAPPID Method
Gets or sets the extension profile ID proerty in a SessionSettings object.  

## Syntax  

```  
[CurrProfileAppId :=] SessionSettings.PROFILEAPPID([NewProfileAppId])  
```  

#### Parameters  
*NewProfileAppId*  
Type: GUID  

Sets the GUID of the profile that is provided by an extension. The value must be a valid GUID for an extension in the system table **2000000072 Profile**.

## Return Value  
Type: GUID  

The ID that is set for the extension profile in the SessionSettings object.  

## Remarks
A profile can be included as part of an extension, instead of being defined as part of the base application. In order to identify the profile, you must specify the ID of the profile and extension itself.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data and uses the PROFILEAPPID method to set the extension profile that has the ID 'MyExtensionProfile' and the extension ID '12345678-1234-1234-1234-1234567890AB'. Then, it sends a request to the client to abandon the current client session and start a new session that uses the new profile ID. This example requires a SessionSettings data type variable.

```
var
  MySessionSettings : SessionSettings;
  begin
    MySessionSettings.INIT
    MySessionSettings.PROFILEID('MyExtensionProfile');
    MySessionSettings.PROFILEAPPID('12345678-1234-1234-1234-1234567890AB');
    MySessionSettings.REQUESTSESSIONUPDATE(false);
  end;  
```  

## See Also  
[REQUESTSESSIONUPDATE method](devenv-requestsessionupdate-method.md)  
