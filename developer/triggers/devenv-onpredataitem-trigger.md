---
title: "OnPreDataItem Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: 4b6df5e3-5346-4171-8113-54e098e4bc02
caps.latest.revision: 7
---
# OnPreDataItem Trigger
Executed before a data item is processed.  

## Applies To  
 Data items  

## Remarks  
 This trigger is executed before a data item is processed, but after the associated variable is initialized and table views and filters are set.  

 You can use this trigger to add additional filtering beyond what is established by the [DataItemLink Property \(Reports\)](../devenv-dataitemlinkreports-property.md) or [DataItemTableView Property](../devenv-DataItemTableView-Property.md). For example, use this trigger if you need to filter an indented data item based on the result of a calculation. Use the [SETRANGE Record\)](../methods/devenv-SETRANGE-Method-Record.md) or [SETFILTER Record\)](../methods/devenv-SETFILTER-Method-Record.md)  to add extra delimiters.  

## See Also  
 [DataItemLink Property \(Reports\)](../devenv-dataitemlinkreports-property.md)   
 [DataItemTableView Property](../devenv-DataItemTableView-Property.md)   
 [SETRANGE Record\)](../methods/devenv-SETRANGE-Method-Record.md)   
 [SETFILTER Record\)](../methods/devenv-SETFILTER-Method-Record.md)
