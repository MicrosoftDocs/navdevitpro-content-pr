---
title: "Table Object"
description: "Description of the table object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/11/2016
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

# Table Object
Tables are fundamental objects that lets you store and manipulate data.     

## Table Example
This table stores address information and has four fields; Address, Locality, Town/City, and County.

```
table 51000 Address
{
    fields
    {
        field(1;Address;Text[50])
        {
            Description='Address retrieved by Service';
        }
        field(2;Locality;Text[30])
        {
            Description='Locality retrieved by Service';
        }
        field(3;"Town/City";Text[30])
        {
            Description='Town/City retrieved by Service';
        }
        field(4;County;Text[30])
        {
            Description='County retrieved by Service';
        }
    }
    keys
    {
        key(1;PrimaryKey;Address)
        {
            Clustered=TRUE;
        }
    }

    procedure MyOrgMethod();
    begin
        Message('Hello from the original method');
    end;
}
```

## See Also
[Tables](tables.md)  
[Table Keys](table-keys.md)