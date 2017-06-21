---
title: "INIT Method (SessionSettings)"
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
author: jswymer
---
# INIT Method
Creates a SessionsSettings fills the property bag with the data currently in the database.  

## Syntax  

```  
SessionSettings.INIT
```  

## Remarks  
 The system automatically converts all of the numeric data types for you.  

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
[REQUESTSESSIONUPDATE method](devenv-requestsessionupdate-method.md)  
