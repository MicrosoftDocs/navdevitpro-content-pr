---
title:"Hiding User Interface Elements Based on Application Area"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 2e3cac9e-20b5-467b-9602-df8a42fb5d79
caps.latest.revision: 2
manager: edupont
---
# Hiding User Interface Elements Based on Application Area
You can develop your application so that certain user interface elements do not appear in the client based on the application area to which they belong. These elements include page fields and actions, report request page fields, and Department items.  
  
 The full implementation of the application areas includes the following processes.  
  
## Application Area Definitions  
 Application areas are defined in table **9178 Application Areas**. Currently there are several predefined areas, including Foundation, Fixed Assets, Jobs, CRM, and more.  
  
## Control Tagging  
 The following controls include the ApplicationArea property:  
  
1.  **Field** control on pages.  
  
2.  **Action** control on pages  
  
3.  **Field** control on report request pages.  
  
4.  **Items** control in a MenuSuites.  
  
 You use the property to assign one or more application areas to the controls. For more information, see [ApplicationArea Property](ApplicationArea-Property.md).  
  
## Application Area Activation  
 To activate the application areas, you use a call to the APPLICATIONAREA function. The function specifies which application areas to active for the current session. I