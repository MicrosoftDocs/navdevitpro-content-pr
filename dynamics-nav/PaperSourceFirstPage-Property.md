---
title: "PaperSourceFirstPage Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: c927f9e3-e6ef-4046-b0d8-7d38e67a50be
caps.latest.revision: 13
manager: edupont
---
# PaperSourceFirstPage Property
Specifies which paper source to use when printing page one of the report.  
  
## Applies To  
 Reports  
  
## Remarks  
 In the **Report – Properties** window, in the **PaperSourceFirstPage** field, choose the paper source. The list contains 13 standard trays and 16 printer-specific trays. It is based on information in the fin.stx file.  
  
 If the printer that is used for this report does not support the specified paper source, then the printer uses the default tray that is specified by the printer driver.  
  
 If you do not specify a value for the **PaperSourceFirstPage** property, then the printer uses the tray that is specified in the [PaperSourceDefaultPage Property](PaperSourceDefaultPage-Property.md).  
  
 If you do not specify a value for either the **PaperSourceFirstPage** property or the [PaperSourceDefaultPage Property](PaperSourceDefaultPage-Property.md), then the printer uses the default printer tray that is defined for the operating system.  
  
 The printer specific trays that are contained in the list are intended for use with printers that have other paper sources than the standard ones that are listed in the property.  
  
 The settings in the **Print** and **Page Setup** dialog boxes override the value that is specified for the **PaperSourceFirstPage** property.  
  
 You can use the **GetPaperTrayForReport** function in codeunit 1, **Application Management**, to set the paper tray from C/AL code. This gives you runtime control over paper tray selection for first, last, and default pages in a report.  
  
## See Also  
 [PaperSourceDefaultPage Property](PaperSourceDefaultPage-Property.md)   
 [PaperSourceLastPage Property](PaperSourceLastPage-Property.md)   
 [How to: Add GetPaperTrayForReport Procedure in Codeunit 1](How-to--Add-GetPaperTrayForReport-Procedure-in-Codeunit-1.md)