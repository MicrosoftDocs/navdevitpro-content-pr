---
title: "Monitoring Microsoft Dynamics NAV Server Events in the Windows Event Log"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: da2944cc-063d-452d-968c-23b90c547600
caps.latest.revision: 28
---
# Monitoring Dynamics NAV Server Events Using Event Viewer and PowerShell
Events that occur on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instances are recorded in event logs on the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)]. You can view the events by using Event Viewer or Windows PowerShell as described in this topic.  
  
##  <a name="ViewEventViewer"></a> Viewing Dynamics NAV Events by Using Event Viewer  
Events that occur on [!INCLUDE[nav_server](includes/nav_server_md.md)] instances are recorded in the event channels specific to Dynamics NAV and also in the general Windows Application log. Event channels provide a way to collect and view events from a specific event trace provider. This differs from the Windows Application log which contains system-wide events from multiple publishers \(applications and components\).   

### Dynamics NAV channel logs
In the Event Viewer console tree, open **Applications and Services Logs** > **Microsoft** > **DynamicsNAV**.
 
#### Server folder

The **Server** folder contains events from the event trace provider called **Microsoft-DynamicsNAV-Server**. The events are recorded in the following logs:  
  
|Log|Description|  
|---------|-----------------|  
|Admin|Includes events that target end users and IT administrators. These events typically indicate a problem that requires action to resolve the problem. An example of an admin event is a tenant database failing to mount on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. For a list and description of the events that can occur, see [Microsoft Dynamics NAV Server Events](Microsoft-Dynamics-NAV-Server-Events.md). <br /><br /> For a list and description of these events, see [Dynamics NAV Server Admin and Operational Events](Microsoft-Dynamics-NAV-Server-Events.md).|  
|Operational|Includes events that provide information about an operation that occurred on [!INCLUDE[nav_server](includes/nav_server_md.md)] instances. These events are typically ordinary operating events that do not require any action but can be used to analyze and diagnose a problem. An example of an operational event is the shutting down of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.<br /><br /> For a list and description of these events, see [Dynamics NAV Server Admin and Operational Events](Microsoft-Dynamics-NAV-Server-Events.md).|  
|Debug|Includes trace events that occur on [!INCLUDE[nav_server](includes/nav_server_md.md)] instances. For more information about the different trace events and others ways to monitor them, see [Microsoft Dynamics NAV Server Trace Events](Microsoft-Dynamics-NAV-Server-Trace-Events.md) and [Monitoring Microsoft Dynamics NAV Server Event Traces](Monitoring-Microsoft-Dynamics-NAV-Server-Event-Traces.md).<br /><br /> **Note:** In Event Viewer, this log is hidden and disabled by default. For information about how to show and enable this log, see [How to: Use Event Viewer to Collect and View Trace Events](How-to--Use-Event-Viewer-to-Collect-and-View-Trace-Events.md).|  

#### Common folder 

The **Common** folder contains telemetry events from the event trace provider called **Microsoft-DynamicsNAV-Common**. This folder contains strictly telemetry events, which have IDs 700-706.. The telemtry events are recorded in the following logs:  
      
|Log|Description|  
|---------|-----------------|  
|Admin|Includes custom telemetry trace events that are emitted from the application. These are events that are sent by [SENDTRACETAG function](sendtracetag-function.md) calls from inside the application. For more information, see [Instrumenting av Application for Telemetry](instrumenting-application-for-telemetry.md)].<br /><br /> **Note** The [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance includes a configuration setting called **Diagnostic Trace Level** (`TraceLevel` in the customsettings.config file) that enables you to specify the lowest severity level of telemetry events to be recorded in the event log, or even turn off telemetry event logging altogether. If you do not see the expected events, then verify the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance configuration with an administrator. For information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md#General).|  
|Operational|Not applicable.|  
|Debug|Includes system telemetry trace events that occur.<br /><br /> **Note:** In Event Viewer, this log is hidden and disabled by default. For information about how to show and enable this log, see [How to: Use Event Viewer to Collect and View Trace Events](How-to--Use-Event-Viewer-to-Collect-and-View-Trace-Events.md).|  
  
### Application log  
  
The Application log includes admin and operational type events \(errors, warnings, and information messages\) that occur on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  
  
To view the **Application** log, in the console tree, choose **Windows Logs**, **Applications**.  
  
The events in this log are the same events that are recorded in the **Admin** and **Operation** logs in the **DynamicsNAV** > **Server** channel. Therefore, you can consider the **Application** log to be a secondary log for these events. Unless you are using System Center Operations Manager to monitor [!INCLUDE[nav_server](includes/nav_server_md.md)] events, you can disable logging [!INCLUDE[nav_server](includes/nav_server_md.md)] events to the Windows Application log and rely on **Applications and Services Logs** instead. For more information, see [How to: Disable Logging Events to the Windows Application Log](How-to--Disable-Logging-Events-to-the-Windows-Application-Log.md).  
  
> [!NOTE]  
>  Trace events are not included in this log.  
  
For more information about how to use Event Viewer, see [Windows Event Viewer.](http://go.microsoft.com/fwlink/?LinkID=314067)  
  
### Filtering Dynamics Server Events in Event Viewer  
By default, the [!INCLUDE[nav_server](includes/nav_server_md.md)] logs contain events of all levels \(error, warning, and information\) for all [!INCLUDE[nav_server](includes/nav_server_md.md)] instances. You can use the filtering functionality that is available in Event Viewer to display only [!INCLUDE[nav_server](includes/nav_server_md.md)] instance events that meet specific criteria. For example, if you have several [!INCLUDE[nav_server](includes/nav_server_md.md)] instances, you can filter logs to show only events from a specific [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. For more information, see the following example.  
  
 **Example**  
  
 Your [!INCLUDE[nav_server](includes/nav_server_md.md)] is running several instances that are configured with multiple tenants. In Event Viewer, you want to view only errors that occurred in the last 24 hours on the tenant *MyTenant1* of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance *MyNavServerInstance1*.  
  
##### To filter the event log  
  
1.  For example, in the console tree of Event Viewer, choose **Applications and Services Logs** > **Microsoft** > **DynamicsNAV** > **Server**.  
  
2.  Select the **Admin** log.  
  
3.  In the **Action** pane, choose **Filter Current Log**.  
  
     The **Filter Current Log** window opens.  
  
4.  On the **Filter** tab, set the **Logged** drop-down list to **Last 24 hours**.  
  
5.  In the **Error Level** section, select the **Error** check box.  
  
6.  Choose the **XML** tab.  
  
     XML similar to the following is displayed:  
  
    ```  
    <QueryList>  
      <Query Id="0" Path="Microsoft-DynamicsNAV-Server/Admin">  
        <Select Path="Microsoft-DynamicsNAV-Server/Admin">  
          *[System[(Level=2) and TimeCreated[timediff(@SystemTime) <= 604800000]]]  
      </Query>  
    </QueryList>  
    ```  
  
     `Microsoft-DynamicsNAV-Server` indicates that [!INCLUDE[nav_server](includes/nav_server_md.md)] is the provider of the events in the log.  
  
7.  Select the **Edit** query manually check box, and then choose the **Yes** button.  
  
8.  In the `<Select Path="Microsoft-DynamicsNAV-Server/Admin">` element, after `*[System[(Level=2) and TimeCreated[timediff(@SystemTime) <= 86400000]]]`, add the following lines:  
  
    ```  
    and  
    *[EventData[Data[@Name='tenantId'] and Data  = 'MyTenant1']]  
    and  
    *[EventData[Data[@Name='serverInstanceName'] and Data='MyNavServerInstance1']]  
  
    ```  
  
     The complete XML should look similar to the following XML:  
  
    ```  
    <QueryList>  
      <Query Id="0" Path="Microsoft-DynamicsNAV-Server/Admin">  
        <Select Path="Microsoft-DynamicsNAV-Server/Admin">  
          *[System[(Level=2) and TimeCreated[timediff(@SystemTime) <= 604800000]]]  
          and  
          *[EventData[Data[@Name='tenantId'] and Data  = 'MyTenant1']]  
          and  
          *[EventData[Data[@Name='serverInstanceName'] and Data='MyNavServerInstance1']]  
        </Select>  
      </Query>  
    </QueryList>  
    ```  
  
9. Choose the **OK** button.  
  
 The **Admin** log displays only errors that occurred in the last 24 hours on tenant *Tenant1* and [!INCLUDE[nav_server](includes/nav_server_md.md)] instance *MyNavServerInstance1*. The applied filter can be removed. Alternatively, you can save it as a custom view. For more information about filtering in Event Viewer, see [Filter Displayed Events](http://go.microsoft.com/fwlink/?LinkID=516925) and [Advanced XML filtering in the Windows Event Viewer](http://go.microsoft.com/fwlink/?LinkID=516924).  
  
##  <a name="ViewEventsWinPS"></a> Viewing Microsoft Dynamics NAV Server Events by Using Windows PowerShell  
 You can use the Get-WinEvent cmdlet of Windows PowerShell to view [!INCLUDE[nav_server](includes/nav_server_md.md)] instance events and trace events in the event logs and event tracing log files on the [!INCLUDE[nav_server](includes/nav_server_md.md)] computer. The Get-WinEvent cmdlet retrieves the same events that can be viewed in the [!INCLUDE[nav_server](includes/nav_server_md.md)] logs \(Admin, Operational, and Debug\) in the **Applications and Services Logs** of Event Viewer.  
  
 The Get-WinEvent cmdlet includes several parameters that enable you to filter the events that you view and specify how the events are displayed. Windows PowerShell enables you can create scripts that perform complex operations for extracting and displaying specific event data. For more information about the Get-WinEvent cmdlet, see [Get-WinEvent](http://go.microsoft.com/fwlink/?LinkID=513535).  
  
 For more information about installing and getting started with Windows PowerShell, see [Getting Started with Windows PowerShell](http://go.microsoft.com/fwlink/?LinkID=254637).  
  
### To use the Get-WinEvent Cmdlet to view [!INCLUDE[nav_server](includes/nav_server_md.md)] events  
  
1.  If you want to view events in the [!INCLUDE[nav_server](includes/nav_server_md.md)]**Debug** log, ensure that the log is enabled. The **Admin** and **Operational** logs are enabled by default.  
  
     For information, see [To enable the Microsoft Dynamics NAV Server Debug Log from Windows PowerShell](Monitoring-Microsoft-Dynamics-NAV-Server-Events-in-the-Windows-Event-Log.md#EnableLog).  
  
2.  On the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)], start Window PowerShell.  
  
     For more information, see [Starting Windows PowerShell](http://go.microsoft.com/fwlink/?LinkID=513794).  
  
3.  At the command prompt, enter the `Get-WinEvent` command. The following table provides some simple example commands.  
  
    |To view|Command|  
    |-------------|-------------|  
    |Events in the all **DynamicsNAV** > **Server** logs|`Get-WinEvent -ProviderName Microsoft-DynamicsNav-Server`|
    |Events in the all **DynamicsNAV** > **Common** logs|`Get-WinEvent -ProviderName Microsoft-DynamicsNav-Common`|  
    |Events in the **DynamicsNAV** > **Server** > **Admin** log|`Get-WinEvent -LogName Microsoft-DynamicsNav-Server/Admin`|
    |Events in the **DynamicsNAV** > **Common** > **Admin** log|`Get-WinEvent -LogName Microsoft-DynamicsNav-Common/Admin`|  
    |Events in the [!INCLUDE[nav_server](includes/nav_server_md.md)] Operational log|`Get-WinEvent -LogName Microsoft-DynamicsNav-Server/Operational`|  
    |Trace events in the [!INCLUDE[nav_server](includes/nav_server_md.md)] Debug log|`Get-WinEvent -LogName Microsoft-DynamicsNav-Server/Debug -Oldest`|  
  
###  <a name="EnableLog"></a> To enable the Dynamics NAV Server Debug Log from Windows PowerShell  
  
1.  On the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)], start Window PowerShell as an administrator.  
  
2.  At the command prompt, enter the following command:  
  
    ```  
    wevtutil.exe set-log “Microsoft-DynamicsNav-Server/<Debug>” /q:true /e:true  
    ```  
  
> [!TIP]  
>  You can also enable the Debug log from Event Viewer. For more information, see [Enable Analytic and Debug Logs](http://technet.microsoft.com/en-us/library/cc749492.aspx).  
  
### Filtering [!INCLUDE[nav_server](includes/nav_server_md.md)] Events  
 You can filter the events that you view in a [!INCLUDE[nav_server](includes/nav_server_md.md)] log by setting the *FilterXpath* parameter of the Get-WinEvent cmdlet. The following examples illustrate how you can use the *FilterXpath* parameter to filter the [!INCLUDE[nav_server](includes/nav_server_md.md)] events.  
  
 #### Example 1  
  
 The following example uses the Get-WinEvent cmdlet to view errors in the [!INCLUDE[nav_server](includes/nav_server_md.md)] Admin log for the tenant *MyTenant1* on the server instance *MyNavServerInstance1*.  
  
```  
Get-WinEvent -LogName 'Microsoft-DynamicsNav-Server/Admin' -FilterXPath "*[System[(Level=2)]] and *[EventData[Data[@Name='tenantId'] and (Data = 'MyTenant1')]] and *[EventData[Data[@Name='serverInstanceName'] and Data='MyNavServerInstance1']]" | Format-List -Property Message-  
```  
  
#### Example 2  
  
 The following is an example of a Windows PowerShell script that you can create and run to view trace events in the [!INCLUDE[nav_server](includes/nav_server_md.md)] Debug log. The script returns the start and stop C/AL function trace events that take more than four seconds to execute on the tenant *MyTenant1* of the server instance *MyNavServerInstance1*.  
  
```  
$maxAllowedSeconds = 4  
  
$xPath = "*[System[(EventID = 400 or EventID = 401)]] and " +   
         "*[EventData[Data[@Name='tenantId'] and (Data  = 'MyTenant1')]] and " +  
         "*[EventData[Data[@Name='serverInstanceName'] and Data='MyNavServerInstance1']]"  
  
$events = Get-WinEvent -LogName 'Microsoft-DynamicsNav-Server/Debug' -FilterXPath $xPath -Oldest -MaxEvents 10000  
  
Write-Host "List of AL functions that took more than $maxAllowedSeconds  seconds to execute :" -ForegroundColor DarkYellow  
  
for($i = 0; $i -lt  $events.Length; $i+=2)  
{   
   $seconds = ($events[$i + 1].TimeCreated - $events[$i].TimeCreated).Seconds  
  
   if ($seconds -ge $maxAllowedSeconds )  
   {  
     Write-Host $events[$i].Message `r`n -ForegroundColor Magenta  
   }  
}  
```  
  
 You can create the script by using, for example, Notepad or Windows PowerShell Integrated Scripting Environment \(ISE\). You save the script as .ps1 file type, and then run it from the Windows PowerShell.  
  
## See Also  
 [Monitoring Microsoft Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md)   
 [Microsoft Dynamics NAV Server Trace Events](Microsoft-Dynamics-NAV-Server-Trace-Events.md)   
 [Monitoring Microsoft Dynamics NAV Server](Monitoring-Microsoft-Dynamics-NAV-Server.md)   
 [Monitoring Microsoft Dynamics NAV Server Using Performance Counters](Monitoring-Microsoft-Dynamics-NAV-Server-Using-Performance-Counters.md)   
 [Event Viewer](http://go.microsoft.com/fwlink/?LinkID=314067)