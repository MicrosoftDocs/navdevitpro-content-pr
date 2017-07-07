---
title: "PrintOnlyIfDetail Property"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: c789cb47-8bd3-4764-8517-6f9390000313
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# PrintOnlyIfDetail Property
Specifies whether to print data in a report for the parent data item when the child data item does not generate any output.  
  
## Applies To  
 Data items  
  
## Property Value  
 **True** if you want print only if the child data item generates output; otherwise, **false**. The default is **false**.  
  
## Remarks  
 This property has no effect on a data item that does not have any child data items. If this property is **false** and there is no record in the child data item that corresponds to the current record in the parent data item, then the report prints data from the current record in the parent data item, even though there is no data for the child data item. If this property is **true** and there is no record in the child data item that corresponds to the current record in the parent data item, then the report does not print data from the current record in the parent data item.  
  
 If there are more than two data items, then the report iterates through each parent-child relationship in the same way.  
  
 Another way to achieve the result of not printing blank lines is to add a filter on the table. For more information, see [SETFILTER Function (Record)](../methods/devenv-SETFILTER-Method-Record.md).  
  
 In previous versions of [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] reports, you could control whether data items without data were printed with the use of body sections in Section Designer. After you upgrade reports in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)], verify whether you need to use filters or the **PrintOnlyIfDetail** property to achieve the same resulting report.  
  
## Example  
 In this example, you create a report to print data from the Sales Header and Sales Line tables. The parent data item is Sales Header. For each record in the Sales Header table, the report iterates through records in the Sales Line table.  
  
 The Sales Header table contains the following data.  
  
|Document Type|Sell-to Customer No.|No.|…|  
|-------------|--------------------|---|-|  
|Order|38128456|101009|…|  
|Order|43687129|101011|…|  
|Order|46897889|101013|…|  
|Order|46897889|101015|…|  
|Order|10000|101016|…|  
  
 The Sales Line table contains the following data.  
  
|Document Type|Document No.|Line No.|…|  
|-------------|------------|--------|-|  
|Order|101009|10000|…|  
|Order|101009|20000|…|  
|Order|101013|10000|…|  
  
 In this example, you set the [DataItemLink Property (Reports)](devenv-dataitemlink-reports-property.md) to "Document Type=FIELD(Document Type),Document No.=FIELD(No.)". If you set **PrintOnlyIfDetail** to **true**, then the report outputs the following data.  
  
|Document Type|Customer No.|Document No.|Line No.|…|  
|-------------|------------|------------|--------|-|  
|Order|38128456|101009|10000|…|  
|Order|38128456|101009|20000|…|  
|Order|46897889|101013|10000|…|  
  
 If you set **PrintOnlyIfDetail** to **false**, then the report outputs the following data.  
  
|Document Type|Customer No.|Document No.|Line No.|…|  
|-------------|------------|------------|--------|-|  
|Order|38128456|101009|10000|…|  
|Order|38128456|101009|20000|…|  
|Order|43687129|101011||…|  
|Order|46897889|101013|10000|…|  
|Order|46897889|101015||…|  
|Order|10000|101016||…|  
  
## See Also  
 [PRINTONLYIFDETAIL Method (Report)](../methods/devenv-printonlyifdetail-method-report.md)