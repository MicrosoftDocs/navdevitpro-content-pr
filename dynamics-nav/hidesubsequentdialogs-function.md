---
title: "HideSubsequentDialogs Function"
ms.custom: na
ms.date: 20/12/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
ms.prod: "dynamics-nav-2017"
---
# HideSubsequentDialogs Function
Hides dialogs that are created by calling the a OPEN function call on dialog type variables other than the t the Dialog.OPEN function call . called [SuppressChildDialog]. When this is set to TRUE, any subsequent call to dialog.open, update, close not related to this window would be ignored.

```
[Ok := ]Dialog.HIDESUBSEQUENTDIALOGS([SetHideSubsequentDialogs])
```
## Parameters
*Dialog*

Type: Dialog

The Dialog variable that you are closing.
## Return Value
*Value*

Type: Code or text

**true** if the notification was sent; otherwise, **false**.

If you omit this optional return value and if the notification cannot be sent, then a run-time error occurs that states that the notification cannot be sent. If you include a return value, then it is assumed that you will handle any errors and no run-time error occurs, even though the notification is not sent.

## Remarks
The SEND function displays the content of the notification that is specified by the [MESSAGE function](function-notificationmessage.md).

For more information and a detailed example, see [Notifications](notifications-developing.md).

##  Example
The following code creates a notification and sends it to the client in the local scope.
```
// Here we set the HIDESUBSEQUENTDIALOGS property
MyDialog1.HIDESUBSEQUENTDIALOGS := TRUE;

// As soon as this dialog opens, it will register as the root dialog.
MyDialog1.OPEN('Dialog 1');
SLEEP(2000);

// The second dialog will not open. However, the code associated with the Open call will run as if it was actually opened.
MyDialog2.OPEN('Dialog 2 #1', MyText);
SLEEP(2000);

// Updating the second dialog will not do anything
MyDialog2.UPDATE(1, MyText2);
SLEEP(2000);

// As soon as they dialogs is closed they can be reopened and they will no longer be hidden
MyDialog2.CLOSE;
MyDialog1.CLOSE;
```

## See Also  
[MESSAGE Function (Notification)](function-notificationmessage.md)  
[SCOPE Function(Notification)](function-notificationscope.md)  
[Notifications](notifications-developing.md)
