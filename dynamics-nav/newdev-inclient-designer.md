---
title: "Using the Dynamics NAV In-Client Designer"
description: "Description of how the in-client designer works."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/02/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Using the Dynamics NAV In-Client Designer

With the [!INCLUDE[navnow_md](includes/navnow_md.md)] in-client designer, you can create extensions using drag-and-drop inside the client. With this preview of the in-client designer, you can:

- Enter and exit design mode
- Move fields around
- Preview your design (desktop, tablet, and phone preview)
- Add existing fields
- Add new fields (for limited types)
- Save the extension for the tenant
 
## Adding a field

The in-client designer is switched on by choosing the design icon in the ribbon top right corner from any page that you want to make modifications to, and then choose **More**. In design mode you modify the current page; you can add new and existing table fields, move fields around, or remove fields from the page.
       
    **Note**: With this preview you can only add new and existing table fields. Adding pages and actions is not yet supported.

Use the add field functionality to add a field to the page. You will get a pane to the right where you can see all of the table fields that are available for the specific page. The table fields displayed are based on the underlying table or tables. The field can have a status of **Placed**, which means that the field already exists on the page. A status of **Ready** means that the field doesn't already exist on the page, and that you can place it.
 
If you want to add a new field, use the plus sign in the right pane and a wizard will guide you through that process. The field is now available and has a status of **Ready**.

    **Note:** When you have finished the wizard, you have to search to find the new field. 

## Other things to be aware of
When you modify subpages on a given page, a square is displayed to mark the area that you can move a field within. This is also true for FactBoxes.

Change a FastTab caption by clicking the caption and start writing. 

The display type icons let you preview the changes you made on desktop, tablet, and phone clients. This way you can make sure that your design will work on the intended display target(s). You can flip to display tablet and phone designs in landscape as well.

When you choose **Stop designing** a wizard will guide you through saving the changes you made as an extension. <!-- more? -->

## See Also
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)  
[Getting Started](newdev-get-started.md)  
[Developer Reference](newdev-reference-overview.md)