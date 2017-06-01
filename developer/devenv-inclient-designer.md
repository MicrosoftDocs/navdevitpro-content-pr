---
title: "Using the In-Client Designer"
description: "Description of how the in-client designer works."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/13/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.author: SusanneWindfeldPedersen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

# Using the In-Client Designer

With the [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] in-client designer, you can create extensions using drag-and-drop inside the client. With this preview of the in-client designer, you can:

- Enter and exit design mode
- Move fields around
- Add existing fields
- Preview your design (desktop, tablet, and phone preview)
- Save the extension for the tenant

## Adding a field

The in-client designer is switched on by choosing the design icon in the ribbon top right corner from any page that you want to make modifications to, and then choosing **More**. In design mode you modify the current page; you can add existing table fields, move fields around, or remove fields from the page.

![Design](media/start-design.gif)  

> [!NOTE]  
> With this preview you can only add existing table fields. Adding pages, groups, parts, and actions is not yet supported.

Use the add field functionality to add a field to the page. You will get a pane to the right where you can see all of the table fields that are available for the specific page. The table fields displayed are based on the underlying table or tables. The field can have a status of **Placed**, which means that the field already exists on the page. A status of **Ready** means that the field doesn't already exist on the page, and that you can place it.

## Other things to be aware of
When you modify subpages on a given page, a square is displayed to mark the area that you can move a field within. This is also true for FactBoxes.

Change a FastTab caption by clicking the caption and start writing.

The display type icons let you preview the changes you made on desktop, tablet, and phone clients. This way you can make sure that your design will work on the intended display target(s). You can flip to display tablet and phone designs in landscape as well.

## See Also
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)  
[Developer Reference](devenv-reference-overview.md)
