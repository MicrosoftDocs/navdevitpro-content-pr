---
title: Menusuite Functionality in AL
description: "Description of the Menusuite functionality in AL."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/10/2017
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

# Menusuite Functionality in AL

Menusuite in AL provides a navigation support for search in the client functionality. This is a simple setting that enables a page or report to be available through search in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. 

You can enable the search when you create a page or report by adding a new property called **UsageCategory**. If the **UsageCategory** is set to None, or if you do not specify the **UsageCategory**, the page or report will not participate in search. If **UsageCategory** property is not None, you can specify an [AccessByPermission Property](properties/devenv-accessbypermission-property.md)  and [ApplicationArea Method](methods/devenv-applicationarea-method.md).


## Menusuite example

This Menusuite example creates a simple customer card page and sets a ``UsageCategory`` property to that page, so the ``SimpleCustomerCard`` page is enabled to participate in search.


```
page 70050088 SimpleCustomerCard 
{ 
    PageType = Card; 
    SourceTable = Customer; 
    UsageCategory = Documents;  
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
[Menusuite Properties](properties/devenv-menusuite-properties.md)   
[Page Object](devenv-page-object.md)  
[Report Object](devenv-report-object.md)  
[Developer Reference](devenv-reference-overview.md)
