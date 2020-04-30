---
title: "GETLASTERROROBJECT Function"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 8465a42a-a195-4fa4-a431-4e7b3bf00847
caps.latest.revision: 6
manager: edupont
---
# GETLASTERROROBJECT Function
Gets the last [System.Exception](https://go.microsoft.com/fwlink/?LinkID=396510) object that occurred.  
  
## Syntax  
  
```  
  
DotNet := GETLASTERROROBJECT  
```  
  
## Property Value/Return Value  
 Type: DotNet  
  
 A System.Exception object that contains the last exception that occurred.  
  
 If no exception has occurred, then function returns a NULL object.  
  
## Remarks  
 You use this function to retrieve and handle the last exception that occurred in the application. The System.Exception object exposes several members that enable you to get detailed information about the exception, such Exception.InnerException and Exception.Message.  
  
## Example  
 This example uses the GETLASTERROROBJECT function to get an exception object that occurs. In this example, the Microsoft .NET Framework objects are executed by MyCodeunit. The C/AL code uses the InnerException property of the System.Exception object to identify whether the inner exception has the type WebException and returns an exception message accordingly.  
  
 This example requires that you create the following variables.  
  
|Variable name constant|Data Type|SubType|  
|----------------------------|---------------|-------------|  
|MyCodeunt|Codeunit|MyCodeunit|  
|Exception|DotNet|'mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'.System.Exception|  
|WebException|DotNet|'System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'.System.Net.WebException|  
  
```  
IF NOT MyCodeunit.RUN THEN BEGIN  
    Exception := GETLASTERROROBJECT;  
  
    IF NOT Exception.InnerException.GetType.Equals(WebException.GetType) THEN  
        ERROR(Exception.Message);  
  
    WebException := Exception.InnerException;  
    ERROR(WebException.Message);  
END;  
```  
  
## See Also  
 <!-- [Error Handling](Error-Handling.md) -->