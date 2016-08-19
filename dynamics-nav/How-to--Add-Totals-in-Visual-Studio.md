---
title: "How to: Add Totals in Visual Studio"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b300cdb1-0163-4c61-a7bf-e0fb460b2b70
caps.latest.revision: 11
manager: edupont
---
# How to: Add Totals in Visual Studio
Totals are an important element of creating useful reports. By totaling data, your report can help the user analyze data that is not otherwise readily available. For example, totals provide a useful overview of the total sales for a given month. Reports can be created with [!INCLUDE[navnowlong](includes/navnowlong_md.md)] and later designed using Visual Studio. This topic describes how to add totals to a report in Visual Studio.  
  
### To add totals in Visual Studio  
  
1.  In Visual Studio, select the total field on the report and on the shortcut menu, select **Expression**.  
  
2.  In the **Expression** window, enter the following expression: `=SUM(Fields!<tablefield>.Value)`  
    For example: `=SUM(Fields!Sales_Line_Amount.Value)`  
  
3.  Save the report in Visual Studio.  
  
4.  Compile and save the report in [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. A message informs you that the .rdlc file for this report has changed and asks if you want to load the changes. Choose **Yes** to save the changes in the database.  
  
## See Also  
 [Walkthrough: Designing a Report with Images, Interactive Sorting, and Visibility Toggle](../Topic/Walkthrough:%20Designing%20a%20Report%20with%20Images,%20Interactive%20Sorting,%20and%20Visibility%20Toggle.md)   
 [Walkthrough: Creating a Link from a Report to a Page](../Topic/Walkthrough:%20Creating%20a%20Link%20from%20a%20Report%20to%20a%20Page.md)   
 [How to: Make a Report Available from a Page](../Topic/How%20to:%20Make%20a%20Report%20Available%20from%20a%20Page.md)