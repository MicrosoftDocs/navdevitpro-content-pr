---
title: "How to: Use Event Viewer to Collect and View Trace Events"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: ddd157e5-069a-44c5-b25b-1e90cb0bf1d0
caps.latest.revision: 4
---
# How to: Use Event Viewer to Collect and View Trace Events
This topic describes how to collect and view [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] event trace data in Event Viewer. Trace events are recorded in a **Debug** log for [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] in the **Applications and Services Logs**. By default the **Debug** log is disabled and may also be hidden in the Event Viewer. To collect trace event data, you must enable the **Debug** log.  
  
### To collect and view trace events in Event Viewer  
  
1.  On the computer that is running [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)], start Event Viewer.  
  
     For more information, see [How to Start Event Viewer](http://technet.microsoft.com/en-us/library/gg163894.aspx).  
  
2.  In the console tree, choose **Applications and Services Logs**, **Microsoft**, **DynamicsNAV**, and then **Server**.  
  
3.  If the **Debug** log is not shown under **Server**, then on the **View** menu, select **Show Analytic and Debug Logs**.  
  
4.  Select the **Debug** log, and then on the **Actions** menu, choose **Enable Log**.  
  
    > [!NOTE]  
    >  Depending on the number of events, you might have to increase the maximum size of the log. The default value is 1028 KB. For more information, see [Set Maximum Log Size](http://go.microsoft.com/fwlink/?LinkID=517563).  
  
 [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] trace events will now be recorded in the **Debug** log. For a list and description of trace events, see [Microsoft Dynamics NAV Server Trace Events](../dynamics-nav/Microsoft-Dynamics-NAV-Server-Trace-Events.md).  
  
## See Also  
 [Monitoring Microsoft Dynamics NAV Server Event Traces](../dynamics-nav/Monitoring-Microsoft-Dynamics-NAV-Server-Event-Traces.md)   
 [Show or Hide Analytic and Debug](http://technet.microsoft.com/en-us/library/cc766275.aspx)   
 [Enable Analytic and Debug Logs](http://technet.microsoft.com/en-us/library/cc749492.aspx)