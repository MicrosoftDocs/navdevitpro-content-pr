---
title: "Table Object"
description: "Description of the table object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/06/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

 

# Table Object
Tables are the core objects used to store data in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Regardless of how data is inputted to the product - from a web service to a finger swipe on the phone app, the results of that transaction will be recorded in a table. <!-- Note whether this has the ame meaning but,here is a suggestion: Regardless of how data is inputted to the product - from a web service or a finger swipe on the phone app - the results of that transaction will be recorded in a table.-->

The structure of a table has four sections. The first block contains metadata for the overall table; the table type. The fields section describes the data elements that make up the table; their name and the type of data they can store. The keys section contains the definitions of the keys that the table needs to support. The final section details the triggers and code that can run on the table.

When developing a solution for [!INCLUDE[navnow_md](includes/navnow_md.md)], you will follow the code layout for a table as shown in the table example below, but for more details on the individual controls and properties that you can use, see [Tables](tables.md) in the online help for [!INCLUDE[navnow_md](includes/navnow_md.md)].

## Snippet support
Typing the shortcut ```ttable``` will create the basic layout for a table object when using the AL Extension in Visual Studio Code.

## Table Example
This table stores address information and has four fields; Address, Locality, Town/City, and County.

```
table 70000030 Address
{
    captionML = ENU='Sample table';
    DataPerCompany = true;

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

            trigger OnValidate();
            begin
                ValidateCounty(County);
            end;

        }
    }
    keys
    {
        key(PrimaryKey;Address)
        {
            Clustered=TRUE;
        }
    }

    var
        Msg : TextConst ENU='Hello from my method';

    trigger OnInsert();
    begin

    end;

    procedure MyMethod();
    begin
        Message(Msg);
    end;
}
```

## See Also
[Table Extension Object](devenv-table-ext-object.md)  
[Developer Reference](devenv-reference-overview.md)  
[Tables](tables.md)  
[Table Keys](table-keys.md)  
[Table Properties](table-properties.md)
