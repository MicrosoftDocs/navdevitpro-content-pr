---
title: "Report and Data Item Triggers"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: 7b87c648-7204-4513-babe-0a49d7996f19
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Report and Data Item Triggers
In reports, triggers are typically used to perform calculations and verification. Triggers let you control how data is selected and retrieved in a more complex and effective way than you can achieve by using properties.  

## Report Triggers  
 The following table lists triggers that apply to the report itself.  

|Trigger|Executed|  
|-------------|--------------|  
|[OnInitReport Trigger](devenv-oninitreport-trigger.md)|When the report is loaded.|  
|[OnPreReport Trigger](devenv-onprereport-trigger.md)|Before the report is run, but after the **RequestPage** has been run.|  
|[OnPostReport Trigger](devenv-onpostreport-trigger.md)|After the report has run, but not if the report was stopped manually or by the [QUIT Method (Report, XMLport)](../methods/devenv-quit-method-report-xmlport.md).|  

## Data Item Triggers  
 The following table lists triggers that apply to each data item on the report.  

|Trigger|Executed|  
|-------------|--------------|  
|[OnPreDataItem Trigger](devenv-onpredataitem-trigger.md)|Before the data item is processed, but after the associated variable has been initialized.|  
|[OnAfterGetRecord (Data Items) Trigger](devenv-onaftergetrecord-data-items-trigger.md)|When a record has been retrieved from the table.|  
|[OnPostDataItem Trigger](devenv-onpostdataitem-trigger.md)|When the data item has been iterated for the last time.|  

## See Also  
 [Report Triggers](devenv-report-triggers.md)   
 [Triggers](devenv-triggers.md)
