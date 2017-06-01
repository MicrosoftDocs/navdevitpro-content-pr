---
title: "EventFunction Property"
ms.custom: na
ms.date: 06/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: ccfbe1a3-b0ac-4933-9036-ae499041ecd5
caps.latest.revision: 4
manager: edupont
---
# EventFunction Property
Specifies the event publisher function that the event subscriber function subscribes to.  

## Applies to  

-   AL functions.  

     This property is only available when the [Event Property](Event-Property.md) is set to **Subscriber**.  

## Property Value  
 An event publisher function in the object that is specified in the [EventPublisherObject Property](EventPublisherObject-Property.md).  

## Remarks  
 You use this property to set up an event subscriber function to respond to the event that is declared by the event publisher function. When the event is raised in the application, the event subscriber function is called.  

 You add AL code to this function that defines the logic to handle the event when it is called.  

 For more information about events, see [Subscribing to Events](Subscribing-to-Events.md).

## See Also  
 [Events in Microsoft Dynamics NAV](Events-in-Microsoft-Dynamics-NAV.md)   
 [Publishing Events](Publishing-Events.md)   
 [Raising Events](Raising-Events.md)   
 [C/AL Function Statements](C-AL-Function-Statements.md)
