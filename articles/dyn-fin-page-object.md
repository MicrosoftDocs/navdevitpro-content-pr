--
title: "Page Object"
description: "Description of the page object."
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

# Page Object
Pages are the main way to display and organize visual data in [!INCLUDE[navnow_md](includes/navnow_md.md)]. They are the primary object that a user will interact with and have a different behavior based on the type that you choose. Pages are designed independently of the device they are to be rendered on, and in this way the same page can be reused across phone, tablet, and web clients.

The structure of a page is hierarchical and breaks down in to three sections. The first block contains metadata for the overall page; the type of the page and the source table it is showing data from. The next section; the layout, describes the visual parts on the page. The final section details the actions that are published on the page.

When developing a solution for [!INCLUDE[navnow_md](includes/navnow_md.md)], you will follow the code layout for a page as shown in the page example below, but for more details on the individual controls and properties that are available, see [Pages](pages.md) in the online help for [!INCLUDE[navnow_md](includes/navnow_md.md)]. 

## Snippet support
Typing the shortcut 'pp' will create the basic layout for a page object when using the AL Extension for Financials in Visual Studio Code.

## Page example

```
page 50088 SimpleCustomerCard
{
    PageType = Card;
    SourceTable = Customer;

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
    {
        // Actions //
    }
}
```

## See Also
[Developing for Dynamics 365 for Financials Overview](dyn-fin-dev-overview.md)  
[Developer Reference](dyn-fin-reference-overview.md)  
[Page Extension Object](dyn-fin-page-ext-object.md)  
[Pages](pages.md)  
[Tables](tables.md)
[Page Properties](page-properties.md)