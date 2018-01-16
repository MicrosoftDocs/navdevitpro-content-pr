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

One aspect of event logging is collecting data about how the application and your deployment infrastructure is working in order to diagnose conditions and troubleshoot problems that affect operation and performance. Another aspect of event logging collecting data about how your application is being used. This is referred to as *telemetry*. Telemetry can tell you about specific activities that users perform within the application. navnow_md.mdCollecting that data is the purpose of instrumenting your app from the inside for telemetry and analytics.

Logging is typically oriented around the internal structure of your app rather than reflecting real-world customer usage. In short, logging is how you collect data about your app in the lab; instrumenting your app for telemetry, on the other hand, is how you collect data once the app is released into the wild.

Telemetry is an automated remote measurement and data collection. 

You might be thinking, “Hey, no problem—I’ve littered my code with all kinds of logging. Won’t that work?” Well, logging is a good start, but it is generally a tool that you use during development so that you can diagnose errors and code flows. Logging is typically oriented around the internal structure of your app rather than reflecting real-world customer usage. In short, logging is how you collect data about your app in the lab; instrumenting your app for telemetry, on the other hand, is how you collect data once the app is released into the wild.

Telemetry, or tele-metering, is automated remote measurement and data collection. It’s used in all kinds of industries, from tracking spacecraft, tracking wildlife, medical monitoring, law enforcement, and so on. The electrical meter attached to my house, for example, automatically sends readings to the utility company, which has eliminated the need for human meter readers. I especially like to think of telemetry in the context of spacecraft, where it is the way in which mission controllers monitor the health and operation of a very expensive piece of hardware that is completely unreachable any other way. 





## See Also
[Monitoring SQL Database Locks](Monitoring-Database-Locks.md)  
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
