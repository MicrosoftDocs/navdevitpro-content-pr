---
title: "DataCaptionFields Property"
ms.custom: na
ms.date: 06/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 82dc05b4-3c03-4c55-808b-2b6b5eb2f820
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# DataCaptionFields Property
Sets the fields that appear to the left of the caption on pages that display the contents of this table.  
  
## Applies To  
  
-   Pages  
  
-   Tables  
  
## Remarks  
  
## Card Pages  
 Card pages display one record at a time. For this object, the value of the underlying table's DataCaptionFields property is used; the value of this property on the page is ignored. If the DataCaptionFields property is not defined on the table, the primary key is used.  
  
## Tabular Pages  
 Tabular pages show multiple records at a time. The following data caption rules are applied:  
  
-   A data caption is only displayed if a filter containing the fields defined in the DataCaptionFields property for the page evaluate to one value. In this case, two situations are possible:  
  
    -   There is a table relation (as defined by the [TableRelation Property](devenv-tablerelation-property.md)) on one or more of the fields. In this case, the DataCaptionFields from the underlying table are used. If this table does not have a value for the DataCaptionFields property, the primary key for that table is used.  
  
    -   There is no table relation. In this case, the (single) value that results from evaluating the filter is used directly.  
  
## Example of DataCaptionFields Use  
 The following is an example of how the DataCaptionFields property is used. The Customer Card page (21) is based on the Customer table (18). Using the **Navigate** menu on this page, users can open other pages, including the Customer Ledger Entry page (25).  
  
 In the Customer table, the DataCaptionFields property is set to **No., Name**. On the Customer Ledger Entry page, the DataCaptionFields property is set to **CustomerNo.**. When the Customer Ledger Entry page (25) is opened from the Customer Card page (21), a filter is set on Customer No. field of the Customer Ledger Entries table, selecting only those entries related to the currently displayed customer on the Customer Card. This relationship is accomplished by setting the **RunPageLink** property of the menu item that invokes the Customer Ledger Entry page to Customer No.=FIELD(No.).  
  
 If you view the Customer Ledger Entry page with a filter applied, the customer name and number appear to the left of the caption on the Customer Ledger Entry page. If you remove the filter, the caption disappears.  
  
 The important point is that the DataCaptionFields property on a page does not directly put any caption on the page, but only works when used with appropriate settings of DataCaptionFields at the table level.  
  
## See Also  
 [Properties](devenv-properties.md)