<properties
                pageTitle="GETDATA Function (Notification) | Project “Madeira”"
                description="Describes the GETDATA function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# GETDATA Function (Notification)
Retrieves data that was passed to a notification instance by a [SETDATA function](function-notificationsetdata.md) call.

```
Value := GETDATA(Name)
```

## Parameters
*Name*

Type: Type: Code or text

The name of the data item that is specified by the SETDATA function call.

## Remarks

##  Example
The following code creates a notification and sends it in the local scope.

```
Notification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
Notification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
Notification.ADDACTION('Click here.', 5001, MyAction);
ActionData := Notification.GETDATA(myData);
Notification.SEND;

```

## See Also  
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)
