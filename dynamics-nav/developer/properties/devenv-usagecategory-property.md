---
title: "UsageCategory Property"
description: "Description of how you use C/SIDE to add pages and reports to Search in the client using the UsageCategory property."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/05/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# UsageCategory Property
Is used to enable a page or report to be available through Search.

## Property Values
The values for the **UsageCategory** property are listed below: 

- None
- Lists
- Tasks
- ReportsAndAnalysis
- Documents
- History
- Administration


## Applies to 

- Pages
- Reports 

## Remarks

If the **UsageCategory** is set to **None**, or if you do not specify **UsageCategory**, the page or report will not show up when you use the Search functionality. 
To make new objects searchable, modify the value of the **UsageCategory** property for the chosen objects, compile them, and then run `Tools > Build Object Search Index` in C/SIDE. This command allows a user to find the newly created objects when the Search function from the Web Client or Windows Client is used. 

## PowerShell 
You can run this command from PowerShell as it follows: 

```
.\finsql.exe Command=buildobjectsearchindex, Servername=YourServer, Logfile=out.txt, Database=YourDatabase
```


## Dependent Properties

The [AccessByPermission property](devenv-accessbypermission-property.md) and [ApplicationArea Property](devenv-applicationarea-property.md) are optional properties, which can be applied to set restrictions on an object accessibility, when you add the **UsageCategory** property. 


## See Also
[Properties](devenv-properties.md)   
[Page Object](../devenv-page-object.md)  
[Report Object](../devenv-report-object.md)  
