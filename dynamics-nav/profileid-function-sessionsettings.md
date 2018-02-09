---
title: "PROFILEID Function (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
author: jswymer
---
# PROFILEID Function
Gets or sets the profile ID property in a SessionSettings object.  

## Syntax  

```  
[CurrProfileId :=] SessionSettings.PROFILEID([NewProfileId])  
```  

#### Parameters  
*NewProfileId*  
Type: Integer  

Specifies the ID of the profile to set in the SessionSettings object. The value must be a valid profile ID in the system table **2000000072 Profile**.

## Return Value  
Type: Text  

The profile ID that is set in the SessionSettings object.  

## Remarks  
The profile ID determines the Role Center that is used in the client session. The PROFILEID property in a SessionSettings object corresponds to the **Profile ID** field in the in the system table **2000000073 User Personalization**.

## Example
This example creates a SessionSettings object that is populated with the current client user's personalization data, and uses the changes the PROFILE function to set  the profile to 'Business Manager'. Finally, the REQUESTSESSIONUPDATE function sends a request to the client to abandon the current session and start a new session that uses the new profile ID. This example requires a SessionSettings data type variable.

The code requires that you create the following C/AL variable.  

|Variable|DataType|  
|--------------|--------------|  
|MySessionSettings|SessionSettings|  

```
    MySessionSettings.INIT;
    MySessionSettings.PROFILEID('Business Manager');
    MySessionSettings.REQUESTSESSIONUPDATE(false);
```  

## See Also  
[INIT Function](init-function-sessionsettings.md)  
[REQUESTSESSIONUPDATE Function](requestsessionupdate-function-sessionsettings.md)  
[SessionSettings Data Type](sessionsettings-data-type.md)    
