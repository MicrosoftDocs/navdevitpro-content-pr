---
title: "Permissions on Database Objects"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: ab8c997f-b5f8-40b1-913d-0b8906418b41
caps.latest.revision: 11
manager: edupont
---
# Permissions on Database Objects
This section provides an overview of permissions and permission sets in [!INCLUDE[navnowlong](includes/navnowlong_md.md)]  
  
## Permissions  
 If you have been granted permission to read a page, then you can open the page and view the data that it displays. If, however, you do not have write permission, you are not allowed to enter data into this page.  
  
 Sometimes, when you open a page it displays information from several tables. To access this page, you must have permission to view all the data displayed by the page. You might not have permission to read directly from all the tables that the page uses. In this case, you must have indirect permission to read from the tables in question. Having indirect permission to a table means that you cannot open the table and read from it but can only view the data it contains indirectly through another object, such as a page or report, that you have direct permission to access.  
  
 [!INCLUDE[nav_current_short](includes/nav_current_short_md.md)] has a number of standard predefined security permission sets. You can use these permission sets as defined or you can change a permission sets to suit your particular needs. You can also create your own permission sets and assign them the permissions that you want.  
  
### Permissions on Objects  
  
|Permission|Description|  
|----------------|-----------------|  
|Read|You can read this object.|  
|Insert|You can insert data into this object.|  
|Modify|You can modify data in this object.|  
|Delete|You can delete data from this object.|  
|Execute|You can run this object.|  
  
## See Also  
 [Data Security](Data-Security.md)   
 [Business Areas and Granules](Business-Areas-and-Granules.md)   
 [Record-Level Security](Record-Level-Security.md)