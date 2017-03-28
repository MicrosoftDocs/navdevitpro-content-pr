---
title: "Mock Code for Codeunit 824 DO Encryption Mgt."
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
author: jswymer
---
## Mock Code for Codeunit 824 DO Encryption Mgt.

The following code is replacement code for Codeunit **824 DO Encryption Mgt.** after converting a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy he code to a text editor, save as a .txt file type, and then import the file to the database by using the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)].
```
OBJECT Codeunit 824 DO Encryption Mgt.
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    SingleInstance=Yes;
    OnRun=BEGIN
          END;

  }
  CODE
  {

    PROCEDURE Encrypt@1(Input@1000 : Text[1024]) : Text[1024];
    BEGIN
    END;

    PROCEDURE Decrypt@2(Input@1000 : Text[1024]) : Text[1024];
    BEGIN
    END;

    PROCEDURE Import@4(Filename@1001 : Text;PasswordText@1002 : Text);
    BEGIN
    END;

    PROCEDURE Export@5(Filename@1000 : Text;PasswordText@1002 : Text);
    BEGIN
    END;

    PROCEDURE HasKey@8() : Boolean;
    BEGIN
    END;

    PROCEDURE CreateKey@6();
    BEGIN
    END;

    PROCEDURE DeleteKey@7();
    BEGIN
    END;

    PROCEDURE SetKeyFilePath@12(NewKeyFilePath@1000 : Text);
    BEGIN
    END;

    BEGIN
    END.
  }
}
```

## Replacement Code for Codeunit 824 DO Encryption Mgt.
```
OBJECT Codeunit 825 DO Payment Mgt.
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    Permissions=TableData 829=m;
    OnRun=BEGIN
          END;

  }
  CODE
  {

    PROCEDURE AuthorizeSalesDoc@14(SalesHeader@1000 : Record 36;CustLedgerEntryNo@1008 : Integer;AuthorizationRequired@1006 : Boolean) : Integer;
    BEGIN
      EXIT;
    END;

    PROCEDURE CheckGenJnlLine@10(GenJournalLine@1000 : Record 81);
    BEGIN
      EXIT;
    END;

    PROCEDURE CaptureGenJnlLine@11(GenJnlLine@1000 : Record 81) : Integer;
    BEGIN
      EXIT(0);
    END;

    PROCEDURE CaptureSalesDoc@15(SalesHeader@1003 : Record 36;CustLedgerEntryNo@1000 : Integer) : Integer;
    BEGIN
      EXIT(0);
    END;

    PROCEDURE RefundGenJnlLine@8(GenJnlLine@1000 : Record 81) : Integer;
    BEGIN
      EXIT;
    END;

    PROCEDURE RefundSalesDoc@2(SalesHeader@1001 : Record 36;CustLedgerEntryNo@1010 : Integer) : Integer;
    BEGIN
      EXIT;
    END;

    PROCEDURE CheckSalesDoc@5(SalesHeader@1000 : Record 36);
    BEGIN
      EXIT;
    END;

    PROCEDURE VoidSalesDoc@28(VAR SalesHeader@1001 : Record 36;VAR DOPaymentTransLogEntry@1002 : Record 829);
    BEGIN
      EXIT;
    END;

    PROCEDURE UpdateTransactEntryAfterPost@17(DOPaymentTransLogEntryNo@1000 : Integer;RelatedCustLedgerEntryNo@1002 : Integer;DocumentType@1003 : 'Payment,Refund');
    BEGIN
      EXIT;
    END;

    PROCEDURE IsAuthorizationRequired@18() : Boolean;
    BEGIN
      EXIT;
    END;

    PROCEDURE IsValidPaymentMethod@22(PaymentMethodCode@1000 : Code[10]) : Boolean;
    BEGIN
      EXIT(FALSE);
    END;

    PROCEDURE CheckCreditCardData@25(CreditCardNo@1000 : Code[20]);
    BEGIN
      EXIT;
    END;

    PROCEDURE FindCurrencyCode@21(CurrencyCode@1000 : Code[10]) : Code[10];
    BEGIN
      EXIT;
    END;

    BEGIN
    END.
  }
}
```

## Fixing Test Runner Codeunits Compilation Errors
If the old database includes test runner codeunits, you must change the signature of the OnBeforeTestRun and OnAfterTestRun triggers of the test runner codeunits to include the *TestPermission* data type parameter. By default, this includes codeunit 130400 **CAL Test Runner** and codeunit 130402 **CAL Command Line Test Runner**.

The following code illustrates the changes to make to the function signatures:

**OnBeforeTestRun trigger signature before:**
```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]) : Boolean
```

**OnBeforeTestRun trigger after:**    
```
    OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];FunctionTestPermissions : TestPermissions) : Boolean)
```

**OnAfterTestRun trigger before:**
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];IsSuccess : Boolean)
```

**OnAfterTestRun trigger after:**
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; FunctionTestPermissions : TestPermissions; Success : Boolean)
```
## Before and After Code for Warnings in Table 79  
 The following table describes the before and after code that will help you resolve the warnings that you receive when you compile table 79 **Company Information**.  

 **Before**  

```  
LOCAL PROCEDURE GetDatabaseIndicatorText@9(IncludeCompany@1003 : Boolean) : Text[250];  
VAR  
  Session@1000 : Record 2000000009;  
  Text@1002 : Text[1024];   
BEGIN  
  Session.SETRANGE("My Session",TRUE);  
  Session.FINDFIRST;  
  Text := Session."Database Name" + ' - ' + Session."Host Name";  
  IF IncludeCompany THEN  
    Text := COMPANYNAME + ' - ' + Text;  
  IF STRLEN(Text) > 250 THEN  
    EXIT(COPYSTR(Text,1,247) + '...');  
  EXIT(Text)  
END;  
```  

 **After**  

```  
LOCAL PROCEDURE GetDatabaseIndicatorText@9(IncludeCompany@1003 : Boolean) : Text[250];  
VAR  
  ActiveSession@1000 : Record 2000000110;  
  Text@1002 : Text[1024];   
BEGIN  
  ActiveSession.SETRANGE("Server Instance ID",SERVICEINSTANCEID);  
  ActiveSession.SETRANGE("Session ID",SESSIONID);  
  ActiveSession.FINDFIRST;  
  Text := ActiveSession."Database Name" + ' - ' + ActiveSession."Server Computer Name";   
  IF IncludeCompany THEN  
    Text := COMPANYNAME + ' - ' + Text;  
  IF STRLEN(Text) > 250 THEN  
    EXIT(COPYSTR(Text,1,247) + '...');  
  EXIT(Text)  
END;  
```  

## Before and After Code for Codeunit 40  
 The following tables describe the before and after code that will help you resolve the warnings that you receive when you compile codeunit 40 **LogInManagement**.  

|||  
|-|-|  
|Before|`User@1003 : Record 2000000120;`|  
|After|`User@1003 : Record 2000000120 SECURITYFILTERING(Filtered);`|  

|||  
|-|-|  
|Before|`Language.SETRANGE("STX File Exist",TRUE);`|  
|After|`Language.SETRANGE("Localization Exist",TRUE);`|  

## Before and After Code for Codeunit 43  
 The following table describes the before and after code that will help you resolve the warnings that you receive when you compile codeunit 43 **LanguageManagement**.  

|||  
|-|-|  
|Before|`Language.SETRANGE("STX File Exist",TRUE);`|  
|After|`Language.SETRANGE("Localization Exist",TRUE);`|  

## See Also  
 [Converting a Database](Converting-a-Database.md)
