---
title: "ShowPrintStatus Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 3c256f96-bbef-4138-9b68-ae7aab80e3c8
caps.latest.revision: 9
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# ShowPrintStatus Property
Sets whether a window that shows the printing status of a report when it is run is displayed.  
  
## Applies To  
 Reports  
  
## Property Value  
 **True** if a status window is shown; otherwise, **false**. The default is **true**.  
  
## Remarks  
 Apart from showing the progress of the report, the window also contains a **Cancel** button that will cause the processing and printing of the report to terminate, when clicked. If you set ShowPrintStatus to **false**, the user will not be able to stop the report prematurely.  
  
 If the [ProcessingOnly Property](devenv-processingonly-property.md) is **true**, there will be no status dialog box, even if ShowPrintStatus is **true**. If you need a status dialog box, you must create one yourself.  
  
## See Also  
 [ProcessingOnly Property](devenv-processingonly-property.md)