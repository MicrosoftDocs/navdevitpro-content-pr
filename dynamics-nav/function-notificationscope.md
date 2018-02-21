---
title: "SCOPE Function (Notification)"
ms.custom: na
ms.date: 09/20/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
ms.prod: "dynamics-nav-2018"
---
# SCOPE Function (Notification)
Specifies the context in which the notification appears in the client.

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
|GlobalScope |The notifications are not directly related to the user's current task. **Note:**  GlobalScope is currently not supported, so do not use this value.|

## Return Value
*CurrSCOPE*

Type: NotificationScope

The scope of the current notification.

## Remarks

For more information and a detailed example, see [Notifications](notifications-developing.md).

##  Example
The following code creates a notification and sends it in the local scope.
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.SEND;
```

## See Also  
[SCOPE Function(Notification)](function-notificationscope.md)  
[SEND Function (Notification)](function-notificationsend.md)  
[Notifications](notifications-developing.md)  
[Multilanguage Development](multilanguage-development.md)
