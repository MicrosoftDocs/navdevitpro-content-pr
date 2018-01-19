---
title: Adding Menus to the Navigation Pane
description: "Enable users to quickly navigate and perform actions by adding the menu items to the navigation pane."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 19/01/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18 

---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Adding Menus to the Navigation Pane

 The navigation pane appears on the left side of the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] window, and contains multiple sections that enable users to quickly navigate and perform actions in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. A single section in the navigation pane can be defined as a menu group that contains multiple sub-menu items. 

 The navigation pane displays the home menu items by default; the other menu items can be accessed by clicking on the small drop-down arrow placed next to the *selected* menu category in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. For users, the menu groups that display in the navigation pane could change depending on the role center page that they access. 


 
 ## How to Add Menus to the Navigation Pane

 In order to add a menu group and sub-menu items to the navigation pane, follow the steps described below.
 
 1. Create a [Page Extension Object](devenv-page-ext-object.md) that extends the **Role Center** page.  
 2. Start creating the [Actions](devenv-actions-overview.md); this will enable you to add multiple actions that users can perform.  
 3. Specify where you will place the new menu group with the existing set of menu items. For example, if you want to place a new menu group before the Sales menu, then add  `addbefore(Sales)`.  
 4. The new menu group should be given a name; this will be the name of the **Actions** group that displays on the Navigation pane.  
 5. Finally, define the appropriate set of **Actions** that you want to add to the new menu group; these actions are displayed as the sub-menu items.


 ## Example
 The example below explains how to add the menu group called `My New Action Group` to the navigation pane. The sub-menu items for the `My New Action Group` contains the actions which are named as `First new page` and `Second new page`. The `First new page` action opens the `Customer Bank Account List` page. In this example, the `My New Action Group` will appear on the navigation pane for the **Sales Order Processor** Role Center. 

```al
pageextension 50120 ExtendNavigationPane extends "Order Processor Role Center"
{

    actions
    {
        addlast(Sections)
        {
            group("My New Action Group")
            {
                action("First new page")
                {
                    RunObject = page "Customer Bank Account List";
                    ApplicationArea = All;
                }
                 action("Second new page")
                {
                    RunObject = page "Customer Ledger Entries";
                    ApplicationArea = All;
                }
            }
        }
    }
}
```

You can also enable pages and reports to appear in the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] search for a quick navigational support. For more information, see [Adding Pages and Reports to Search](devenv-al-menusuite-functionality.md).   

## See Also
[Differences in the Dynamics NAV Development Environments](devenv-differences.md)  
[AL Development Environment](devenv-reference-overview.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Actions Overview](devenv-actions-overview.md)  
[Adding Pages and Reports to Search](devenv-al-menusuite-functionality.md)  