---
title: "Table Object"
description: "Description of the table object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/15/2016
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
Tables are the core objects used to store data in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Regardless of how data is inputted to the product - from a web service to a finger swipe on the phone app, the results of that transaction will be recorded in a table.

The structure of a table has four sections. The first block contains metadata for the overall table; the table type. The fields section describes the data elements that make up the table; their name and the type of data they can store. The keys section contains the definitions of the keys that the table needs to support. The final section details the triggers and code that can run on the table.

When developing a solution for Financials, you will follow the code layout for a table as shown in the table example below, but for more details on the individual controls and properties that you can use, see [Tables](tables.md) in the online help for [!INCLUDE[navnow_md](includes/navnow_md.md)]. 

## Snippet support
Typing the shortcut 'tt' will create the basic layout for a table object when using the AL Extension for Financials in Visual Studio Code.

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
[Table Extension Object](dyn-fin-table-ext-object.md)  
[Developer Reference](dyn-fin-reference-overview.md)  
[Tables](tables.md)  
[Table Keys](table-keys.md)  
[Table Properties](table-properties.md)