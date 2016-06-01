<properties
                pageTitle="SEND Function (Notification) | Project “Madeira”"
                description="Describes the MESSAGE function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# SEND Function (Notification)
Specifies the content of the notification.

```
[Ok := ]SEND
```
## Return Value
*Ok*

Type: Boolean

**true** if the notification was sent; otherwise, **false**.

If you omit this optional return value and if the notification cannot be sent, then a run-time error occurs that states that the notification cannot be sent. If you include a return value, then it is assumed that you will handle any errors and no run-time error occurs, even though the notification is not sent.




## Remarks

##  Example
The following code creates a notification and sends it in the local scope.

```
Notification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
Notification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
Notification.SEND;
```

## See Also  
[MESSAGE Function (Notification)](function-notificationmessage.md)  
[SCOPE Function(Notification)](function-notificationscope.md)  
[Notifications](notifications-developing.md)
