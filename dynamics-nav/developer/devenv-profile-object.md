---
title: "Profile Object"
description: "Description of the page object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/11/2017
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

# Profile Object
The profile object in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] allows you to build an individual experience for each user profile. Profile object performs a validatation to check whether the specified role center page, and page customizations exists, when you define a new profile object. You can add changes to the page layout and actions, but you cannot add variables, procedures, or triggers. 

## Snippet support
Typing the shortcut ```tprofile``` will create the basic layout for a profile object when using the AL Extension in Visual Studio Code.

## Page example

```
profile TheBoss 
{
    Description = 'The Boss';
    RoleCenter = "Business Manager Role Center";
    Customizations = MyCustomization;
}

pagecustomization MyCustomization customizes "Customer List"
{
    layout
    {
        modify(Name) {
            Visible = false;
        }
    }
}

```

## See Also  
[Developer Reference](devenv-reference-overview.md)  
[Developing Extensions](devenv-dev-overview.md)  
