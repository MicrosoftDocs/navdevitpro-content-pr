---
title: "Signing an APP Package File"
description: "How do you sign an extension developed in the AL language."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 01/25/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.author: solsen
ms.assetID: be636361-9de8-4efb-ad50-445e4b7b3255
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Signing an APP Package File
Code signing is a common practice for many applications. For more information, see [Authenticode](https://msdn.microsoft.com/en-us/library/ms537359\(VS.85\).aspx) in the MSDN Library. 

The signing must be performed on a computer that has [!INCLUDE[navnow](includes/navnow_md.md)] 2018 or later installed. You must have a certificate on the computer (as a file or in the certificate store) that includes code signing for the intended purpose. It is recommended that you use a certificate from a third party certificate authority.

> [!IMPORTANT]  
> If you are publishing the extension as an app on AppSource, the .app package must be signed using a certificate from a [Certification Authority](https://technet.microsoft.com/en-us/library/cc751157.aspx) that has it's root certificates in Microsoft Windows.

For testing purposes and on-premise deployments, it is acceptable to create a self-signed certificate using the [New-SelfSignedCertificate](https://technet.microsoft.com/library/hh848633) cmdlet in PowerShell on Windows 10 or [MakeCert](https://msdn.microsoft.com/en-us/library/windows/desktop/aa386968(v=vs.85).aspx).  

## Self-signed certificate
The following example illustrates how to create a new self-signed certificate for code signing:

```
New-SelfSignedCertificate –Type CodeSigningCert –Subject “CN=ProsewareTest”
```

Example MakeCert command to create a new self-signed certificate for code signing:

```
Makecert –sk myNewKey –n “CN=Prosewaretest” –r –ss my
```

Optionally, but recommended, use a time stamp when signing the APP package file. A time stamp allows signature to be verifiable even after the certificate used for the signature has expired. For more information, see [Time Stamping Authenticode Signatures](https://msdn.microsoft.com/en-us/library/windows/desktop/bb931395\(v=vs.85\).aspx).  

Use a signing tool such as [SignTool](https://msdn.microsoft.com/en-us/library/8s9b9yaz\(v=vs.110\).aspx) or [CodeSign](https://msdn.microsoft.com/en-us/library/ms537364\(v=vs.85\).aspx) to sign the APP package file.  

The following example signs the Proseware.app file using the certificate in the password-protected MyCert.pfx file.

```
SignTool sign /f MyCert.pfx /p MyPassword “C:\NAV\Proseware.app”
```

The following example signs the Proseware.app file with a time stamp using the certificate in the password-protected MyCert.pfx file.

```
SignTool sign /f MyCert.pfx /p MyPassword /t http://timestamp.verisign.com/scripts/timestamp.dll "C:\NAV\Proseware.app”
```

The following example signs the Proseware.app file using the certificate in the My store with a subject name of "Prosewarerest".

```
SignTool sign /n Prosewaretest "C:\NAV\Extension\Proseware.app”
```

> [!NOTE]  
>  If you want to publish an unsigned extension package, you must explicitly state that by using the *–SkipVerification* parameter on the `Publish-NAVApp` cmdlet.  


## See Also
[Getting Started with AL](devenv-get-started.md)  
[Keyboard Shortcuts](devenv-keyboard-shortcuts.md)    
[AL Development Environment](devenv-reference-overview.md)  
