<properties
                pageTitle="SCOPE Function (Notification) | Project “Madeira”"
                description="Describes the SCOPE function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# SCOPE Function (Notification)
Specifies the scope in which the notification appears to users in the client.

```
[CurrSCOPE := ]SCOPE([NewSCOPE])
```

## Parameters
*NewSCOPE*

Type: NotificationScope

The parameter has the following values:

|  Value  |  Description  |
|---------|---------------|
|LocalScope |The notification appears in context of the user's current task, on the page the user is currently working on. This is the default value.|
|GlobaocalScope |The notifications are not directly related to the user's current task, and it appears on the user's Role Center|

**Note:**  GlobalScope is currently not supported.

## Return Value
*CurrSCOPEE*

Type: NotificationScope

The scope of the current notification.

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
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)  
[Multilanguage Development](multilanguage-development.md)
