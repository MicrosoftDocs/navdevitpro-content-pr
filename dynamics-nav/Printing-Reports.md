---
title: "Printing Reports"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 82a210a7-f42a-4fc2-8d27-d9a8c89bd38c
caps.latest.revision: 19
manager: edupont
---
# Printing Reports
You can specify page settings and page orientation for a printed report from the following UI locations:  
  
- The **Report Properties** dialog box on the client report definition \(RDLC\) report layout in Visual Studio.  
  
- The **Properties** dialog box for the printer.  
  
- The **Print** dialog box that is displayed immediately before you print.  
  
- The **Page Setup** dialog box from the **Print Preview** page in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  
  
  The page settings that are used for the printed report depend on the mode in which you print the report.  
  
  You can use the following modes to print a report:  
  
- Run a report that has the [UseRequestPage Property](UseRequestPage-Property.md) set to **No**, and therefore, does not display a request page.  
  
- Print a report from the request page without previewing the report.  
  
- Print a report from the **Print Preview** page.  
  
  With [!INCLUDE[nav_web](includes/nav_web_md.md)], from the print preview, you can only print to a local printer. To print from the print preview, you must the install a client-side component. For more information, see [Printing Reports from ReportViewer](http://go.microsoft.com/fwlink/?LinkId=225474).  
  
## Specifying Page Settings and Orientation  
 The following table describes how you access each of the dialog boxes in which you can specify page settings and orientation.  
  
|Print mode|To access the **Report Properties** dialog box|To access the **Print** dialog box|To access the **Page Setup** dialog box|  
|----------------|----------------------------------------------------|-------------------------------------------------------------|----------------------------------------|
|Run a report that does not have a request page|When you design the report layout in Visual Studio, on the **Report** menu, choose **Report Properties**.|Cannot access|Cannot access|  
|Print a report from the request page without previewing|When you design the report layout in Visual Studio, on the **Report** menu, choose **Report Properties**.|From the client, on the request page, choose **Print**.|Cannot access|  
|View a preview of a report|When you design the report layout in Visual Studio, on the **Report** menu, choose **Report Properties**.|In the **Print Preview** window, choose the **Print** icon.|In the client, in the **Print Preview** window, choose the **Page Setup** icon.|  
  
## How Printed Report Settings Are Determined  
 The following table describes how the page and orientation settings are determined depending on the mode that you use to print the report.  
  
|Print mode|The printed report paper size, margins and orientation are determined by|
|--------|----------------------------------------------------------------------|
|Printing a Report Without a Request Page|The settings in the **Report Properties** dialog box on the RDLC layout.|  
|Printing a Report From the Request Page |The settings in the **Report Properties** dialog box on the RDLC layout but is overridden if you change the settings in the **Print** dialog box.| 
|Printing a Report From the Print Preview Page|The settings in the **Report Properties** dialog box on the RDLC layout but is overridden if you change the settings in the **Page Setup** dialog box.|

> [!NOTE]
> The values in the **Print** dialog box and in the **Page Setup** dialog box are initially set to the values from the Report Properties dialog box on the RDLC report layout.

> [!NOTE]  
>  In [!INCLUDE[nav2017](includes/nav2017.md)] and subsequent versions, the printed report settings are determined by default to match the **Report Properties** to the current available paper. Therefore, it does no longer refer to the **Printer Properties** if the layout of the report specifies a custom paper size, as it did in earlier versions.
> 
>  To disable this setting and use the [previous](https://docs.microsoft.com/en-us/previous-versions/dynamicsnav-2016/ff477105%28v=nav.90%29) settings, add the following line to the CustomSettings.config file and restart the server to reload configuration:  `<add key="CalculateBestPaperSizeForReportPrinting" value="false" />`.

## See Also  
 [How to: Specify Printer Selection for Reports](How-to--Specify-Printer-Selection-for-Reports.md)   
 [How to: Verify the Paper Size](How-to--Verify-the-Paper-Size.md)   
 [Printing Reports from a Background Session](Printing-Reports-from-a-Background-Session.md)
