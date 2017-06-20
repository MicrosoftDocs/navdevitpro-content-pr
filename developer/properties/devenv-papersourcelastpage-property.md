---
title: "PaperSourceLastPage Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 1947a79f-ea51-4e9a-b814-0d126ffffbca
caps.latest.revision: 8
author: SusanneWindfeldPedersen
---
# PaperSourceLastPage Property
Specifies which paper source to use when printing the last page of the report.  
  
## Applies To  
 Reports  
  
## Remarks  
 In the **Report – Properties** window, in the **PaperSourceLastPage** field, choose the paper source. The list contains 13 standard trays and 16 printer-specific trays. It is based on information in the fin.stx file.  
  
 If the printer that is used for this report does not support the specified paper source, then the printer uses the default tray that is specified by the printer driver.  
  
 If you do not specify a value for the **PaperSourceLastPage** property, then the printer uses the tray that is specified in the [PaperSourceDefaultPage Property](devenv-papersourcedefaultpage-property.md).  
  
 If you do not specify a value for either the **PapersourceLastPage** property or the PaperSourceDefaultPage property, then the printer uses the default printer tray that is defined for the operating system.  
  
 The printer specific trays that are contained in the list are intended for use with printers that have other paper sources than the ones listed in the property.  
  
 The settings in the **Print** and **Page Setup** dialog boxes override the value that is specified for the **PaperSourceLastPage** property.  
  
 You can use the **GetPaperTrayForReport** function in codeunit 1, **Application Management**, to set the paper tray from AL code. This gives you runtime control over paper tray selection for first, last, and default pages in a report.  
  
## See Also  
 [PaperSourceDefaultPage Property](devenv-papersourcedefaultpage-property.md)   
 [PaperSourceFirstPage Property](devenv-papersourcefirstpage-property.md)   
 [How to: Add GetPaperTrayForReport Procedure in Codeunit 1](How-to--Add-GetPaperTrayForReport-Procedure-in-Codeunit-1.md)