---
title: "Table Extension Object"
description: "Description of the table extension object."
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

# Table Extension Object
The table extension object extends a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] table object and adds or overrides the functionality. 

## Table Extension example
This table extension object extends the Customer table object by adding a field ```ShoeSize```, with ID 50090 and the data type ```Decimal```. It also contains a procedure to check if the ShoeSize field is filled in. 

```
tableextension 50090 CustomerExtension extends Customer
{
    fields
    {
        field(50090;ShoeSize;Decimal) {}
    }

    procedure HasShoeSize() : Boolean;
    begin
        exit(ShoeSize <> 0);
    end;
}
```
## Applies to
Tables

## See Also
 [Tables](tables.md)  
 [Properties](Properties.md)
