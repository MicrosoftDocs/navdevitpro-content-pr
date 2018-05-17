---
title: "PasteIsValid Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 7f3e261c-65ba-4adc-9fba-344a6eca8146
caps.latest.revision: 6
author: SusanneWindfeldPedersen
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# PasteIsValid Property
Sets whether inserting records into this table using the paste command is enabled.  
  
## Applies To  
 Tables  
  
## Property Value  
 **True** if you want to allow insert by pasting; otherwise, **false**. The default value is **true**.  
  
## Remarks  
 If records are usually inserted in the table through an external code unit function, set the PasteIsValid property equal to **false**.  
  
 The [OnInsert Trigger](../triggers/devenv-oninsert-trigger.md) of the table is executed when a record is inserted by pasting.  
  
## See Also  
 [OnInsert Trigger](../triggers/devenv-oninsert-trigger.md)