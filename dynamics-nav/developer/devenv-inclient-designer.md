---
title: "Using the In-Client Designer"
description: "Description of how the in-client designer works."
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

# Using the In-Client Designer

With the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in-client designer, you can create extensions using drag-and-drop functionality inside the client that can perform the following actions:  

|Components   |Action                                                             | 
|-------------|-------------------------------------------------------------------|
|Fields       |Add from table, move, and remove                                   |
|Columns      |Add from table, move, remove, set freeze pane, and clear freeze pane|
|Cues (tiles) |Move and remove                                                    |
|Parts        |Move and remove                                                    |
|Captions     |Rename FastTab captions                                            |

Other capabilities for using the in-client designer include: 

- Preview design (desktop, tablet, and phone preview).   
- Save the extension for the tenant and download code.         

## Switch to design mode  

The in-client designer is switched on by choosing the design icon ![design icon](media/design_icon.png) on the ribbon top right corner from any page that you want to make modifications to, and then choosing **More**.  

> [!NOTE]  
> With this preview you can only add existing table fields. Adding pages, groups, parts, and actions is not yet supported.

![Design](media/start-design.gif)  
  
## Drag-and-drop functionality  

In design mode, you modify the current page; you can add existing table fields, move fields around, or remove fields from the page. You can use the in-client designer to make changes of what everybody in a specific role sees, by customizing the workspace to suit your business goals. Changing pages to display the information it needs, and where it needs by using the simple drag-and-drop functionality.  

## Add components

Use the add field functionality to add a field to the page. You will get a pane to the right where you can see all of the table fields that are available for the specific page. The table fields displayed are based on the underlying table or tables. The field can have a status of **Placed**, which means that the field already exists on the page. A status of **Ready** means that the field doesn't already exist on the page, and that you can place it.  

**Applies to**  

Fields, and columns.

## Move components around

Point anywhere on a field, and drag it to its new location. The location is indicated by either a thick horizontal or vertical line.  

**Applies to**  

Fields, columns, cues (tiles), and parts.

## Remove components

To remove a field, column, part, or a cue, select the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) placed on the component, and choose **Remove**. 

**Applies to**  

Fields, columns, cues (tiles), and parts. 

## Set freeze pane and clear freeze pane

The freeze pane defines the columns that always appear in the list, even when you scroll horizontally; and locks one or more columns in left till where you set freeze pane to.

Select the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) of the column that you want as the last column of the freeze pane, and then choose **Set Freeze Pane**.

If you want to set the freeze pane back to its original designed location, select the arrowhead indicator ![arrowhead indicator left](media/designer_arrow_left.png) or ![arrowhead indicator down](media/designer_arrow_down.png) for the current freeze pane column, and choose **Clear Freeze Pane**.

**Applies to**  

Columns

> [!IMPORTANT]  
> For columns, you cannot make changes to a list if the list is shown as tiles. You must first switch the page to the list view by selecting the icon ![show as list](media/show_as_list.png "show as list").  

## Edit caption

Change a FastTab caption by clicking the caption and start writing. 

**Applies to**  

FastTab

## Preview on target device

The display type icons let you preview the changes you made on desktop ![desktop](media/desktop_view.png), tablet ![tablet](media/tablet_view.png), and phone ![phone](media/phone_view.png) clients. This way you can make sure that your design will work on the intended display target(s). You can flip to display tablet and phone designs in landscape as well. 

![Display options](media/display_options.png)  

## Save extension
Finish up your design by choosing **Stop Designing**, which allows you to name the extension with an option to download code, and save the extension for the tenant. 

## Other things to be aware of

- When you modify subpages on a given page, a square is displayed to mark the area that you can move a field within. This is also true for FactBoxes.  

- Removing specific fields are restricted due to accounting limitations.

- You can only add fields, columns, or tiles from a predefined list, which is based on the page. You cannot create new ones.  

- You can only add fields, columns or tiles in its specific view ![show as list](media/show_as_list.png "show as list"), ![show as tall tiles](media/show_as_tall_tiles.png "show as tall tiles"), or ![show as wide tiles](media/show_as_wide_tiles.png "show as wide tiles"). 

## See Also
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)  
[Developer Reference](devenv-reference-overview.md)
