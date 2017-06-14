---
title: "RowSpan Property"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 45bd8abe-360f-4cb1-98f7-c91c086a7723
caps.latest.revision: 9
manager: 
---
# RowSpan Property
Sets the number of rows that a field spans in a GridLayout control.  
  
## Applies to  
 Field controls that are in a GridLayout control on a page.  
  
## Property Values  
 An integer that specifies the number of rows to span the field.  
  
## Remarks  
 When you set a field to span several rows, then the field occupies the cells in the rows below it and existing fields in the occupied cells are moved to the right. For example, the following illustration shows a GridLayout control that consists of four fields arranged in two rows.  
  
 ![GridLayout of 4 fields in 2 rows and 2 columns](media/NAVGridLayout2rX2c.png "NAVGridLayout2rX2c")  
  
 If you set Field 1 to span two rows, then the following layout is displayed:  
  
 ![GridLayout showing row span](media/NAVGridLayoutRowSpan.png "NAVGridLayoutRowSpan")  
  
> [!IMPORTANT]  
>  The RowSpan property is not supported by the [!INCLUDE[nav_web](../includes/nav_web_md.md)]. If the page displays in the [!INCLUDE[nav_web](../includes/nav_web_md.md)], then the property is ignored and the field will not span any rows.  
  
## See Also  
 [How to: Arrange Fields in Rows and Columns Using the GridLayout Control](How-to--Arrange-Fields-in-Rows-and-Columns-Using-the-GridLayout-Control.md)