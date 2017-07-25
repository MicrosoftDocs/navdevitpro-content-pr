---
title: "OnAssistEdit Trigger"
description: 
author: SusanneWindfeldPedersen

ms.custom: na
ms.date: 07/07/2017
ms.author: solsen
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: 8b1ead83-80f1-42cc-b091-d0732efc156b
caps.latest.revision: 11
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnAssistEdit Trigger
Executed in place of the [AssistEdit Property](../properties/devenv-assistedit-property.md) features that are provided in the application.  

## Applies To  
 Fields on pages  

> [!NOTE]  
>  The trigger is not invoked on a page that is in view mode<!--NAV in the [!INCLUDE[nav_web](../includes/nav_web_md.md)]-->.  

## Remarks  
 If there is an error in the trigger code, then the page is closed.  

 You can use this trigger to write to the database.  

## See Also  
 [Triggers](devenv-triggers.md)
