---
title: "Temporary Property (XMLports)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 75932773-71ea-4203-a7ad-3d24d3b79e42
caps.latest.revision: 12
manager: edupont
---
# Temporary Property (XMLports)
Sets whether a temporary table is created to store the records imported using the XMLport.  
  
## Applies To  
 Record variables.  
  
## Remarks  
 If the data that you are importing has a different structure than the table in [!INCLUDE[navnow](includes/navnow_md.md)] that you want to insert it into, you could import the data into a temporary table. The temporary table holds the data in cache without writing it to the database. You can then modify the data before inserting it into the database.