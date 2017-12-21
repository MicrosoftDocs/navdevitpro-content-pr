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
Specifies whether to hide dialogs l on dialog type variables other than the t the Dialog.OPEN function call . called [SuppressChildDialog]. When this is set to TRUE, any subsequent call to dialog.open, update, close not related to this window would be ignored.

```
[IsHideSubsequentDialogs := ]Dialog.HIDESUBSEQUENTDIALOGS([SetHideSubsequentDialogs])
```
## Parameters
*Dialog*

Type: Dialog

The Dialog variable that you want to open.

*SetHideSubsequentDialogs*

Type: Boolean

**true** hides any subsequent calls to dialog.OPEN, update, close that is not related to this window would be ignored. **false** is default.

## Return Value
*IsHideSubsequentDialogs*

Type: Boolean

**true** if the HIDESUBSEQUENTDIALOGS set to **true**; otherwise, **false**.

## Remarks
You must call Dialog.HIDESUBSEQUENTDIALOGS before Dialog.OPEN.



##  Example
The following code illustrates how the HIDESUBSEQUENTDIALOGS function works.

This code example requires that you create the following variables.  

|Name|DataType|  
|----------|--------------|  
|MyDialog1|Dialog|  
|MyDialog2|Dialog|  

This code example requires that you create the following text constants in the **C/AL Globals** window.  

|Name|ConstValue|  
|----------|----------------|  
|Text000|plus|   


```
// The HIDESUBSEQUENTDIALOGS function is is used on MyDialog1 dialog.
MyDialog1.HIDESUBSEQUENTDIALOGS := TRUE;

// When MyDialog1 dialog opens, it will register as the root dialog.
MyDialog1.OPEN('Dialog 1');
SLEEP(2000);

// MyDialog2 dialog will not open. However, the code associated with the Open call will run as if it was actually opened.
MyDialog2.OPEN('Dialog 2');
SLEEP(2000);

// Updating MyDialog2 dialog will have no effect
MyDialog2.UPDATE(1, Text000);
SLEEP(2000);

// MyDialog1 dialog will open 
MyDialog1.OPEN('Dialog 1 #1', Text000);
SLEEP(2000);

// As soon as MyDialog1 dialog is closed, other can be reopened and they will no longer be hidden
MyDialog1.CLOSE;

MyDialog2.UPDATE(1, Text000);
SLEEP(2000);

```

## See Also  
[MESSAGE Function (Notification)](function-notificationmessage.md)  
[SCOPE Function(Notification)](function-notificationscope.md)  
[Notifications](notifications-developing.md)
