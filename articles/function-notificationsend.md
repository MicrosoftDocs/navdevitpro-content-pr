<properties
                pageTitle="MESSAGE Function (Notification) | Project “Madeira”"
                description="Describes the MESSAGE function of the Notification data type for sending notifications"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# MESSAGE Function (Notification)
Specifies the content of the notification.

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
[TestPermissions Property](property-testpermissions.md)  
[OnBeforeTestRun Trigger](trigger-onbeforetestrun.md)  
[Testing With Permission Sets](testing-permissionsets.md)  
[Testing the Application](testing-testingapplication.md)  
[How to: Create a Test Runner Codeunit](testing-howcreatetestrunnercodeunit)  
[How to: Create Test Codeunits and Test Functions](testing-howcreatetestcodeunitsfunctions.md)  
[How to: Create Handler Functions](howcreatehandlerfunctions.md)  
[Walkthrough: Testing Purchase Invoice Discounts](testing-walkthroughtestingpurchaseinvoice.md)  
