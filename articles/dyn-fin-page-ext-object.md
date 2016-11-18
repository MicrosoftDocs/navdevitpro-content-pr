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
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---
[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/dyn_fin_dev_preview.md)]

# Page Extension Object
The page extension object extends a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] page object and adds or overrides the functionality. 

## Page Extension example
The following page extension object extends the Customer Card page object by adding a field control ```ShoeSize``` to the ```General``` group on the page. The field control is added as the last control in the group using the ```addlast``` function. 

```
pageextension 50080 CustomerCardExtension extends "Customer Card"
{
    layout
    {
        addlast(General)
        {
            field("Shoe Size"; ShoeSize)
            {
                
            }
        }
    }
} 
``` 

## Applies To  
Pages  
  
## See Also  
[Page Object](dyn-fin-page-object.md)  
[Developer Reference](dyn-fin-reference-overview.md)  
[Pages](Pages.md)   
[How to: Create a Page](How-to--Create-a-Page.md)   
[Page Properties](page-properties.md)
