---
title: "Adding Pages and Reports to Search"
description: "Description of how you use AL to add pages and reports to Search in the client."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Adding Pages and Reports to Search
AL provides navigational support for pages and reports in the client. You enable a page or report to be available through Search in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] using the **UsageCategory** setting. 

When you create a [Page](devenv-page-object.md) or a [Report](devenv-report-object.md), you add the **UsageCategory** property. The values for the UsageCategory property are listed below: 

- None
- Lists
- Tasks
- ReportsAndAnalysis
- Documents
- History
- Administration

If the **UsageCategory** is set to **None**, or if you do not specify **UsageCategory**, the page or report will not show up when you use the Search functionality. 

<!--
If you want to add the page or report to Search, set the **UsageCategory** property by adding the [AccessByPermission Property](properties/devenv-accessbypermission-property.md) and [ApplicationArea Property](properties/devenv-applicationarea-property.md). 
-->

## Optional Accessibility Settings

You can add the page or report to Search and control the accessibility to **Execute** access, or, allow **Read**, **Insert**, **Modify** and **Delete** access by adding the [AccessByPermission property](properties/devenv-accessbypermission-property.md). Likewise, control the accessibility to application area by the grouped-user category by adding the [ApplicationArea Property](properties/devenv-applicationarea-property.md). 

The [AccessByPermission Property](properties/devenv-accessbypermission-property.md) and [ApplicationArea Property](properties/devenv-applicationarea-property.md) are some optional settings for using with **UsageCategory** property.


## Example
The following example creates a ``SimpleCustomerCard`` page and sets a ``UsageCategory`` property to the page, so that the ``SimpleCustomerCard`` page is enabled in Search. 


```
page 70050088 SimpleCustomerCard 
{ 
    PageType = Card; 
    SourceTable = Customer; 
    UsageCategory = Documents;  
    AccessByPermission = page SimpleCustomerCard = X;
    ApplicationArea = Basic;
    layout 
    { 
        area(content) 
        { 
            group(General) 
            { 
                field("No.";"No.") {} 
                field(Name;Name) {} 
                field(Address;Address) {} 
            } 
        } 
    } 
} 

```

## See Also
[MenuSuite Properties](properties/devenv-menusuite-properties.md)   
[Page Object](devenv-page-object.md)  
[Report Object](devenv-report-object.md)  
[Developer Reference](devenv-reference-overview.md)
