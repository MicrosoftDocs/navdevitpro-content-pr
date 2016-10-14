---
title: "Page Extension Object"
description: "Description of the page extension object."
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
# Page Extension Object
The page extension object extends the <include here> page object and adds 


The following page extension object extends the Customer Card page with ID 21.

```
pageextension 21 CustomerCardExtension extends "Customer Card"
{
    actions
    {
        area(navigation)
        {
            addlast()
            {
                // With this addition you can always get to the car List
                // when you are bored with the customer.
                action(50011;"Open Car List")
                {
                    RunObject = Page TheCarList;
                }
            }
        }
    }
} 
``` 
  
## Applies To  
 Pages  
  
## Remarks  
  
## See Also  
 [Pages](Pages.md)   
 [How to: Create a Page](How-to--Create-a-Page.md)   
 [Properties](Properties.md)
