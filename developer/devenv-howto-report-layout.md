---
title: "How to: Create a Report"
description: "Describes the steps involved in creating a report layout."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/13/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# How to: Create a Report Layout
When you create a new report for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], there are two things you have to think about; defining the report dataset of data items and columns, and then designing the report layout. The prerequisite for the next steps, is that you have already created a report object. For more information, see [Report Object](devenv-report-object.md).

1. Define the report object as shown in [Report Object](devenv-report-object.md)
2. Publish the report object to the server by pressing F5.
3. Open Dynamics NAV, and then search for **Custom Report Layouts**.
4. Create a new report layout; make sure to check the **Insert Word Layout** check box.
5. Export the layout of the report.
6. Save the Word layout to the VS code project and open the layout in Word.
7. In Word, edit the layout using the **XML Mapping Pane** on the **Developer** tab. If you do not already see the Developer tab, go to **Options**, then **Customize Ribbon**, and in the **Main tabs** section, select the **Developer** check box.
8. In Word, in the **Custom XML part**, locate the report, and then open the layout.
9. Drag elements onto the document, and save the report layout when you are done.
10. Back in Visual Studio Code, make sure to add the properties ```WordLayout``` set to the name of the layout file, and the ```DefaultLayout``` property set to **Word**.
11. Press F5 to compile and run the report.


## See Also
[Report Object](devenv-report-object.md)  
