---
title: "Using Designer"
description: "Description of how Designer works."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 08/28/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Using Designer

Developing extensions using new development environment offers a wide range of possibilities. It is exceedingly important to pick suitable ways that servers a better development experience, when switching between user interface (UI) and VS Code. Designer truly complements VS Code, as it provides easy and convenient way of making immediate adjustments to your design using drag-and-drop components.  

Here is a quick overview of [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] Designer capabilities: 

|Features                            |Applies to                       | 
|-----------------------------------|---------------------------------|
|Add components                     |fields and columns               |
|Move components around             |fields, columns, cues, and parts |
|Remove components                  |fields, columns, cues, and parts |
|Set freeze pane and clear freeze pane |columns                       |
|Edit caption                       |fasttab, cards, factbox          |
|Preview design                     |general                          |
|Save extension and download code   |general                          |

## Enter Designer

Enter Designer, by choosing the design icon ![design icon](media/design_icon.png) on the ribbon top right corner from any page that you want to make modifications to, and start designing using drag-and-drop components. You can also launch the browser, and enter Designer, using the F6 shortcut in VS Code. 

> [!NOTE]  
> With this preview you can only add existing table fields. Adding pages, groups, parts, and actions is not yet supported.

![Design](media/start-design.gif)  

Every time you start designing, you are effectively creating a new extension. Your changes are immediately visible to other users. Finish up your design by choosing **Stop Designing**, which allows you to name the extension with an option to download code, and save the extension for the tenant. If you choose not to download the code at the end, you can still pull that via the Ctrl+F7 shortcut. You can also uninstall the extension from the Extension Management page or even download source from there. 

## Drag-and-drop components

In Designer, you modify the current page; you can add existing table fields, move fields around, or remove fields from the page. You can make changes to display the information it needs, and where it needs by using drag-and-drop components. The changes you make in Designer will apply to all users.

To add components, you get a pane to the right where you can see all of the table fields that are available for the specific page. The table fields displayed are based on the underlying table or tables. The field can have a status of **Placed**, which means that the field already exists on the page. A status of **Ready** means that the field doesn't already exist on the page, and that you can place it. 

Edit FastTab, Card, FactBox captions by clicking the caption and start writing. Simple, clear, and plain.

Removing a field, column, part, or a cue can be performed, by selecting the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) placed on the component, and then by choosing **Remove**. 

## Set freeze pane and clear freeze pane

The freeze pane locks one or more columns to the left, even when you scroll horizontally. You can set freeze pane, by selecting the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) of the column that you want as the last column of the freeze pane, and then by choosing **Set Freeze Pane**. If you want to set the freeze pane back to its original designed location, select the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) for the current freeze pane column, and then choose **Clear Freeze Pane**.

## Preview design

The display type icons let you preview the changes you made on desktop ![desktop](media/desktop_view.png), tablet ![tablet](media/tablet_view.png), and phone ![phone](media/phone_view.png) clients. This way you can make sure that your design will work on the intended display target(s). You can flip to display tablet and phone designs in portrait and landscape. 

![Display options](media/display_options.png)  

## Other things to be aware of

- When you modify parts on a given page, a square is displayed to mark the area that you can move a field within. This is also true for FactBoxes.  

- Removing specific fields are restricted due to accounting limitations.

- You can only add fields, columns or tiles to the applicable view by selecting the icon ![show as list](media/show_as_list.png "show as list"), ![show as tall tiles](media/show_as_tall_tiles.png "show as tall tiles"), or ![show as wide tiles](media/show_as_wide_tiles.png "show as wide tiles"). Adding certain components is not allowed using drag-and-drop when it is restricted to that view.

- You can only add fields/columns, from a predefined list, which is based on the source table. You cannot create new ones.  


## See Also
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)  
[Developer Reference](devenv-reference-overview.md)
