---
title: "HYPERLINK Method"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
ms.assetid: f5d64ccc-71b4-4820-9ba7-fb054092f4a4
caps.latest.revision: 20
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# HYPERLINK Method
Passes a URL as an argument to an Internet browser, such as Windows Internet Explorer.  

## Syntax  

```  
HYPERLINK(URL)  
```  

#### Parameters  
 *URL*  
 Type: Text  

 A URL that is passed to the Internet browser as an argument.  

## Remarks  
 The syntax must be a valid URL, such as *http://www.microsoft.com*, or file path, such as *c:\\temp\\myfile.txt*. If you want the URL to be configurable, you can get the URL from a field or a variable instead. If you pass an empty string, then no browser window is opened.  

<!-- Windows
If you use this method for an application that runs on the [!INCLUDE[nav_windows](../includes/nav_windows_md.md)], then the default Internet browser that is based on the setting in the system registry is used. If the browser is already running, then a new tab opens in the browser window. If you use this method for an application that runs on the [!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)], then a new tab in the same browser window that is currently hosting the [!INCLUDE[d365fin_web_md](../includes/d365fin_web_md.md)] is opened.  
-->

At runtime, a new tab is opened in the same browser window where [!INCLUDE[d365fin_md](../includes/d365fin_md.md)] is running.

 The HYPERLINK method works with different protocols and file types as along as the syntax is valid.  

 The HYPERLINK method does not work on NAS services.  

## Example  
 The following example shows two uses of the HYPERLINK method to open the specified URL in the default browser. In the first line of code, the URL is specified in code. The second line of code illustrates how you can get a URL that is stored in a field on the current table.  

```  
HYPERLINK('http://www.microsoft.com');   
...  
HYPERLINK(Rec.UrlField);  

```  

## See Also  
 [APPLICATIONPATH Method](devenv-APPLICATIONPATH-Method.md)   
 [GUIALLOWED Method](devenv-GUIALLOWED-Method.md)   
 [SLEEP Method](devenv-SLEEP-Method.md)   
 [TEMPORARYPATH Method](devenv-TEMPORARYPATH-Method.md)
