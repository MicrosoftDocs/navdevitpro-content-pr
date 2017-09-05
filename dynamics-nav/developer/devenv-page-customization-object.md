---
title: "Page Customization Object"
description: "Description of the page customization object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 07/12/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Page Customization Object
The page customization object in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. The page customization object has more restrictions than the [page extension object](devenv-page-ext-object.md); when you define a new page customization object, you cannot add variables, procedures, or triggers. You can add changes to the page layout and actions.

## Snippet support
Typing the shortcut ```tpagecust``` will create the basic layout for a page customization object when using the AL Extension in Visual Studio Code.

## Page customization example
The following page customization example 

```
pagecustomization 70000123 MyCustomization customizes "Customer List"
{
    actions
    {
        moveafter("Blanket Orders"; "Aged Accounts Receivable")

        modify(NewSalesBlanketOrder)
        {
            Visible = false;
        }

        
    }
}
```

## See Also
[Developing Extensions](devenv-dev-overview.md)  
[Developer Reference](devenv-reference-overview.md)  
[Page Object](devenv-page-object.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Page Extension Properties](properties/devenv-page-property-overview.md)   
