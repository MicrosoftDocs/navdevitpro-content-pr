---
title: "Running Setup on the Command Line"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: f436d80f-57e7-4399-a93d-52ee4d751ec7
caps.latest.revision: 16
---
# Running Setup on the Command Line
You can run [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup at a command prompt. On the [!INCLUDE[navnow](includes/navnow_md.md)] installation media, Setup.exe is in the root directory.  
  
 After installation, the typical location for Setup.exe on the target computer is:  
  
```  
C:\Program Files (x86)\Common Files\Microsoft Dynamics NAV\90\Setup  
```  
  
 You can use the following options with Setup.exe.  
  
|Setup option|Description|  
|------------------|-----------------|  
|**\/config \<Setup config file\>**|Specifies path and file name information for a [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup configuration file to load.<br /><br /> This is the only required option.|  
|**\/help**|Displays Help about Setup.exe options.|  
|**\/log \<log path\>**|Specifies path and file name information for a Setup log file to be created by Setup. The file must not exist before you run Setup.|  
|**\/quiet**|Specifies that Setup does not display anything on the screen. All configuration information is taken from the specified configuration file.|  
|**\/repair**|Repairs the current installation of [!INCLUDE[navnowlong](includes/navnowlong_md.md)].|  
|**\/uninstall**|Removes the current installation [!INCLUDE[navnowlong](includes/navnowlong_md.md)].|  
  
## See Also  
 [Working with Microsoft Dynamics NAV Setup](Working-with-Microsoft-Dynamics-NAV-Setup.md)   
 [How to: Create or Load a Setup Configuration File](How%20to:%20Create%20or%20Load%20a%20Setup%20Configuration%20File.md)   
 [Editing a Setup Configuration File](Editing-a-Setup-Configuration-File.md)