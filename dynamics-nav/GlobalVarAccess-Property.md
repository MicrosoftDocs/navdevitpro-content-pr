---
title: "GlobalVarAccess Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8792ef2-9a9e-4be6-a6d1-d5fa8b5a5705
caps.latest.revision: 3
manager: edupont
---
# GlobalVarAccess Property
Specifies whether global variables in the object that contains the event publisher function are accessible to event subscriber functions that subscribe to the published event.  
  
## Applies to  
 C\/AL functions.  
  
 This property is only available when the [Event Property](../dynamics-nav/Event-Property.md) is set to **Publisher** and the [EventType Property](../dynamics-nav/EventType-Property.md) is set to **Integration**.  
  
## Property Value  
 **Yes** to allow access from event subscriber functions to global variables in the object that contains the event publisher function; otherwise, **No**. The default value is **No**.  
  
## Remarks  
 When you set the GlobalVarAccess property to **Yes**, event subscriber functions that subscribe to an event can call the global variable parameters in the object that is specified by the [EventPublisherObject Property](../dynamics-nav/EventPublisherObject-Property.md), which contains the event publisher function that declares the event. You must add variable parameters to the event subscriber functions manually and use a name and type that matches the variable declaration in the event publisher object.  
  
## See Also  
 [Events in Microsoft Dynamics NAV](../dynamics-nav/Events-in-Microsoft-Dynamics-NAV.md)   
 [Publishing Events](../dynamics-nav/Publishing-Events.md)   
 [Raising Events](../dynamics-nav/Raising-Events.md)   
 [Subscribing to Events](../dynamics-nav/Subscribing-to-Events.md)   
 [GlobalVarAccess Property](../dynamics-nav/GlobalVarAccess-Property.md)   
 [C\-AL Function Statements](../dynamics-nav/C-AL-Function-Statements.md)