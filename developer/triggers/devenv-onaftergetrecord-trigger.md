---
title: "OnAfterGetRecord Trigger"
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
ms.assetid: 07ceb5c1-253c-4336-b6ef-525e312e8650
caps.latest.revision: 7
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnAfterGetRecord Trigger
Executed after a record is retrieved from a table but before it is displayed to the user.  
  
## Applies To  
 Pages  
  
## Remarks  
 Use this trigger to calculate variables that depend on the current record.  
  
 If there is an error trigger code, then the page is closed.  
  
## See Also  
 [Triggers](devenv-triggers.md)