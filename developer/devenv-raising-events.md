---
title: "Raising Events"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
author: jswymer
---
# Raising Events
After an event has been published by an event publisher method, you can modify the application to raise the event where it is needed. Subscribers of an event will not react on the event until it is raised in the application.  

To raise an event, you add logic in AL code of the application to call the event publisher method that declares the event. The procedure for calling the event publisher method is the same as calling any other function in AL.  

When the code that calls the event publisher method is run, all event subscriber methods that subscribe to the event are run. If there are multiple subscribers, then each event subscriber method is run one after another. The order in which the event subscribers run is random and cannot it cannot be specified.  

If there are no subscribers to the published event, then the line of code that calls the event publisher method is ignored and not executed.  

## <a name="RaisingEventEx">Example
This example uses a page extension object **70000002 MyCustomerExt** to modify the page **21 Customer Card** so that an event is raised when a user changes the **Address** field. For this example, the event has already been published by the event publisher method `OnAddressLineChanged` in a separate codeunit called **70000001 MyPublishers**. In the code that follows, the page extension object modifies the `OnBeforeValidate` trigger of the **Customer Card** page to raise the event `OnAddressLineChanged` which includes the new value of the **Address** field.

```
pageextension 70000002 MyCustomerExt extends "Customer Card"
{
    layout
    {
        modify(Address)
        {
            trigger OnBeforeValidate();
                var
                    Publisher : Codeunit 70000001;
                begin
                    Publisher.OnAddressLineChanged(Address);
                end;
                }
            }

    actions
    {
        // Add changes to page actions here
    }
    
}
```
To learn about how the event used in this example is published, see [Publishing Events Example](Publishing-Events.md#PubEx). 

The next step would be to subscribe to the event to handle to condition. For information, see [Subscribing to Events](Subscribing-to-Events.md).  

## See Also  
 [Publishing Events](Publishing-Events.md)   
 [Subscribing to Events](Subscribing-to-Events.md)   
 [Events in Microsoft Dynamics NAV](Events-in-Microsoft-Dynamics-NAV.md)   
 [Introducing Events](Introducing-Events.md)
