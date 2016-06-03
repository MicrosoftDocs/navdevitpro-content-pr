 <properties
                pageTitle="Notifications | Project “Madeira”"
                description="Describes how you can develop notifications in the application using C/AL."
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# Notifications
Notifications provide a programmatic way to send non-intrusive information to the user interface (UI) in the Dynamics NAV Web client. Notifications differ from messages initiated by the MESSAGE function. With messages, users are typically required to address the message and take some form of corrective action before they continue working. Notifications give users information about a current situation, but do not require any immediate action or block users from continuing with their current task. For example, you could have a notification that a customer's credit limit is exceeded.

## Notifications in the UI
In the UI, notifications appear in the **Notification** bar, similar to validation errors, at the top of the page on which a user is currently working. The user can then choose to dismiss the notification, which clears it, or if actions are defined on notification, choose one of the actions. Any validation errors on the page will be shown first.

There can be multiple notification, where they appear one after the other, with the latest at the top.

Notification remain for duration of the page instance or until the user dismisses them or takes action on them.

## Developing Notifications
By using the new Notification and NotificationScope data types and functions in C/AL, you can add code to send notifications to users for two different scopes: local and global. A local scope notification appears in context of what the user is currently doing, while global scope notifications are not directly related to the current task

|  Function  |  Description  |
|------------|---------------|
|[MESSAGE](function-notificationmessage.md)  |Specifies the content of the notification that appears in the UI.|
|[SCOPE](function-notificationscope.md)     |Specifies the scope in which the notification appears.|
|[SEND](function-notificationsend.md)  |Creates an instance of a notification in the UI at runtime|
|[ADDACTION](function-notificationaddaction.md)  |Includes an action on the notification, whcih the user can choose to perform an operation.|
|[SETDATA](function-notificationsetdata.md)  |Specifies data to be passed to the notification instance.|
|[GETDATA](function-notificationgetdata.md)  |Retrieves data from a SETDATA function call.|

### Creating and Sending Notifications
You implement notifications by using the MESSAGE and SEND functions. the MESSAGE function define the content of the notification. When the MESSAGE function is called, it creates an instance of the notification on the Dynamics NAV Server. The SEND function passes the notification instance to the client at runtime.

### Adding Actions on Notifications
The ADDACTION function provides you a way to create more interactive notifications. By default, users have the option to dismiss the notifications. However, there might be cases where you want to provide them with different actions, such as a simple task, which they can take to address the notification. You can have multiple actions on a single notification instance.

### Handling Data with Notifications

## Example
This simple example will illustrate how notifications work and provide some insight into how you can use them.
```
Notification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
Notification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
Notification.SEND;
```

## See Also  
