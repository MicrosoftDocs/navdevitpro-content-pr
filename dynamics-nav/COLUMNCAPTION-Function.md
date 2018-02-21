---
title: "COLUMNCAPTION Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 47ad403e-3a68-47b8-a4a2-0896b1c88a0d
caps.latest.revision: 12
manager: edupont
---
# COLUMNCAPTION Function
Returns the current caption of a query column as a text string.  
  
## Syntax  
  
```  
  
Caption := Query.COLUMNCAPTION(Column)  
```  
  
#### Parameters  
 *Query*  
 Type: query  
  
 A variable that specifies the query object that contains the column.  
  
 *Column*  
 Type: Text  
  
 Refers to the name of the query column. The name of a query column is specified by the [Name Property](Name-Property.md) of the column in Query Designer.  
  
## Property Value/Return Value  
 Type: Text  
  
 The current value of [CaptionML Property](CaptionML-Property.md) for the query column.  
  
## Remarks  
 The **CaptionML** property is multi-language enabled, so it can contain a list of text strings in different languages. The string that is used is selected according to the user's language settings. For more information, see [Multilanguage Development](Multilanguage-Development.md).  
  
## Example  
 The following example shows how to get the caption for a column of a query. The query is called **My Customer Query** and has a column with the name **Customer\_No**.  
  
 This example requires that you create the following variables.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Caption|Text|Not applicable|  
|MyQuery|Query|My Customer Query|  
  
```  
Caption := MyQuery.COLUMNCAPTION("Customer_No");  
MESSAGE(Caption);  
```  
  
## See Also  
 [How to: Create Queries](How-to--Create-Queries.md)