---
title: "How to: Set Up a Local Language for the ADCS Web Service"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a3b09603-96ac-409e-aafa-d676e19bab6e
caps.latest.revision: 4
manager: edupont
---
# How to: Set Up a Local Language for the ADCS Web Service
To have messages, including errors, display in the language of the user, you have to modify the ADCS web service codeunit to account for the language setting.  
  
### To specify the local language of ADCS messages  
  
1.  Start the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)], and on the **Tools** menu, choose **Object Designer**.  
  
2.  Choose **CodeUnit**, and from the list, select codeunit 7714. Choose the **Design** button. The C/AL Editor opens.  
  
3.  In the **ProcessDocument** function, add a line of code as highlighted in the following code. The following example demonstrates setting the language code for German.  
  
    ```  
  
              GLOBALLANGUAGE(1031);  
    InputXmlDocument := InputXmlDocument.XmlDocument;  
    InputXmlDocument.LoadXml(Document);  
    ADCSManagement.ProcessDocument(InputXmlDocument);  
    ADCSManagement.GetOutboundDocument(OutputXmlDocument);   
    Document := OutputXmlDocument.OuterXml;  
    ```  
  
## See Also  
 [Configuring Automated Data Capture System](Configuring-Automated-Data-Capture-System.md)