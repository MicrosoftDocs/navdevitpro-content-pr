---
title: "PDFFontEmbedding Property"
ms.custom: na
ms.date: 06/14/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 5e251ec0-0bf2-4139-a8a2-cfaca5dae3ad
caps.latest.revision: 6
author: SusanneWindfeldPedersen
---
# PDFFontEmbedding Property
Specifies whether fonts are embedded in PDF files that are generated for reports.  
  
## Applies To  
  
-   Reports  
  
    > [!NOTE]  
    >  This property only applies when the report uses an RDLC report layout at runtime. This property is ignored when a Word report layout is used.  
  
## Property Value  
  
|[!INCLUDE[bp_tableoption](../includes/bp_tableoption_md.md)]|[!INCLUDE[bp_tabledescription](../includes/bp_tabledescription_md.md)]|  
|----------------------------------|---------------------------------------|  
|**Default**|Uses the **Report PDF Embedding** setting of the [!INCLUDE[nav_server](../includes/nav_server_md.md)] instance to determine whether fonts are embedded in PDF files. For more information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md).<br /><br /> This is the default setting.|  
|**False**|Fonts are not embedded in PDF files.|  
|**True**|Fonts are embedded in PDF files.|  
  
## Remarks  
 This property applies when an RDLC report is saved as a PDF under the following circumstances:  
  
-   On the [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] client when the user chooses to save a report as PDF from the report's request page or print preview.  
  
    > [!NOTE]  
    >  This property is ignored when a report is saved as PDF from the print preview in the [!INCLUDE[nav_web](../includes/nav_web_md.md)]. In this case, the [!INCLUDE[nav_server](../includes/nav_server_md.md)] instance setting is always used.  
  
-   On [!INCLUDE[nav_server](../includes/nav_server_md.md)] by the [SAVEAS Method](../methods/devenv-SAVEAS-method.md) or [SAVEASPDF Method \(Report\)](../methods/devenv-SAVEASPDF-method-Report.md).  
  
 Embedding fonts in a PDF of a report makes sure that the PDF will use the same fonts as the original file, regardless of where the PDF is opened and which fonts are installed on the computer. However, embedding fonts can significantly increase the size of the PDF files. By disabling font embedding, you can decrease the size of the report PDF files.  
  
## See Also  
 [Running Reports](Running-Reports.md)