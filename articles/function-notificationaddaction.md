<properties
                pageTitle="ADDACTION Function (Notification) | Project “Madeira”"
                description="Describes the ADDACTION function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# MESSAGE Function (Notification)
Specifies an action that the user can take when a notification appears in the UI.

```
ADDACTION(Caption, CodeunitID, FunctionName)
```

## Parameters
*Caption*

Type: Type: Code or text

The text string that to appear as the caption of the action in the notification UI. The string can be a text constant that is enabled for multilanguage functionality.

*CodeunitID*

Type: Integer

The ID of the codeunit to run when the action is initiated form the notification UI. The codeunit should contain at least one global function to be called by the notification action.

*FunctionName*

Type: Type: Code or text

The name of the function in the codeunit, which is specified by the *CodeunitID* parameter, that you want to run for the action.

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
