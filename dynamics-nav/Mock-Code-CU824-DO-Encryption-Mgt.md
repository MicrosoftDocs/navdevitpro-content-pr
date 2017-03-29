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

The following code is replacement code for Codeunit **824 DO Encryption Mgt.** after converting a [!INCLUDE[navcorfu_md](includes/navcorfu_md.md)] database to [!INCLUDE[nav2017](includes/nav2017.md)]. Copy the code to a text editor, save as a .txt file type, and then use  [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)] to import the file and compile the object.
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

## See Also  
 [Converting a Database](Converting-a-Database.md)  
 [How to: Import-Objects](How-to--Import-Objects.md)
