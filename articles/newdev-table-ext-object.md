---
title: "Table Extension Object"
description: "Description of the table extension object."
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

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Table Extension Object
The table extension object allows you to add additional fields or to change some properties on a table provided by the [!INCLUDE[navnow_md](includes/navnow_md.md)] service. In this way, you can add data to the same table and treat it as a single table. For example, you may wish to create a table extension for a retail winter sports store. In your solution you want to have ```Ski Size``` as an additional field on the customer table. Adding this as an extension allows you to write code for the customer record and also include values for the ```Ski Size```.

Along with defining other fields, the table extension is where you write trigger code for your additional fields.

When developing a solution for [!INCLUDE[navnow_md](includes/navnow_md.md)], you will follow the code layout for a table extension as shown in the example below, but for more details on the individual controls and properties that are available, see [Tables](tables.md). 

## Snippet support ##
Typing the shortcut 'te' will create the basic layout for a table extension object when using the AL Extension in Visual Studio Code.

## Properties ##
Using a table extension allows you to overwrite some properties on fields in the base table. The following properties can be changed:

- optioncaptionML
- closing date
- description
- width

## Table Extension example
This table extension object extends the Customer table object by adding a field ```Ski Size```, with ID 50090 and the data type ```Integer```. It also contains a procedure to check if the ```ShoeSize``` field is filled in. 

```
tableextension 50090 RetailWinterSportsStore extends Customer
{
    fields
    {
        field(50090;SkiSize;Integer) {}
        // How do I set description property?

        // How do I change a property (like description) on an existing field?
    }

    procedure HasSkiSize() : Boolean;
    begin
        exit(ShoeSize <> 0);
    end;
}
```
## Applies to
Tables

## See Also
[Table Object](newdev-table-object.md)  
[Developer Reference](newdev-reference-overview.md)  
[Tables](tables.md)  
[Table Properties](table-properties.md)
