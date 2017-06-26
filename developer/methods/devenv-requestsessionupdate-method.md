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
Passes a SessionSettings object to the client to request a new session that uses the user personalization properties in the object. The current client session is abandoned and a new session is started.  

## Syntax  

```  
SessionSettings.REQUESTSESSIONUPDATE(SaveSettings)  
```  

#### Parameters  
 *SaveSettings*  
 Type: Boolean  

Specifies whether to save the personalization properties in the SessionSettings to the table **2000000073 User Personalization** in the database for the current client user. **true** saves the settings; **false** does not.

If you set this parameter to **true**, before sending the request to the client, the server instance will store the property values of the SessionSettings object to the corresponding fields in the table **2000000073 User Personalization**

If you set this to **false**, when the new client session is closed, the next time the user signs in, the session will return to the previous personalization settings. This enable you to use the SessionSettings object to temporarily change the personalization settings for the current session.

## Remarks  
Within the scope of the REQUESTSESSIONUPDATE method, it is not recommended to run code after the REQUESTSESSIONUPDATE method call that requires client communication  because the current client session will be abandoned.

Before the REQUESTSESSIONUPDATE method is called, be sure that all the personalization properties in the SessionSettings object have values; otherwise this can result in unwanted. For You can use the INIT method to populate the object with the values in the database.

If this method is called in an OData or SOAP web service call, it is ignored.

## Example  
This example uses the INIT method to create a SessionSettings object that includes the current client user's personalization settings from the database, and then uses the COMPANY method to set the company to 'MyCompany'. Finally, the REQUESTSESSIONUPDATE method sends a request to the client to abandon the current client session and start a new session that uses the personalization settings in the SessionSettings object, including the new company.

```
var
  MySessionSettings : SessionSettings;
  begin
    MySessionSettings.INIT
    MySessionSettings.COMPANY('MyCompany');
    MySessionSettings.REQUESTSESSIONUPDATE(true);
  end;  
```  


## See Also  
[INIT method](devenv-init-method.md)  
