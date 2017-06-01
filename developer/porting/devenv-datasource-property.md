---
title: "DataSource Property"
ms.custom: na
ms.date: 06/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 5e18b123-0ded-4aec-aa31-c710e6c015b4
caps.latest.revision: 7
manager: edupont
---
# DataSource Property
Sets the field to associate with a column of a query.  
  
## Applies to  
 Query columns and filter rows  
  
## Property Value  
 Field  
  
 You choose fields from the table that is specified by the [DataItemTable Property](DataItemTable-Property.md) of the column’s parent data item.  
  
## Remarks  
 A query retrieves data from fields of one or more tables. To specify a table in a query, you define a data item, and then set the DataItemTable Property of the data item to the table. After you define the data item, you can add columns under the data item, and then modify the DataSource properties of the columns to specify the fields to include in the query results. You can also set the column field by changing the **Data Source** column in Query Designer.  
  
 You can use the same field on different columns in your query. Each column in a query must a unique name, which is defined by the defined by the [Name Property](Name-Property.md). By default, columns are given a name that is based on the field name. If the query has duplicate column names, then you use the Name Property to give columns unique names.  
  
## See Also  
 [Understanding Query Filters](Understanding-Query-Filters.md)   
 [How to: Set Up Filter Rows in Query Designer](How-to--Set-Up-Filter-Rows-in-Query-Designer.md)