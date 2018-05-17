---
title: "RunPageOnRec Property"
ms.custom: na
ms.date: 06/15/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: b453e896-1467-4123-ab2e-1bbce78ed7bd
caps.latest.revision: 8
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# RunPageOnRec Property
Sets the same record on the page you launch from this control as is already displayed on the current page.  
  
## Applies To  
  
-   Page actions  
  
## Property Value  
 **True** if the current record on the page that you will launch from this control is displayed; otherwise, **false**. The default is **false**.  
  
## Remarks  
 For example, suppose the current page is the sales order and you are providing a way to see the sales statistics for the current customer. You would select RunObject in the PushAction property and use the [RunObject Property](devenv-runobject-property.md) to run the sales statistics page. In this property you could select Yes to display the same record on both pages.  
  
## See Also  
 [RunPageView Property](devenv-runpageview-property.md)   
 [RunPageLink Property](devenv-runpagelink-property.md)