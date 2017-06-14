---
title: "DataItemLinkType Property"
ms.custom: na
ms.date: 06/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 2805061c-ac39-4ff4-ae23-c4dc5e462636
caps.latest.revision: 6
manager: edupont
---
# DataItemLinkType Property
Sets the data item link type between data items in a query to determine the records that are included in the resulting dataset.  
  
## Applies To  
  
-   Query data items  
  
## Property Value  
 The DataItemLinkType property has the following values.  
  
|Value|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-----------|---------------------------------------|  
|Use Default Values If No Match|The resulting dataset contains all the records from the upper data item or data items; even if a record does not have a matching value in the linked field of lower data item as specified by the [DataItemLink Property \(Query\)](devenv-dataitemlink-query-property.md).|  
|Exclude Row If No Match|The resulting dataset contains only records from data item tables that have matching values for the fields that are linked by the DataItemLink property.|  
|SQL Advanced Options|Provide alternatives to **Use Default Values If No Match** and **Exclude Row If No Match** for generating a dataset that correspond to joins in SQL SELECT statements. When you set the property to SQL Advanced Options, the [SQLJoinType Property](devenv-sql-join-type-property.md) appears where you can select the SQL join types. For more information, see [SQL Advanced Options for Data Item Link Types](SQL-Advanced-Options-for-Data-Item-Link-Types.md).|  
  
## Remarks  
 When setting up a data item link between two data items, you always set up the DataItemLinkType property on the lower data item in Query Designer.  
  
 The DataItemLinkType property works together with the DataItemLinkType property to combine records from tables into a dataset. The DataItemLink property sets up "equal to" \(=\) comparison between two or more fields of the data item tables. When the query is run, the query compares each row of the two data items to find records that have matching values for the fields. Records that have matching field values are combined into a row in the resulting dataset. In some cases, there will be records that do not have matching values. You use the [DataItemLinkType Property](devenv-dataitemlink-type-property.md) to include records that do not have matching field values.  
  
> [!NOTE]  
>  If the DataItemLinkType property is set to **SQL Advanced Options** and the [SQLJoinType Property](devenv-sql-join-type-property.md) is set to **Cross Join**, then you cannot set the DataItemLink property because there is no relationship between table fields. For more information about cross joins, see [SQL Advanced Options for Data Item Link Types](SQL-Advanced-Options-for-Data-Item-Link-Types.md).  
  
 For more information about data item links, see [Understanding Data Item Links](Understanding-Data-Item-Links.md).  
  
 For a step-by-example of using the DataItemLinkType, see [Walkthrough: Creating a Query to Link Two Tables](Walkthrough--Creating-a-Query-to-Link-Two-Tables.md).