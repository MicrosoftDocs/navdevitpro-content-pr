---
title: "Codeunit Object"
description: "Description of the codeunit object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/14/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Codeunit Object
A codeunit is a container for AL code that you can use in many application objects. For more information, see [Understanding Codeunits](understanding-codeunits.md).

## Snippet support
Typing the shortcut ```tcodeunit``` will create the basic layout for a codeunit object when using the AL Extension in Visual Studio Code.

## Codeunit Example
This codeunit example checks whether a given customer has registered a shoesize. If not, the customer is assigned a shoesize of 42.

```
codeunit 70000100 CreateCustomer
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
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)  
[Table Extension Object](devenv-table-ext-object.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Developer Reference](devenv-reference-overview.md)
