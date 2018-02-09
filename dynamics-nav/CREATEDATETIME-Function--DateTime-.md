---
title: "CREATEDATETIME Function (DateTime)"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: da519380-0780-48da-8b37-bdda2bcf632c
caps.latest.revision: 6
manager: edupont
---
# CREATEDATETIME Function (DateTime)
Creates a DateTime object from a date and a time.  
  
## Syntax  
  
```  
  
DateTime := CREATEDATETIME(Date, Time)  
```  
  
#### Parameters  
 *Date*  
 Type: Date  
  
 The date that you want to use to create a DateTime.  
  
 You cannot use an undefined date to create a DateTime.  
  
 *Time*  
 Type: Time  
  
 The time that you want to use to create a DateTime.  
  
 You cannot use an undefined time to create a DateTime.  
  
## Property Value/Return Value  
 Type: DateTime  
  
 The concatenated DateTime.  
  
## Example  
 These examples of using the CREATEDATETIME function require that you create the following variables.  
  
|Name|DataType|  
|----------|--------------|  
|TestDate|Date|  
|TestTime|Time|  
|TestDateTime|DateTime|  
  
```  
TestDate := TODAY;  
TestTime := TIME;  
TestDateTime := CREATEDATETIME(TestDate,TestTime);  
…  
TestDateTime := CREATEDATETIME(081111D,020000T);  
…  
TestDateTime := CREATEDATETIME(010101D,0T);  
```  
  
## See Also  
 [DateTime Functions](DateTime-Functions.md)