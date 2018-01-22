---
title: Developing telemetry into your Dynamics NAV application
description: This topic desscribes how to add code to application objects that enables you to gather telemetry.
ms.custom: na
ms.date: 22/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Instrumenting an Application for Telemetry
This article describes how you can implement custom telemetry trace events in your application for collecting telemetry data. This data can then be collected and visualized for  troubleshooting or analyzing the application against the desired business goals. 

## Telemetry overview
One aspect of event logging is collecting data about how the application and your deployment infrastructure is working in order to diagnose conditions and troubleshoot problems that affect operation and performance. For example, this type of event logging includes [!INCLUDE[nav_server_md](includes/nav_server_md.md)] events and trace events like SQL and AL function traces.

Another aspect of event logging is *telemetry*, which is collecting data about how your application functions and how it is being used in production. Telemetry can tell you about specific activities that users perform within the application in the production enviroment. Telemetry is also useful tool for troubleshooting, especially instances where you are not able to reproduce the conditions experienced by the user or have no access to the user's environment. Telemetry can be divided into different levels or categories, like: telemetry for engineering, telemetry about the business, telemetry for customers

By default, the [!INCLUDE[navnow](includes/navnow_md.md)] application is instrumented to emit several system telemetry trace events that are recorded in the event log. Custom telemetry trace events enable you to send telemetry data from anywhere in the application code. 

## Creating custom telemetry events

To create a custom telemetry event, you use the [SENDTRACETAG function](sendtracetag-function.md) in C/AL code. The SENDTRACETAG function has the following syntax:

```  
SENDTRACETAG(Tag, Category, Verbosity, Message)  
```  

You use the parameters to define the information about the telemetry trace event. This information is can be consumed by event logging tools, and presented in different ways.

|Parameter|Description|
|---------|-----------|
|Tag|A text string that assigns an identifier to the telemetry trace event. The tag can consist of letters, numbers, and special characters. For example, system telemetry events use an auto-generated 7-character tag, such as 000002Q. Try to make your tags unique, for example, by using a prefix. |
|Category|A text string that assigns the telemetry trace event to a category.|
|Verbosity|An enumeration that specifies the severity level of the telemetry trace event. The value can be Critical, Error, Warning, Normal, Verbose.|
|Message|A text string that specifies the descriptive message for the telemetry trace event.|

For example, the following code creates simple telemetry trace events for the five different severity levels. 
```  
SENDTRACETAG('MyCo-0001', 'Action', VERBOSITY::Critical, 'This is a critical message.');
SENDTRACETAG('MyCo-0002', 'Action', VERBOSITY::Error, 'This is an error message.');
SENDTRACETAG('MyCo-0003', 'Action', VERBOSITY::Warning, 'This is a warning message.');
SENDTRACETAG('MyCo-0004', 'Action', VERBOSITY::Normal, 'This is an informational message.');
SENDTRACETAG('MyCo-0005', 'Action', VERBOSITY::Verbose, 'This is a verbose message. ');
```  

To test out this code, add it to the `OnRun` tigger of a codeunit, and then run the codeunit.

## Viewing and collecting telemetry data
Viewing and collecting telemetry data is done the same way as with other trace events emitted by [!INCLUDE[navnow](includes/navnow_md.md)], for example, by using tools like Event Viewer, Performance Monitor, PerfView, and logman.

In Event Viewer, telemetry trace events can be viewed from **Applications and Services Logs**, in the **Microsoft** > **DynamicsNAV** > **Common** folder. The custom telemetry trace events are recorded in the **Admin**  folder. You should be aware that only events with severity level of Warning, Error, and Critical will appear. For more information, see [Monitoring Dynamics NAV Server Events Using Event Viewer](Monitoring-Microsoft-Dynamics-NAV-Server-Events-in-the-Windows-Event-Log.md).

With other tools like Performance Monitor and PerfView, you can collect telemetry data by using **Microsoft-DynamicsNAV-Common** as the event trace provider. For more information, see [Get Started Monitoring Events](Monitoring-Microsoft-Dynamics-NAV-Server-Event-Traces#GetStartedEvents).

> [!IMPORTANT]  
>  The [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance includes a configuration setting called **Diagnostic Trace Level** (`TraceLevel` in the customsettings.config file) that enables you to specify the lowest severity level of telemetry events to be recorded in the event log, or even turn off telemetry event logging altogether. If you do not see the expected events, then verify the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance configuration with an administrator. For information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md#General). 

## See Also
[Monitoring SQL Database Locks](Monitoring-Database-Locks.md)  
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
