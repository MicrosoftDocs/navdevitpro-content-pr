---
title: "Mock Code for Codeunit 827 DO Payment Card Validation"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
manager: edupont
---
## Mock Code for Codeunit 827 DO Payment Card Validation

The following code is replacement code for Codeunit **827 DO Payment Card Validation** after converting a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then use  [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)] to import the file and compile the object.
```
OBJECT Codeunit 827 DO Payment Card Validation
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    OnRun=BEGIN
          END;

  }
  CODE
  {
    VAR
      Text001@1000 : TextConst 'ENU=''Invalid card type''.';
      Text002@1002 : TextConst 'ENU=%1 must not contain spaces.';
      Text003@1003 : TextConst 'ENU=The specified %1 is not valid.';
      Text004@1004 : TextConst 'ENU=%1 can only contain digits.';
      Text005@1005 : TextConst 'ENU=You must specify %1.';
      Text006@1006 : TextConst 'ENU=Validation rule does not allow spaces.';
      Text007@1007 : TextConst 'ENU=%1 does not meet the required length.';
      Text008@1008 : TextConst 'ENU=%1 exceeds the maximum length.';

    PROCEDURE ValidateCreditCard@1(CardNumber@1000 : Text[30];CardTypeName@1001 : Text[20]);
    BEGIN
      EXIT;
    END;

    BEGIN
    END.
  }
}

```

## See Also  
 [Converting a Database](Converting-a-Database.md)
