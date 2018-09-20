---
title: "Exposing Methods and Properties in a Windows Client Control Add-in"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 9f1b5e9e-4167-4d57-bb0f-498587530ec7
caps.latest.revision: 18
manager: edupont
---
# Exposing Methods and Properties in a Windows Client Control Add-in
Control add-ins let you add custom user interface \(UI\) controls to pages in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)]. By using the basic control add-in definition interfaces, a control add-in is bound to a page only through the field that is applied with the control add-in. It is also bound to the page through the [SourceExpr Property](SourceExpr-Property.md), the [OnControlAddin Trigger](OnControlAddin-Trigger.md), and other triggers for exposed events. To extend UI controls on a page, you can expose methods and properties in a control add-in assembly so that they can be called by C/AL code on most page triggers.  
  
## Exposing Methods and Properties  
 To expose a public method or property in a control add-in, you add the method or property to the control add-in class and mark it by using the managed attribute [Microsoft.Dynamics.Framework.UI.Extensibility.ApplicationVisibleAttribute](https://docs.microsoft.com/en-us/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.ApplicationVisibleAttribute) in control add-in class.  
  
 The following code example is from a control add-in class that exposes a simple method and property.  
  
```c#  
  
[ControlAddInExport("MyControlAddIn")]  
public class MyControlAddIn : WinFormsControlAddInBase, ...  
{  
    ...  
  
    //Exposes a method  
    [ApplicationVisible]  
    public string Add(int param1, int param2)  
    {  
        return FormatNumber(param1 + param2, this.Notation);  
    }  
  
    //Exposes a property  
    [ApplicationVisible]  
    public Notation Notation  
    {  
        get { return this.notation; }  
        set { this.notation = value; }  
    }  
  
```  
  
## Calling Methods and Properties in the Control Add-in From C/AL Triggers  
 Exposed methods and properties in a control add-in can be invoked from C/AL code on page triggers. The invoking mechanism resembles other .NET Framework types with the .NET Framework interoperability except that you can call the control add-in methods and properties using C/AL without defining a variable.  
  
 To call a method in C/AL code on a page trigger, use the following code.  
  
```c#  
CurrPage.ControlName.MyMethod(parameter)  
```  
  
 To call a property in C/AL code, use the following code.  
  
```c#  
CurrPage.ControlName.MyProperty  
```  
  
 `ControlName` is the name of the field control that is applied with the control add-in. The name is specified by the [Name Property](Name-Property.md). `MyMethod` and `MyProperty` are the names of method and property of the control add-in to be invoked.  


## Nested Control Add-in Event Calls to the OnControlAddIn` trigger 
If your code requires more than one call to the `OnControlAddIn` trigger in C/AL on the same transaction (in other words, nested event calls), then the C/AL code that you want the nested event calls to run must by run by in CODEUNIT.RUN function call. This enables the application code to keep track of errors that occur in the nested event calls to the `OnControlAddIn` trigger.

This is illustarted in the following code examples. 

**Event trigger in Add-in**

The following is code is a snippet of the event definitions in a control add-in called **SampleAddin**. The control add-in includes an event, `ControlAddIn`, a public method `NestedAddinCall`, and single button control.

```
        private void ControlAddinButtonClicked(object sender, EventArgs e)
        {
            ControlAddIn?.Invoke(0, "First call");
        }

        [ApplicationVisible]
        public void NestedAddinCall()
        {
            ControlAddIn?.Invoke(1, "Second call");
        }
```

**Codeunit for running nested event calls code** 

The following code specifies the codeunit that will be used to run the code in the nested (second) event call. 

```
OBJECT Codeunit 50000 SimpleAddIn
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Modified=;
    Version List=;
  }
  PROPERTIES
  {
    TableNo=50000;
    OnRun=BEGIN
            INSERT;
          END;

  }
  CODE
  {

    BEGIN
    END.
  }
}
```

**Control-addin page**

The following code specifies a page that contain the control add-in.
 
```
OBJECT Page 50000 SimpleAddIn_page
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Modified=;
    Version List=;
  }
  PROPERTIES
  {
  }
  CONTROLS
  {
    { 10014500;;Container ;
                Name=General;
                ContainerType=ContentArea }

    { 10014501;1;Field    ;
                Name=SimpleAddIn;
                SourceExpr=Something;
                ControlAddIn=[SimpleAddIn;PublicKeyToken=nnnnnnnnnnnnnnnn];
                OnControlAddIn=BEGIN
                                 IF Index = 0 THEN
                                   CurrPage.SimpleAddIn.NestedAddinCall();
                                 ELSE IF Index = 1 THEN
                                   NestedServerCall(FORMAT(Index), Data)  
                               END;

                ShowCaption=No }

  }
  CODE
  {
    VAR
      Something : Text;

    LOCAL PROCEDURE NestedServerCall(code : Code[10];data : Text[200]);
    VAR
      AddInData : Record 50000;
      InsertResult : Boolean;
    BEGIN
      AddInData.INIT;
      AddInData.DateTime := CURRENTDATETIME;
      AddInData.Data := data;
      InsertResult := CODEUNIT.RUN(50000,AddInData);
      IF NOT InsertResult THEN
        ERROR(GETLASTERRORTEXT);
    END;

    BEGIN
    END.
  }
}
  
```

### Triggers That Are Not Supported  
 You cannot invoke control add-in methods and properties from the following triggers because the triggers are invoked before the page is instantiated:  
  
-   [OnInit Trigger](OnInit-Trigger.md)  
  
-   [OnOpenPage Trigger](OnOpenPage-Trigger.md)  
  
-   [OnNewRecord Trigger](OnNewRecord-Trigger.md)  
  
## See Also  
 [How to: Create a Windows Client Control Add-in](How-to--Create-a-Windows-Client-Control-Add-in.md)   
 [Extending the Windows Client Using Control Add-ins](Extending-the-Windows-Client-Using-Control-Add-ins.md)   
 [Extending Microsoft Dynamics NAV Using Microsoft .NET Framework Interoperability](Extending-Microsoft-Dynamics-NAV-Using-Microsoft-.NET-Framework-Interoperability.md)