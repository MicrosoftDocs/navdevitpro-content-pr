---
title: "Codeunit Object"
description: "Description of the codeunit object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/30/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Codeunit Object
A codeunit is a container for AL code that you can use in many application objects. For more information, see [Understanding Codeunits](understanding-codeunits.md).

## Codeunit Example
This codeunit example checks whether a given customer has registered a shoesize. If not, the customer is assigned a shoesize of 42.

```
codeunit 50040 CreateCustomer
{
    trigger OnRun();
    var
        r : record Customer;
    begin
        if not r.HasShoeSize() then
            r.ShoeSize :=  42;  
    end;
}

```

## See Also
[Developing Extensions for Dynamics NAV Overview](newdev-dev-overview.md)
[Table Extension Object](newdev-table-ext-object.md)  
[Page Extension Object](newdev-page-ext-object.md)  
[Developer Reference](newdev-reference-overview.md)
