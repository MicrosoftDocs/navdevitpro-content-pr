---
title: "Troubleshooting: Internet Explorer cannot display the webpage"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 22f85168-f8db-42e3-a4ab-db4158342b0d
caps.latest.revision: 6
manager: terryaus
---
# Troubleshooting: Internet Explorer cannot display the webpage
When you try to access Microsoft Dynamics NAV Web Client you get the following message:  
  
 **Internet Explorer cannot display the webpage**  
  
 This error can be caused by several conditions. The most common causes are that the URL is incorrect or the web site for [!INCLUDE[nav_web](includes/nav_web_md.md)] is not started.  
  
## Resolution  
 To resolve this issue, try the following:  
  
1.  Verify that the URL is correct. For more information about URLs, see [Opening a Page in the Microsoft Dynamics NAV Web Client by Using a URL](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md).  
  
2.  Use the Internet Information Services \(IIS\) Manager to start or restart the [!INCLUDE[nav_web](includes/nav_web_md.md)] website.  
  
3.  If the computer that is running the [!INCLUDE[nav_web](includes/nav_web_md.md)] website has Windows Firewall turned on, then verify that there is an inbound rule that allows connections on the TCP\/IP port that is used by the website.  
  
     For more information, see [How to: Create an Inbound Rule in Windows Firewall for the Port of Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Create%20an%20Inbound%20Rule%20in%20Windows%20Firewall%20for%20the%20Port%20of%20Microsoft%20Dynamics%20NAV%20Web%20Client.md)  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [Troubleshooting the Microsoft Dynamics NAV Web Client Installation](Troubleshooting-the-Microsoft-Dynamics-NAV-Web-Client-Installation.md)   
 [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md)