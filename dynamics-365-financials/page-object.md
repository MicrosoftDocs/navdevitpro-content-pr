---
title: "Page Object"
description: "Description of the page object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/07/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
caps.latest.revision: 18
---
# Page Object
The page object contains the definition of fields, groups, actions, and metadata. A page object definition can contain the following elements (mandatory marked):

+ PageType definition
+ SourceTable definition
+ Layout
+ Actions 


## Example

```
page 100 CustomerCard
{
    PageType = Card;
    SourceTable = Customer;

    layout
    {
        area(content)
        {
            group(1;General)
            {
                field(2;Name;Name) {}
                field(3;SearchName;SearchName) {}
                field(4;Address;Address) {}
            }

            group(10;Invoicing)
            {
                field(11;Currency;CurrencyCode) {}
            }
        }
    }

    actions
    {
        area(processing)
        {

        }

    }
}
``` 
  
## Remarks  
  
## See Also  
 [Pages](../dynamics-nav/Pages.md)   
 [How to: Create a Page](../dynamics-nav/How%20to:%20Create%20a%20Page.md)   
 [Properties](../dynamics-nav/Properties.md)
