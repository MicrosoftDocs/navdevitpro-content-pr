---
title: "Report Object"
description: "Description of the report object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/06/2017
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

# Report Object
Reports are used to print or display information from a database. You can use a report to structure and summarize information, and to print documents, such as sales quotes and invoices. 

Creating a report consists of two primary tasks; the first task is to create the underlying data model and the next is to define the visual layout that displays the data. The report object defines the underlying data model and specifies which database tables and fields to pull data from. When the report is run, that data is displayed in a specified layout; the visual layout, which determines the content and format of a report when it is viewed and printed. 

You build the layout of a report by arranging data items and columns, and specifying the general format, such as text font and size. There are two types of report layouts; client report definition, also called RDCL layouts and Word layouts. RDLC layouts are defined in Visual Studio Report Designer or Microsoft SQL Server Reporting Services Report Builder. Word layouts are created using Word 20?. Word layouts are based on a Word document that includes a custom XML part representing the report dataset.

## Snippet support
Typing the shortcut ```?``` will create the basic layout for a report object when using the AL Extension in Visual Studio Code.

## Report example

```

```

## See Also
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)  
[Developer Reference](newdev-reference-overview.md)  
[Page Extension Object](newdev-page-ext-object.md)  
[Pages](pages.md)  
[Tables](tables.md)  
[Page Properties](page-properties.md)