---
title: "How to: Create a Report"
description: "Describes the steps involved in creating a report layout."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

# How to: Create a Report Layout
When you create a new report, there are two things you have to think about; first, you define the report dataset of data items and columns, then you can design the report layout. The prerequisite for the next steps, is that you have already created a report object. For more information, see [Report Object](newdev-report-object.md).

1. First, you must define the report object
2. Publish the report object to the server by pressing F5.
3. Open Dynamics NAV, and then search for Custom Report Layouts
4. Create a new report layout, make sure to check the Insert Word Layout check box.
5. Export the layout of the report.
6. Save the Word layout to the VS code project and open it.
7. Open the layout in Word

Make sure that the Developer tab exists - setting in Word, Developer ribbon tab.
8. In the Custom XML part, locate the report, open the layout.
9. Drag elements onto the document, and save the report layout when you are done.
10. In Visual Studio Code, make sure to add the properties WordLayout with the name of the layout file, and DefaultLayout set to Word. 
11. Either make the report....
12. Press F5 to compile and run the report.


## See Also
[Report Object](newdev-report-object.md)  