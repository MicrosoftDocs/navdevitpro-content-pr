---
title: "Mock Code for Codeunit 826 DO Payment Integration Mgt."
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
## Mock Code for Codeunit 826 DO Payment Integration Mgt.

The following code is replacement code for Codeunit **826 DO Payment Integration Mgt.** after converting a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then use  [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)] to import the file and compile the object.
```
OBJECT Codeunit 826 DO Payment Integration Mgt.
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    Permissions=TableData 824=rimd,
                TableData 828=r,
                TableData 829=m;
    OnRun=BEGIN
          END;

  }
  CODE
  {
    VAR
      Text001@1001 : TextConst 'ENU="Error Code = %1; Message = %2."';
      Text002@1002 : TextConst 'ENU=Failed to read parent transaction ID.';
      Text003@1003 : TextConst 'ENU=You must complete Microsoft Dynamics ERP Payment Services Connection Setup before you use Payment Services.';
      Text004@1004 : TextConst 'ENU=Microsoft Dynamics ERP Payment Services has not been enabled.';
      Text005@1005 : TextConst 'ENU=Credit card authorization in progress...';
      Text006@1006 : TextConst 'ENU=Failed to refresh the transaction status.\';
      Text007@1007 : TextConst 'ENU=Microsoft Dynamics ERP Payment Services Signup was canceled.';
      Text008@1008 : TextConst 'ENU=Sign-up process must be completed before you can select a service.';
      Text009@1009 : TextConst 'ENU=Sign-up process succeeded. Select a valid service ID.';
      CreateKeyBeforeSignupError@1000 : TextConst 'ENU=You must create an encryption key before starting sign-up process.';
      DOPaymentTransLogMgt@1101 : Codeunit 829;

    PROCEDURE Disassociate@32();
    BEGIN
      EXIT;
    END;

    PROCEDURE SelectServiceId@31(VAR ServiceId@1000 : GUID);
    BEGIN
      EXIT;
    END;

    PROCEDURE RefreshTransactionStatus@1(DOPaymentTransLogEntry@1000 : Record 829);
    BEGIN
      EXIT;
    END;

    PROCEDURE ServiceBoarding@2();
    BEGIN
    END;

    BEGIN
    END.
  }
}
```

## See Also  
 [Converting a Database](Converting-a-Database.md)
