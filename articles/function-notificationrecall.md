<properties
                pageTitle="RECALL Function (Notification) | Project “Madeira”"
                description="Describes the RECALL function of the Notification data type for recalling notifications"
                services=""
                documentationCenter="Madeira"
                authors="SusanneWindfeldPedersen"/>
<tags
    ms.service="dynamics-nav"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="NAV"
    ms.date="07/12/2016"
    ms.author="SusanneWindfeldPedersen" />

# RECALL Function (Notification)
Recall a sent notification.

```
[Ok := ]RECALL
```
## Return Value
*Value*
**true** if the notification was recalled; otherwise, **false**.

If you omit this optional return value and if the notification cannot be recalled, then a run-time error occurs that states that the notification cannot be recalled. If you include a return value, then it is assumed that you will handle any errors and no run-time error occurs, even if the notification is not recalled.

##  Example
The following code creates a notification and sends it if NewBalance is greater than the credit limit. If it is lower than the credit limit, it recalls the notification.

```
MyNotification.ID := '00000000-0000-0000-0000-000000000001';
IF NewBallance > Rec. "Credit Limit" THEN BEGIN
  MyNotification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
  MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
  MyNotification.ADDACTION('Fix it.', 50001, 'FixCustomerCreditLimit');
  MyNotification.SETDATA('CustomerNo.', Rec."No.");
  MyNotification.SEND;
END ELSE
  MyNotification.RECALL;
```

## See Also  
[ID Function (Notification)](function-notificationid.md)
[SEND Function (Notification)](function-notificationsend.md)  
[MESSAGE Function (Notification)](function-notificationmessage.md)  
[SCOPE Function (Notification)](function-notificationscope.md)  
[Notifications](notifications-developing.md)
