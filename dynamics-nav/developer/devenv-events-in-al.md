---
title: "Events in Microsoft Dynamics 365 for Financials and Dynamics NAV"
ms.custom: na
ms.date: 01/29/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e800bc78-feb2-4f19-b79a-3fd70e06320f
caps.latest.revision: 7
manager: edupont
---
> [!NOTE]  
> [!INCLUDE[d365fin_navnow_supported_md](includes/d365fin_navnow_supported_md.md)]

# Events in AL
The use of events is a proven and established programming concept that can ease application upgrade and limit or even eliminate the need for code modifications in customized applications because of application platform changes.  

You can use events to design the application to react to specific actions or behavior that occur. Events enable you to separate customized functionality from the application business logic. By using events in the application where customizations are typically made, you can lower the cost of code modifications and upgrades to the original application.  
  
-   Code modifications to customized functionality can be made without having to modify the original application.  
  
-   Changes to the original application code can be made with minimal impact on the customizations.  
  
 Events can be used for different purposes, such as generating notifications when certain behavior occurs or the state of an entity changes, distributing information, and integrating with external systems and applications. For example, in the [!INCLUDE[demolong](includes/demolong_md.md)], events are used for extensively for workflow and [!INCLUDE[crm](includes/crm_md.md)] integration.

 There are several different event types. The process for implementing these events is slightly different. To learn about the different types, see [Event Types](devenv-event-types.md).
  
## How events work  
 The basic principal is that you program events in the application to run customized behavior when they occur. Events in AL are modeled after Microsoft .NET Framework. There are three major participants involved in events: the *event*, a *publisher* and a *subscriber*.  
  
-   An *event* is the declaration of the occurrence or change in the application. An event is declared by an AL method, which is referred to as an *event publisher function*. An event publisher method is comprised of a signature only and does not execute any code.
  
-   A *publisher* is the object that contains event publisher method that declares the event. The publisher exposes an event in the application to subscribers, essentially providing them with a hook-up point in the application.  
  
     Publishing an event does not actually do anything in the application apart from making the event available for subscription. The event must be raised for subscribers to respond. An event is raised by adding logic to the application that calls into the publisher to invoke the event \(the event publisher method\).  
  
     Partners or subsystems can then take advantage of the published event in their solutions. An ISV that delivers vertical solutions, and Microsoft itself, are the typical providers of published events.  
  
     Business and integration type events must be explicitly published and raised, which means that you must create event publisher functions and add them to objects manually. On the other hand, trigger events, which occur on table and page operations, are published and raised implicitly by the system at runtime. Therefore, no coding is required to publish them.  
  
-   A *subscriber* listens for and handles a published event. A subscriber is an AL method that subscribes to a specific event publisher method and includes the logic for handling the event. When an event is raised, the subscriber method is called and its code is run. A subscriber enables partners to hook into the core application functionality without having to do traditional code modifications. Any [!INCLUDE[d365fin_long_md](includes/navnow_md.md)] and [!INCLUDE[navnow_md](includes/navnow_md.md)] solution provider, which also includes Microsoft, can use event subscribers.  
  
 There can by multiple subscribers to a single event publisher method. However, a publisher has no knowledge of subscribers, if any. Subscribers can reside in different parts of the application than publishers.  
  
## How to implement events  
 Implementing events consists of the following tasks:  
  
1.  Publish the event.  
  
     For business and integration events, create and configure a method in an application object to be an event publisher method. For more information, see [Publishing Events](devenv-publishing-events.md). This is not required for trigger events because these are automatically published by the system. 
  
2.  Raise the event.  
  
     Add code that calls the event publisher method. For more information, see [Raising Events](devenv-raising-events.md). This is not required for trigger events because these are raised automatically by the system.
  
3.  Subscribe to the event.  
  
     At the consumer end, add one or more subscriber methods that subscribe to published events when they are raised. For more information, see [Subscribing to Events](devenv-subscribing-to-events.md).  
  
  
## See Also  
[Publishing Events](devenv-publishing-events.md)  
[Raising Events](devenv-raising-events.md)  
[Subscribing to Events](devenv-subscribing-to-events.md)  
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)  
<!--NAV
[Debugging Events](devenv-debugging-events.md)  
[Best Practices with Microsoft Dynamics 365 for Financials](devenv-events-best-practices.md)  
 [Walkthrough: Publishing, Raising, and Subcribing to an Event in Microsoft Dynamics NAV](Walkthrough--Publishing--Raising--and-Subcribing-to-an-Event-in-Microsoft-Dynamics-NAV.md)  
[Walkthrough: Implementing New Workflow Events and Responses](Walkthrough--Implementing-New-Workflow-Events-and-Responses.md)  -->