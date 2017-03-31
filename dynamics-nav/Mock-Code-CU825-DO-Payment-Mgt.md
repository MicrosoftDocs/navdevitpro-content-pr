---
title: "Mock Code for Codeunit 825 DO Payment Mgt."
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
## Mock Code for Codeunit 825 DO Payment Mgt.

The following code is replacement code for Codeunit **825 DO Payment Mgt.** after converting a  [!INCLUDE[navcorfu_md](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then use  [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)] to import the file and compile the object.
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
```

## See Also  
 [Converting a Database](Converting-a-Database.md)  
 [How to: Import-Objects](How-to--Import-Objects.md)
