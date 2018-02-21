---
title: "PROFILESYSTEMSCOPE Function (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
author: jswymer
---
# PROFILESYSTEMSCOPE Function
Gets or sets the profile scope property in a SessionSettings object. 

## Syntax  

```  
[CurrProfileScope :=] SessionSettings.PROFILESCOPE([NewProfileScope])  
```  

#### Parameters  
*NewProfileScope*  
Type: Boolean  

Specifies whether the profile applies to the system or to a tenant only. **true** sets the profile to apply to the system; **false** sets the profile to apply to a tenant only.

## Return Value  
Type: Boolean  

**true** if the profile applies to the system; **false** if the profile applies to a tenant.

## Remarks
The PROFILESYSTEMSCOPE property in a SessionSettings object corresponds to the **Scope** field in the in the system table **2000000073 User Personalization**.

## Example
This example creates a SessionSettings object, and then uses the PROFILESYSTEMSCOPE function to set the profile scope to apply to the system. This example requires a SessionSettings data type variable.

The code requires that you create the following C/AL variable.  

|Variable|DataType|  
|--------------|--------------|  
|MySessionSettings|SessionSettings|  


```
    MySessionSettings.PROFILESYSTEMSCOPE(true);
```

## See Also  
[SessionSettings Data Type](sessionsettings-data-type.md)  
