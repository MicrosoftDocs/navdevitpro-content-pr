 <properties
                pageTitle="Notifications | Project “Madeira”"
                description="Describes how you can develop notifications in the application using C/AL."
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# Notifications
Notifications provide a programmatic way to send non-intrusive information to the user interface (UI) in the Dynamics NAV Web client. Notifications differ from messages initiated by the MESSAGE function. Messages are modal, which means users are typically required to address the message and take some form of corrective action before they continue working. On the other hand, notifications are non-modal. Their purpose is to give users information about a current situation, but do not require any immediate action or block users from continuing with their current task. For example, you could have a notification that a customer's credit limit is exceeded.

## Notifications in the UI
In the UI, notifications appear in the **Notification** bar (similar to validation errors) at the top of the page on which a user is currently working. The user can then choose to dismiss the notification, which clears it. Or if actions are defined on notification, the user can choose one of the actions. 

* There can be multiple notifications. The notifications appear chronological order from top to bottom.
* Notifications remain for duration of the page instance or until the user dismisses them or takes action on them.
* Notifications that are defined on sub-pages, for example in parts and FactBoxes, appear in the same **Notification** bar. 
* Validation errors on the page will be shown first.

## Developing notifications - overview
By using the **Notification** and **NotificationScope** data types and functions in C/AL, you can add code to send notifications to users.

|  Function  |  Description  |
|------------|---------------|
|[MESSAGE](function-notificationmessage.md)  |Specifies the content of the notification that appears in the UI.|
|[SCOPE](function-notificationscope.md)     |Specifies the scope in which the notification appears.|
|[SEND](function-notificationsend.md)  |Creates an instance of a notification in the UI at runtime|
|[ADDACTION](function-notificationaddaction.md)  |Specifies an action on the notification.|
|[SETDATA](function-notificationsetdata.md)  |Specifies data to be transferred to the notification instance.|
|[GETDATA](function-notificationgetdata.md)  |Retrieves data from a SETDATA function call.|

The following sections describe the use of these functions in more detail.

## Creating and sending notifications
You implement notifications by using the **MESSAGE** and **SEND** functions. The **MESSAGE** function defines the content of the notification. When the MESSAGE function is called, it creates an instance of the notification on the Dynamics NAV Server. The **SEND** function passes the notification to the client at runtime.
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SEND
```

## Defining the notification scope
The scope is the realm in which a notification is broadcast in the client. There are two different scopes: local and global. A local scope notification appears in context of the user's current task, that is, on the page the user is currently working on. A global scope notifications are not directly related to the current task. These appear on the user's Role Center.
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.SEND;
```
**Note:** The *GlobalScope* is currently not supported. The default scope is *LocalScope*.

## Adding actions on notifications
The ADDACTION function provides you a way to create more interactive notifications. By default, users have the option to dismiss the notifications. However, there might be cases where you want to provide them with different actions, such as a simple task, which they can take to address the notification.

To implement an action, you create a codeunit that contans a global function in which you add business logic for the action. You then include the **ADDACTION** function in the notification code to call the function.  You can have multiple actions on a single notification instance.
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.ADDACTION('Action 1',50002,'RunAction1');
MyNotification.ADDACTION('Action 2',50002,'RunAction2');
MyNotification.SEND;
```

## Handling data with notifications
You can use the **SETDATA** and **GETDATA** functions to handle data in a notification, typically with respect to actions. The **SETDATA** function defines the data that you want to transfer to the notification instance. The data is defined as text in a key-value pair. When the notification is sent to the client, the data is passed to the notification instance. With the **GETDATA** function, you can then retrieve the data, and add logic to handle it.

The following code sets the data for a notification:
```
MyNotification.MESSAGE := 'This is a notification';
MyNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
MyNotification.SETDATA('Created',FORMAT(CURRENTDATETIME,0,9));
MyNotification.SETDATA('ID',FORMAT(CREATEGUID,0,9));
MyNotification.ADDACTION('Action 1',50002,'RunAction1');
MyNotification.ADDACTION('Action 2',50002,'RunAction2');
MyNotification.SEND;
```
The following code gets the data for a notification:

```
MyNotification.GETDATA('Created');
MyNotification.GETDATA('ID');
```
## Example
This simple example illustrates how notifications work and provides some insight into how you can use them. This example uses page **42 Sales Order** of the CRONUS International Ltd. demonstration database accroding to the following.

*   The code compares a customer's balance with their credit limit. If the balance exceeds the credit limit, a notification is sent to the client.
*   The notification includes an action, which has the caption **Change credit limit**, that opens page **21 Customer Card**. This enables the user to increase the credit limit.

### Variables and text constants
Create the following C/AL variables and text constants on page **21 Customer Card**:


|  Variable Name |  Data Type  |  Subtype  |
|----------------|-------------|-----------|
|Customer    |  Record     |    Customer |
|CreditBalanceNotification|  Notification  | (not applicable) |

|  Text Constant Name |  ConstValue |
|----------------------|------------|
|Text003    |The customer's current balance exceeds their credit limit.|
|Text004|  Change credit limit  |

### Notification code
Add the following code the OnOpenPage tigger of the page:

```
IF Customer."Balance (LCY)" > customer."Credit Limit (LCY)" THEN
    CreditBalanceNotification.MESSAGE := 'The customer's current balance exceeds their credit limit.';
    CreditBalanceNotification.SCOPE := NOTIFICATIONSCOPE::LocalScope;
    CreditBalanceNotification.SETDATA(CustNumber, Customer."No.");
    CreditBalanceNotification.ADDACTION('Change credit limit', 5001, OpenCustomer);
    CreditBalanceNotification.SEND;
```
### Data handling
Create codunit 5001 that includes a global function that has the name **OpenCustomer**.

Add the following C/AL variables to the codeunit:


|  Variable  |  Data Type  |  Subtype  |
|------------|-------------|-----------|
|CustomerNo    |  Text     |   |
|CustRec|Record|Customer|
|CustPage|Page|Customer Card|

Add the following code to the **OpenCustomer** function:

```
CustomerNo := GETDATA(CustNumber);
CustRec.GET(CustomerNo);
CustPage.SETRECORD(CustRec);
CustPage.RUN;

```

## See Also  
