---
title: "Codeunit Object"
description: "Description of the codeunit object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/25/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/dyn_fin_dev_preview.md)]

# Codeunit Object
A codeunit is a container for AL code that you can use in many application objects. For more information, see [Understanding Codeunits](understanding-codeunits.md).

## Codeunit Example
This codeunit example  

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
[Table Extension Object](dyn-fin-table-ext-object.md)  
[Page Extension Object](dyn-fin-page-ext-object.md)  
[Developer Reference](dyn-fin-reference-overview.md)
