---
title: "AccessByPermission Property"
ms.custom: na
ms.date: 06/07/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 72602cd4-853f-4bca-8fd9-b33c206a593b
caps.latest.revision: 12
author: SusanneWindfeldPedersen
---
# AccessByPermission Property
Sets a value for a table field or UI element that determines the permission mask for an object that a user must have to see and access the related page fields or UI element in the client. The UI element will be removed at runtime if the user does not have permissions to a certain object as specified in the **Access By Permission** window.

 All types of UI elements will be removed if they relate to an object to which the user does not have the required permissions:  

-   Fields on pages, including FactBoxes  

-   Actions on pages, including toolbars and navigation panes  

-   Page parts, such as **Lines** FastTabs  

<!--
> [!NOTE]  
>  To use this property, the **UI Elements Removal** field in the [!INCLUDE[nav_admin](includes/nav_admin_md.md)] must be set to **LicenseFile** or **LicenseFileAndUserPermissions**. For more information, see [How to: Specify When UI Elements Are Removed](How-to--Specify-When-UI-Elements-Are-Removed.md).  
-->

## Applies To  

-   Fields in tables (affecting all related fields on pages)  

-   Fields on pages  

-   Actions on pages  

-   MenuSuite items  

-   Page parts, such as a **Lines** FastTab  

## Property Value  
 When you choose the **AssistEdit** button, the **Access By Permission** window opens. Fill the fields as described in the following table.  

|Table field|Description|  
|---------------------------------|---------------------------------------|  
|**Object Type**|Specify the type of object to which permission is required to display the UI element.|  
|**Object ID**|Specify the object to which permission is required to display the UI element.|  
|**Read**|Specify if Read permission is required to display the UI element.|  
|or **Insert**|Specify if Insert permission is required to display the UI element.|  
|or **Modify**|Specify if Modify permission is required to display the UI element.|  
|or **Delete**|Specify if Delete permission is required to display the UI element.|  
|or **Execute**|Specify if Execute permission is required to display the UI element.|  

> [!NOTE]  
>  If multiple permissions are selected, then one or the other applies.  


## See Also  
 [Properties](devenv-properties.md)