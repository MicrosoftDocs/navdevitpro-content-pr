<properties
                pageTitle="Notifications | Project “Madeira”"
                description="Describes how you can develop notifications in the application using C/AL."
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# Notifications
Notifications provide a programmatic way to send non-intrusive information to the user interface in the Dynamics NAV Web client. Notifications differ from messages initiated by the MESSAGE function. With messages, users are typically required to address the message and take some form of corrective action before they continue working. Notifications give users information about a current situation, but do not require any immediate action or block users from continuing with their current task. For example, you could have a notification that a customer's credit limit is exceeded.

In the user interface, users will see the **Notification** bar at the top of the page from where the **Notification** can be dismissed. Any validation errors on the page will be shown first.

## Developing Notifications
By using the new Notification and NotificationScope data types and functions in C/AL, you can add code to send notifications to users for two different scopes: local and global. A local scope notification appears in context of what the user is currently doing, while global scope notifications are not directly related to the current task. The following example illustrates the simplified code for local scope notification:

```
Notification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
Notification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
Notification.SEND;
```


## See Also  
