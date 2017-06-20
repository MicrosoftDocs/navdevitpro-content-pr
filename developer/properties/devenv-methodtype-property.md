---
title: "MethodType Property"
ms.custom: na
ms.date: 06/16/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 2173a1b2-c2aa-470d-a17f-13f71ece068c
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---
# MethodType Property
Sets a date or totals type method on the query column. The method is applied by the [Method Property](devenv-method-property.md).  
  
## Applies to  
 Query columns  
  
## Property Value  
  
|Value|Description|  
|-----------|-----------------|  
|None|No method type is applied. This is the default value.|  
|Date|Applies the date method that is specified by the **Method** property to the query column. The available date methods retrieve the day, month, or year from the date expression of field values in the column.|  
|Totals|Applies the totals method that is specified by the **Method** property to the query column. The available totals methods calculate the sum of field values in the column, the average, minimum, and maximum field value in a column, or the total number, or count, of records for a group in the resulting dataset.|  
  
## Remarks  
 The **Date** method type can only be set in fields that have a data type of Date or DateTime. For more information about date methods, see [Using the Date Method to Retrieve Day, Month, and Year Data](../devenv-Using-the-Date-Method-to-Retrieve-Day-Month--and-Year-Data.md).  
  
 Except when the **Method** property is set to **Count**, the **Totals** method type can only be used on fields that have a numeric data type of **Decimal**, **Integer**, **BigInteger**, or **Duration**.  
  
 When you set the **MethodType** property of a column to **Totals**, the rows in the resulting dataset are automatically grouped by the other columns in the query as indicated by a check mark in the **Group By** column in Query Designer. When grouped in the resulting dataset, rows that have similar column values are combined into a single record. Setting the **MethodType** property to **Totals** corresponds to using the SQL aggregate functions SUM, AVG, MIN, MAX, and COUNT in SQL SELECT statements. For more information, see [Understanding Query Totals and Grouping](../devenv-Understanding-Query-Totals-and-Grouping.md).  
  
## See Also  
 [Method Property](devenv-method-property.md)   
 [Using the Date Method to Retrieve Day, Month, and Year Data](../devenv-Using-the-Date-Method-to-Retrieve-Day--Month-and-Year-Data.md)   
 [Understanding Query Totals and Grouping](../devenv-Understanding-Query-Totals-and-Grouping.md)   
 [How to: Create Queries](../devenv-How-to-Create-Queries.md)