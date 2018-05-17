---
title: "PreviewMode Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e79b25b8-4582-450b-93e0-5ec01110e9fc
caps.latest.revision: 3
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# PreviewMode Property
Specifies how the report opens when you preview it.  

## Applies To  
 Reports  

## Property Value  

|Value|Description|  
|-----------|-----------------|  
|**Normal**|Specifies that the report opens in the default view mode where you can navigate between entries and so on.|  
|**PrintLayout**|Specifies that the report opens in the print layout mode that shows how the report will print on paper.|  

## Remarks  
 In the **Report – Properties** window, in the **PreviewMode** field, specify how the report must open in preview mode. The default mode can be different to how the report prints on paper. If you want to make sure that users see the report as it will look on paper, choose **PrintLayout**.  

 Regardless of your choice, users can change the display mode in the **Print Preview** window. For example, if you choose the default mode, users can choose the **Print Layout** button. However, if the AL code for the report uses the PREVIEW function to disable printing from the preview, then users cannot change the display mode to print layout.  

## See Also  
<!--
 [Report Design Overview](../devenv-report-design-overview.md)   
 [Designing Reports](../devenv-designing-reports.md)   
 [Printing Reports](../devenv-printing-reports.md) -->  
 [PREVIEW Method (Report)](../methods/devenv-preview-method-report.md)
