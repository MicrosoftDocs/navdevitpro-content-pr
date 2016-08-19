---
title: "DELETEENCRYPTIONKEY"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7dea6cb3-a530-4918-8726-d3316cfc2be1
caps.latest.revision: 6
manager: edupont
---
# DELETEENCRYPTIONKEY
Deletes the encryption key for the current [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] tenant.  
  
> [!IMPORTANT]  
>  Use the System Restore permission set in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] to allow importing the encryption key.  
  
## Syntax  
  
```  
DELETEENCRYPTIONKEY()  
```  
  
## Example  
 This code example checks if encryption is configured for the tenant using the [ENCRYPTIONENABLED](../dynamics-nav/ENCRYPTIONENABLED.md) function and if so, it performs the deletion of the encryption key.  
  
```  
IF NOT ENCRYPTIONENABLED THEN  
  ERROR('Encryption has not been enabled.');  
  DELETEENCRYPTIONKEY();  
  
```  
  
## See Also  
 [System](../dynamics-nav/System.md)   
 [Technical Reference](../dynamics-nav/Technical-Reference.md)   
 [C\-SIDE Reference Guide](../dynamics-nav/C-SIDE-Reference-Guide.md)