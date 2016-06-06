<properties
                pageTitle="SEND Function (Notification) | Project “Madeira”"
                description="Describes the MESSAGE function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# SEND Function (Notification)
Sends the notification to UI.

```
[Ok := ]SEND
```
## Return Value
*Value*

Type: Code ot text

**true** if the notification was sent; otherwise, **false**.

If you omit this optional return value and if the notification cannot be sent, then a run-time error occurs that states that the notification cannot be sent. If you include a return value, then it is assumed that you will handle any errors and no run-time error occurs, even though the notification is not sent.

## Remarks
For more information and a detailed example, see [Notifications](notifications-developing.md).

##  Example
The following code creates a notification and sends it in the local scope.
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.SEND
```

## See Also  
[MESSAGE Function (Notification)](function-notificationmessage.md)  
[SCOPE Function(Notification)](function-notificationscope.md)  
[Notifications](notifications-developing.md)
