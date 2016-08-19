---
title: "Customizing Report Layout Implementation in Codeunit 1"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 095b6c75-5ad6-4145-abcd-f5baea6f5b0d
caps.latest.revision: 11
manager: edupont
---
# Customizing Report Layout Implementation in Codeunit 1
Reports can be run directly from the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] client or from C\/AL code by calling the RUN, SAVEASWORD, SAVEASPDF, or SAVEASEXCEL functions. When a report is run, the application calls the following functions in codeunit 1 to determine which report layout to use on the report.  
  
-   [HasCustomLayout Function](../dynamics-nav/HasCustomLayout-Function.md)  
  
-   [MergeDocument Function](../dynamics-nav/MergeDocument-Function.md)  
  
-   [ReportGetCustomRdlc Function](../dynamics-nav/ReportGetCustomRdlc-Function.md)  
  
 These functions determine how to handle custom Word and RDLC layouts that are used on the report, which are stored in table **9650 Report Layouts**. You can customize the report layout implementation by modifying the C\/AL code of these functions in codeunit 1.  
  
## Function Call Flow  
 To use the correct report layout for a report at run time, the report layout functions in codeunit 1 are called according to following flow.  
  
-   Before the [OnPreReport Trigger](../dynamics-nav/OnPreReport-Trigger.md) trigger is invoked, the application calls the **HasCustomLayout** function.  
  
     The **HasCustomLayout** function determines whether the report is currently set up to use a custom RDLC layout or Word layout, and then calls one of the following functions:  
  
    -   If the report is currently set up to use a custom RDLC layout, then the **ReportGetCustomRdlc** function is called after the [OnPreReport Trigger](../dynamics-nav/OnPreReport-Trigger.md) is invoked.  
  
         This function loads the proper RDLC layout and uses the layout to render the report.  
  
    -   If the report is currently set up to use a custom Word layout, then the **MergeDocument** function is called after the [OnPostReport Trigger](../dynamics-nav/OnPostReport-Trigger.md) is invoked.  
  
         This function loads the proper Word layout and renders the report based on the action from the report request page, such **SaveAsPdf**, **SaveAsWord**, **SaveAsExcel**, **Preview**, or **Print**.  
  
    -   If the report is not currently set up to use a custom Word or RDLC layout, then the built\-in layout is used for the report.  
  
## Modifying the Report Layout Implementation  
 To modify the report layout implementation, you design the implementation and then add C\/AL code to the functions in codeunit 1.  
  
#### To modify codeunit 1  
  
1.  In the [!INCLUDE[nav_dev_long](../dynamics-nav/includes/nav_dev_long_md.md)], on the **Tools** menu, choose **Object Designer**.  
  
2.  In **Object Designer**, choose **Codeunit**, and then choose codeunit 1 **Application Management**.  
  
3.  Add a code to the **HasCustomLayout**, **MergeDocument**, and **ReportGetCustomRdlc** functions.  
  
4.  Save and compile codeunit 1.  
  
## See Also  
 [REPORT.RUN Function](../dynamics-nav/REPORT.RUN-Function.md)   
 [SAVEASWORD Function \(REPORT\)](../dynamics-nav/SAVEASWORD-Function--REPORT-.md)   
 [SAVEASPDF Function \(Report\)](../dynamics-nav/SAVEASPDF-Function--Report-.md)   
 [SAVEASEXCEL Function \(Report\)](../dynamics-nav/SAVEASEXCEL-Function--Report-.md)   
 [Designing RDLC Report Layouts](../dynamics-nav/Designing-RDLC-Report-Layouts.md)   
 [Designing Word Report Layouts](../dynamics-nav/Designing-Word-Report-Layouts.md)