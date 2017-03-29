---
title: "Mock Code for Codeunit 829 DO Payment Trans. Log Mgt."
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
## Mock Code for Codeunit 829 DO Payment Trans. Log Mgt.

The following code is replacement code for Codeunit **829 DO Payment Trans. Log Mgt.** after converting a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then use !INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] to import the file and compile the object.
```
OBJECT Codeunit 829 DO Payment Trans. Log Mgt.
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    Permissions=TableData 829=im;
    OnRun=BEGIN
          END;

  }
  CODE
  {

    PROCEDURE ValidateCanDeleteDocument@1(PaymentMethodCode@1010 : Code[10];DocumentType@1011 : Integer;DocumentTypeName@1012 : Text[30];DocumentNo@1013 : Code[20]);
    BEGIN
      EXIT;
    END;

    PROCEDURE ValidateHasNoValidTransactions@2(DocumentType@1000 : Integer;DocumentTypeName@1001 : Text[30];DocumentNo@1002 : Code[20]);
    BEGIN
      EXIT;
    END;

    PROCEDURE FindValidAuthorizationEntry@4(DocumentType@1000 : Integer;DocumentNo@1001 : Code[20];VAR DOPaymentTransLogEntry@1002 : Record 829) : Boolean;
    BEGIN
      EXIT(FALSE);
    END;

    PROCEDURE FindPostingNotFinishedEntry@5(DocumentType@1000 : Integer;DocumentNo@1001 : Code[20];VAR DOPaymentTransLogEntry@1002 : Record 829) : Boolean;
    BEGIN
      EXIT(FALSE);
    END;

    PROCEDURE FindCapturedButNotFinishedEntr@10(CustomerNo@1000 : Code[20];DocumentNo@1001 : Code[20];PaidAmount@1002 : Decimal;CurrencyCode@1003 : Code[10];CreditCardNo@1004 : Code[20];VAR DOPaymentTransLogEntry@1005 : Record 829) : Boolean;
    BEGIN
      EXIT(FALSE);
    END;

    PROCEDURE InitializeTransactionLogEntry@8(VAR DOPaymentTransLogEntry@1000 : Record 829;CreditCardNo@1001 : Code[20];SourceType@1002 : ' ,Order,Invoice';SourceNo@1003 : Code[20];CustomerNo@1004 : Code[20];TransactionType@1005 : Option;VAR ParentDOPaymentTransLogEntry@1006 : Record 829) : Integer;
    BEGIN
      EXIT(0);
    END;

    BEGIN
    END.
  }
}

```

## See Also  
 [Converting a Database](Converting-a-Database.md)
