---
title: "DataItemLink Property (Reports)"
ms.custom: na
ms.date: 06/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 18ac2683-a8b0-4dc4-8dcf-717e93b51865
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---

# DataItemLink Property (Reports)
Sets the corresponding fields from two data items that are linked by the [DataItemLinkReference Property](devenv-dataitemlink-reference-property.md). The link is defined as a property of the indented (child) data item.  
  
## Applies To  
  
-   Data items  
  
-   Reports  
  
## Remarks  
 The following syntax shows the DataItemLink property.  
  
 **<field>=FIELD\(\<reference field>)**  
  
 The following table describes **field** and **reference field**.  
  
|Syntax|Description|  
|------------|-----------------|  
|<field>|A field from the child data item|  
|<reference field>|A field from the less indented (parent) data item that is identified by the [DataItemLinkReference Property](devenv-dataitemlink-reference-property.md)|  
  
 The DataItemLink property sets a filter on the child data item. This filter selects records that contain the same field value in both the parent and child data items. 
  
 The following example illustrates using this property. You have two data items, a parent and child. The parent data item is a list of customers, called Customer. The child data item contains a record of all sales orders. In the customer table, the primary key is the customer number, which is stored in the No. field. In the table that contains sales data, each record contains this customer number as a foreign key in a field called Sell-to Customer No. You set the value of the [DataItemLinkReference Property](devenv-dataitemlink-reference-property.md) on the child data item to the parent data item. You set the DataItemLink property of the child data item to the following value.  
  
 **Sell-to Customer No.=FIELD(No.)**  
  
 You now have a filter on the records in the child data item. This filter only displays records that pertain to the currently selected customer record. You can also accomplish the same task by placing the following AL statement in the [OnPreDataItem Trigger](../triggers/devenv-onpredataitem-trigger.md) for the child data item.  
  
```  
SETRANGE("Sell-to Customer No.",Customer."No.");  
```  
  
## See Also  
 [OnPreDataItem Trigger](../triggers/devenv-onpredataitem-trigger.md)   
 [DataItemLinkReference Property](devenv-dataitemlink-reference-property.md)