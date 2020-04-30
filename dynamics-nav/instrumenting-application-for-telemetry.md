---
title: Developing telemetry into your Dynamics NAV application
description: This topic desscribes how to add code to application objects that enables you to gather telemetry.
ms.custom: na
ms.date: 11/22/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Instrumenting an Application for Telemetry
This article describes how you can implement custom telemetry trace events in your application for collecting telemetry data. This data can then be collected and visualized for analyzing the application against the desired business goals, trobleshooting, and more. 

## Telemetry overview
One aspect of event logging is collecting data about how the application and your deployment infrastructure is working in order to diagnose conditions and troubleshoot problems that affect operation and performance. For example, this type of event logging includes [!INCLUDE[nav_server_md](includes/nav_server_md.md)] events and trace events like SQL and AL function traces.

Another aspect of event logging is *telemetry*, which is collecting data about how your application functions and how it is being used in production. Telemetry can tell you about specific activities that users perform within the application in the production enviroment. Telemetry is also useful tool for troubleshooting, especially instances where you are not able to reproduce the conditions experienced by the user or have no access to the user's environment. Telemetry can be divided into different levels or categories, like: telemetry for engineering, telemetry about the business, telemetry for customers

By default, the [!INCLUDE[navnow](includes/navnow_md.md)] application is instrumented to emit several system telemetry trace events that are recorded in the event log. Custom telemetry trace events enable you to send telemetry data from anywhere in the application code. 

## Creating custom telemetry events

To create a custom telemetry event, you use the [SENDTRACETAG function](sendtracetag-function.md) in C/AL code. You can use the SENDTRACETAG function in any object, trigger or function. The SENDTRACETAG function has the following syntax:

```  
SENDTRACETAG(Tag, Category, Verbosity, Message)  
```  

<!--

```  
SENDTRACETAG(Tag, Category, Verbosity, Message[, DataClassification])  
```  
-->

You use the parameters to define the information about the telemetry trace event. This information is can be consumed by event logging tools, and presented in different ways.

|Parameter|Description|
|---------|-----------|
|Tag|A text string that assigns an identifier to the telemetry trace event. The tag can consist of letters, numbers, and special characters. [!INCLUDE[navnow_md](includes/navnow_md.md)] system telemetry events use an auto-generated, auto-incremented, 7-character tag that includes numbers and letters, such as 000002Q. and 000013P. Try to make your tags unique from these telemetry event tags by, for example, using at least 8 characters or a prefix, like Cronus-0001 and Cronus-0002.  |
|Category|A text string that assigns the telemetry trace event to a category that you define. For example, you could have a category for upgrading, user activity, or reporting.|
|Verbosity|An enumeration that specifies the severity level of the telemetry trace event. The value can be Critical, Error, Warning, Normal, or Verbose. This severity level can be used by [!INCLUDE[nav_server_md](includes/nav_server_md.md)] to filter out lower-level telemetry trace events from being emitted. See [Viewing and collecting telemetry data](instrumenting-application-for-telemetry.md#ViewTelemetry). |
|Message|A text string that specifies the descriptive message for the telemetry trace event.|

<!-- future CU 
|DataClassification|A DataClassification data type that assigns a classification to the telemetry trace event. For more information, see [Data Classifications](classifying-data.md#DataClassifications).|

-->
For example, the following code creates simple telemetry trace events for the five different severity levels. 

```  
SENDTRACETAG('Cronus-0001', 'Action', VERBOSITY::Critical, 'This is a critical message.');
SENDTRACETAG('Cronus-0002', 'Action', VERBOSITY::Error, 'This is an error message.');
SENDTRACETAG('Cronus-0003', 'Action', VERBOSITY::Warning, 'This is a warning message.');
SENDTRACETAG('Cronus-0004', 'Action', VERBOSITY::Normal, 'This is an informational message.');
SENDTRACETAG('Cronus-0005', 'Action', VERBOSITY::Verbose, 'This is a verbose message.');
```  

<!-- future CU
```  
SENDTRACETAG('Cronus-0001', 'Action', VERBOSITY::Critical, 'This is a critical message.', DATACLASSIFICATION::CustomerContent);
SENDTRACETAG('Cronus-0002', 'Action', VERBOSITY::Error, 'This is an error message.',  DATACLASSIFICATION::EndUserIdentifiableInformation);
SENDTRACETAG('Cronus-0003', 'Action', VERBOSITY::Warning, 'This is a warning message.', DATACLASSIFICATION::AccountData);
SENDTRACETAG('Cronus-0004', 'Action', VERBOSITY::Normal, 'This is an informational message.', DATACLASSIFICATION::OrganizationIdentifiableInformation);
SENDTRACETAG('Cronus-0005', 'Action', VERBOSITY::Verbose, 'This is a verbose message.', DATACLASSIFICATION::SystemMetadata);
```  
-->

For a simple test of this code, add it to the `OnRun` trigger of a codeunit, and then run the codeunit. Of course, you can also call the code from other objects, triggers or functions as well.

## <a name="ViewTelemetry"></a>Viewing and collecting telemetry data
Viewing and collecting telemetry data is done the same way as with other trace events emitted by [!INCLUDE[navnow](includes/navnow_md.md)], for example, by using tools like Event Viewer, Performance Monitor, PerfView, or logman.

-   In Event Viewer, telemetry trace events can be viewed from **Applications and Services Logs**, in the **Microsoft** > **DynamicsNAV** > **Common** folder. The custom telemetry trace events are recorded in the **Admin**  folder. You should be aware that only events with severity level of Warning, Error, and Critical will appear.

    For more information, see [Monitoring Dynamics NAV Server Events Using Event Viewer](Monitoring-Microsoft-Dynamics-NAV-Server-Events-in-the-Windows-Event-Log.md).

-   With other tools like Performance Monitor, PerfView, and logman, you can collect telemetry data by using **Microsoft-DynamicsNAV-Common** as the event trace provider.

    For more information, see [Get Started Monitoring Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md#GetStartedEvents).

> [!IMPORTANT]  
>  The [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance includes a configuration setting called **Diagnostic Trace Level** (`TraceLevel` in the customsettings.config file) that enables you to specify the lowest severity level of telemetry events to be recorded in the event log, or even turn off telemetry event logging altogether. If you do not see the expected events, then verify the [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance configuration with an administrator. For information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md#General). 

## See Also
[Monitoring Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md)  
[Development in C/AL](development.md)   
