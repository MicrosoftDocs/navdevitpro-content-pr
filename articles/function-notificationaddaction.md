<properties
                pageTitle="ADDACTION Function (Notification) | Project “Madeira”"
                description="Describes the ADDACTION function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# MESSAGE Function (Notification)
Specifies an action in the notification UI that the user can select.

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

## Remarks
An action provides a way for you to add an interactive notification that enables users to respond to or take action on the notification. The function that is called by the action will contain logic that you want to run for the action.

For more information and a detailed example, see [Notifications](notifications-developing.md).

##  Example
The following code creates two actions for a notification. The actions call the **RunAction1** and **RunAction** functions in codeunit 50002.

```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.ADDACTION('Action 1',50002,'RunAction1');
MyNotification.ADDACTION('Action 2',50002,'RunAction2');
MyNotification.SEND;
```

## See Also
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)
