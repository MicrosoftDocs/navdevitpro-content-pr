---
title: "Managing Report Layouts in Dynamics NAV"
author: edupont04
ms.custom: na
ms.date: 10/21/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
manager: edupont
---

## Managing Report Layouts
A report layout controls content and format of the report, including which data fields of a report dataset appear on the report and how they are arranged, text style, images, and more. From the [!INCLUDE[navnow](includes/navnow_md.md)] clients, you can change which layout is used on a report, create new layout, or modify the existing layouts.  

## About Report Layouts
A report layout is a document that acts as a template that defines the appearance of a [!INCLUDE[navnow](includes/navnow_md.md)] report when viewing, printing, or saving the report. In particular, a report layout sets up the following:  

-   The label and data fields to include from the dataset of the [!INCLUDE[navnow](includes/navnow_md.md)] report.  

-   The text format, such as font type, size and color.  

-   The company logo and its position.  

-   General page settings, such as margins and background images.

### Built\-in and Custom Report Layouts  
 Your [!INCLUDE[navnow](includes/navnow_md.md)] application includes several *built\-in layouts*. Built\-in layouts are predefined layouts that are designed for specific reports. [!INCLUDE[navnow](includes/navnow_md.md)] reports will have a built\-in layout as either an RDLC report layout, Word report layout, or in some cases both. You cannot modify a built\-in report layout from the [!INCLUDE[navnow](includes/navnow_md.md)] client but you use them as a starting point for building your own custom report layouts.  

*Custom layouts* are report layouts that you design to change the appearance of a report. You typically create a custom layout based on a built\-in layout, but you can create them from scratch or from a copy of an existing custom layout. Custom layouts enable you to have multiple layouts for the same report, which you switch among as needed. For example, you can have different layouts for each [!INCLUDE[navnow](includes/navnow_md.md)] company, or you can have different layouts for the same company for specific occasions or events, like a special campaign or holiday season.   

##  Word Report Layout Overview  
 A Word report layout is a based on Word document \(.docx file type\). Word report layouts enable you to design report layouts by using Microsoft Word. A Word report layout determines the report's content \- controlling how that content elements are arranged and how they look. A Word report layout document will typically use tables to arrange content, where the cells can contain data fields, text, or pictures.  

Showing the gridlines is useful when you are editing the Word report layout so that you can see table cell boundaries. However, you should hide the gridlines when you are finished editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.  

> [!NOTE]  
>  Images that are based on a field in the report dataset, which means they are defined in a content control, cannot be displayed when you edit the layout in Word. They will appear in the report when it is run.  

The label and data fields are defined by *content controls*. Content controls act as placeholders for the actual report data. In the Word report layout document, the content controls only include a reference to a field in the report dataset.  

## RDLC Layout Overview  
 RDLC layouts are based on client report definition layouts \(.rdlc or .rdl file types\). These layouts are created and modified by using SQL Server Report Builder. The design concept for RDLC layouts is similar to Word layouts, where the layout defines the general format of the report and determines the fields from the dataset to include. Designing RDLC layouts is more advanced than Word layouts.  

## Creating layouts
By default, a report will have a built\-in report layout, which can be either an RDLC report layout or Word report layout, or both. You cannot modify built\-in layouts. However, you can create your own custom layouts that enable you to change the appearance of report when it is viewed, printed or saved. You can create multiple custom report layouts for the same report, and then switch the layout that is used by a report as needed.  

To create a custom layout, you can either make a copy of an existing custom layout or add a new custom layout, which in most cases is based on a built\-in layout. When you add a new custom layout, you can choose to add an RDLC report layout type, Word report layout type, or both. The new custom layout will automatically be based on the built\-in layout for the report if one is available. If there is no built\-in layout for the type, then a new blank layout is a created, which you will have to modify and design from scratch.

 A [!INCLUDE[navnow](includes/navnow_md.md)] report can be set up with multiple report layouts, which you can switch among as required. You can use one of the built\-in report layouts or you can create custom report layouts and assign them to your reports as needed.  

 There are two types of report layouts that you can use on reports, *Word* and *RDLC*.  

## See Also
[Designing Report Layouts from the Microsoft Dynamics NAV Development Environment](Designing-Report-Layouts-from-the Microsoft-Dynamics-NAV-Development-Environment.md)  
[How to: Change Which Layout is Currently Used on a Report](How-to--Change-Which-Layout-is-Currently-Used-on-a-Report.md)  
