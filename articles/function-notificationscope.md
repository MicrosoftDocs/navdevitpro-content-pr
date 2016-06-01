<properties
                pageTitle="SCOPE Function (Notification) | Project “Madeira”"
                description="Describes the SCOPE function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# SCOPE Function (Notification)
Specifies the scope in which the notification appears to users content of the notification.

```
[CurrMESSAGE := ]MESSAGE([NewMESSAGE])
```

## Parameters
*NewMESSAGE*

Type: Type: Code or text

The text string that you want to display for the notification. The string can be a text constant that is enabled for multilanguage functionality.

## Return Value
*CurrMESSAGE*

Type: Code ot text

The content of the current notification.

## Remarks

##  Example
The following code creates a notification and sends it in the local scope.

```
Notification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
Notification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
Notification.SEND;
```

## See Also  
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)  
[Multilanguage Development](multilanguage-development.md).
