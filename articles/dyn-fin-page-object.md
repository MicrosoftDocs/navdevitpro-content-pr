--
title: "Page Object"
description: "Description of the page object."
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

# Page Object
 
## Page Overview ##

Pages are the main way to display and organize visual data in Dynamics 365 for Financials. They are the primary object that a user will interact with and have a different behavior based on the type you choose. Pages are designed independantly of the device they are to be rendered on, and in this way the same page can be reused across phone, tablet and web clients.

The structure of a page is heirarchical and breaks down in to three sections.  The first block contains metadata for the overall page; which type the page is and which source table it is showing the data from.  The next section - the layout - describes the visual parts on the page.  The final section details the actions that are published on the page.

In developing a solution for Dynamics 365 for Financials, you will follow the code layout for a page as shown in the Page Example, but for more details on the individual controls and properties you can use, see the [Pages Overview](https://msdn.microsoft.com/en-us/dynamics-nav/pages-overview) section in the online help for Dynamics NAV. 

## Snippet support ##
Typing the shortcut 'pp' will create the basic layout for a page object when using the AL Extension for Dyanmics 365 for Financials in Visual Studio Code.

## Page Example

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

## See Also
[Tables](tables.md)
[Sample code online](http://whatabouthosting10pagesinasamplepack.com)
