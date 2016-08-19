---
title: "Troubleshooting: Client Returns Wrong CLIENTTYPE"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 703de4b4-115c-4d7e-ae80-57761a996fbf
caps.latest.revision: 3
---
# Troubleshooting: Client Returns Wrong CLIENTTYPE
Running, for example, the [!INCLUDE[nav_tablet](../dynamics-nav/includes/nav_tablet_md.md)] and the [!INCLUDE[nav_phone](../dynamics-nav/includes/nav_phone_md.md)] simultaneously in the same browser session will return the same `CLIENTTYPE`.  
  
 If you have implemented code that checks for the `CURRENTCLIENTTYPE`, you must run each of the different clients in separate browser windows to make sure that the correct client type is returned for each of the clients.  
  
## See Also  
 [Troubleshooting: Client Returns Wrong CLIENTTYPE](../Topic/Troubleshooting:%20Client%20Returns%20Wrong%20CLIENTTYPE.md)   
 [Designing for Different Screen Sizes on Tablet and Phone](../dynamics-nav/Designing-for-Different-Screen-Sizes-on-Tablet-and-Phone.md)   
 [CURRENTCLIENTTYPE Function](../dynamics-nav/CURRENTCLIENTTYPE-Function.md)   
 [DEFAULTCLIENTTYPE Function](../dynamics-nav/DEFAULTCLIENTTYPE-Function.md)