---
title: "REQUESTSESSIONUPDATE Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# REQUESTSESSIONUPDATE Method
Passes a SessionSettings object to the client to request a new session that uses the user personalization properties in the object. The current client sessesion is terminated and a new session is started with the personalization settings in the    This method passes the object it is called on to the client, along with the boolean. Before it does that, if the boolean is true, it stores all the contents of the object to the database. This means we will assume all fields to be set, and throw if something does not validate.  

Create new complex type SessionSettings to pass around the session settings to be used. This type contains the properties shown on the My Settings page which can be edited by the user: the profile, company, work date, locale, language and time zone.

The type should not be extendable in extensions.

Any functions related to session refresh will be functions on this object. It will have a function REQUESTSESSIONUPDATE, which takes a non optional boolean parameter SaveSettings, determining whether the changes should be saved to the database or only applied to the 'refreshed' session.

It has a function INIT which fills the property bag with the data currently in the database.

If the methods are called in an OData/SOAP call, they should be ignored.

## Syntax  

```  
SessionSettings.REQUESTSESSIONUPDATE(SaveSettings)  
```  

#### Parameters  
 *SaveSettings*  
 Type: Boolean  

 Specifies whether to save the personalization settings in the table **2000000073 User Personalization** in the database. **true** saves the settings; **false** does not. If you set this to **false**, when the new client session is closed, the next time the user signs in, the session will return to the previous personalization settings.

## Remarks  
If this method is called in an OData or SOAP web service call, it is ignored.

It is not recommended to have code after this call because if there is client communication the session has been abandoned.

## Example  
 This example shows how to remove the sign from a negative numeric value. This example requires that you create the following variables and text constant.  

|Variable name|DataType|  
|-------------------|--------------|  
|x|Decimal|  
|y|Decimal|  

|Text constant name|ENU Value|  
|------------------------|---------------|  
|Text000|x = %1, y = %2|  

```  
x := -10.235; // x is assigned a negative value  
y := ABS(x); // y is assigned the value of x without sign  
MESSAGE(Text000, x, y);  
```  

 The message window displays the following:  

 **x = -10.235, y = 10.235**  

## See Also  
[INIT method](devenv-init-method.md)  
