---
title: "Monitoring Microsoft Dynamics NAV Server Events"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d7d57a32-f65e-4b02-bed8-86f1dfbf2fa8
caps.latest.revision: 15
---
# Monitoring Microsoft Dynamics NAV Server Events
You can monitor events on [!INCLUDE[nav_server](includes/nav_server_md.md)] to diagnose conditions and troubleshoot problems that affect operation and performance.  
  
## Event Logging Overview  
 [!INCLUDE[navnow](includes/navnow_md.md)] uses Event Tracing for Windows \(ETW\), which is a subsystem of Windows operating systems. ETW provides a tracing mechanism for events that are raised by an application or service. ETW enables you to use industry standard tools such as Windows Performance Monitor, PerfView, Event Viewer, and Windows PowerShell to dynamically collect data on trace events that occur on the [!INCLUDE[nav_server](includes/nav_server_md.md)].  
  
 Events that occur on [!INCLUDE[nav_server](includes/nav_server_md.md)] instances are recorded in Windows Event logs on the [!INCLUDE[nav_server](includes/nav_server_md.md)] computer. [!INCLUDE[navnowlong](includes/navnowlong_md.md)] uses channels on all events. Event channels provide a way to collect and view events from a specific provider, which in this case is [!INCLUDE[nav_server](includes/nav_server_md.md)], and group the events according to predefined types, such as admin, operational, and debug. For example, in Event Viewer, [!INCLUDE[nav_server](includes/nav_server_md.md)] instance events are collected in the Admin, Operational, and Debug channel logs for [!INCLUDE[nav_server](includes/nav_server_md.md)] in the Applications and Services Logs.  
  
 For more general information about ETW and event channels, see [Event Tracing for Windows](http://go.microsoft.com/fwlink/?LinkID=313939) and [Event Logs and Channels in Windows Event Log](http://go.microsoft.com/fwlink/?LinkID=517298)  
  
## In This Section  
 [Monitoring Microsoft Dynamics NAV Server Events in the Windows Event Log](Monitoring-Microsoft-Dynamics-NAV-Server-Events-in-the-Windows-Event-Log.md)  
  
 [Monitoring Microsoft Dynamics NAV Server Event Traces](Monitoring-Microsoft-Dynamics-NAV-Server-Event-Traces.md)