---
title:"How to: Add a Global Variable to a Codeunit"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 77c8278e-3355-4a09-9de3-192911618010
caps.latest.revision: 11
---
# How to: Add a Global Variable to a Codeunit
To add a global variable to a codeunit, use the following procedure.  
  
### To add a global variable  
  
1.  Open the **C\/AL Editor**, choose **View**, and then choose **C\/AL Globals**.  
  
    > [!NOTE]  
    >  For more information about how to open the C\/AL Editor, see [How to: Modify an Existing Codeunit](../Topic/How%20to:%20Modify%20an%20Existing%20Codeunit.md).  
  
2.  In the **C\/AL Globals** window, choose the **Variables** tab.  
  
3.  Enter a name and select a data type.  
  
     If the data type that you select corresponds to an application object, you must also select a subtype, that is, the name of a specific object in the database.  
  
     If you select **OCX**, **Automation**, or **DotNet**, then you must add a subtype. For more information, see the following topics:  
  
    -   [Extending Microsoft Dynamics NAV Using COM](Extending-Microsoft-Dynamics-NAV-Using-COM.md)  
  
    -   [Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability](Extending-Microsoft-Dynamics-NAV-Using-Microsoft-.NET-Framework-Interoperability.md)  
  
     If you select text or code, you must define a length for the variable. The default length is 10 characters for code and 30 characters for text.  
  
## See Also  
 [Codeunits](Codeunits.md)