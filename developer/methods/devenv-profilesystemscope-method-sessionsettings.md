---
title: "PROFILESYSTEMSCOPE Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# PROFILESYSTEMSCOPE Method
Gets or sets the profile scope in a SessionSettings object.  

## Syntax  

```  
[CurrProfileScope :=] SessionSettings.PROFILESCOPE([NewProfileScope])  
```  

#### Parameters  
*NewProfileScope*  
Type: Boolean  

Specifies whether the profile applies to the system or to a specific tenant database only. **true** sets the profile to apply to the system; **false** sets the profile to apply to a tenant database only.

## Return Value  
Type: Boolean  

**true** if the profile applies to the system; **false** if the profile applies to a tenant database only.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data, and then uses the PROFILESYSTEMSCOPE method to set the extension profile with the ID 'MyExtensionProfile' and extension ID '12345678-1234-1234-1234-1234567890AB' to apply to the tenant database only. Finally, the REQUESTSESSIONUPDATE method sends a request to the client to abandon the current client session and start a new session that uses the new profile ID. This example requires a SessionSettings data type variable.

var
  MySessionSettings : SessionSettings;
  begin
    MySessionSettings.INIT
    MySessionSettings.PROFILEAPPID('MyExtensionProfile');
    MySessionSettings.PROFILESYSTEMSCOPE('12345678-1234-1234-1234-1234567890AB');
    MySessionSettings.REQUESTSESSIONUPDATE(false);
  end;  
```  

## See Also  
[REQUESTSESSIONUPDATE method](devenv-requestsessionupdate-method.md)  
