---
title: "EnableExternalImages Property"
ms.custom: na
ms.date: 06/13/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 90a5408d-e091-409c-85fe-49508eeb92f0
caps.latest.revision: 23
manager: edupont
---
# EnableExternalImages Property
Sets whether external images are allowed on a report.  
  
## Applies To  
 Client report definition \(RDLC\) report layouts  
  
## Property Value  
 **True** if external images are allowed; otherwise, **false**. The default is **false**.  
  
## Remarks  
 When you use the Visual Studio Report Designer for creating reports for the RoleTailored client, you can add images such as your company logo to a report. You can add either *embedded* or *external* images.  
  
-   With an embedded image, the source file is compiled as part of the report. If a report only uses embedded images, then you can set the **EnableExternalImages** property to **false**. For an example of using embedded images, see [How to add a Company Picture to a Report](http://go.microsoft.com/fwlink/?LinkID=184213&clcid=0x409).  
  
-   With an external image, the source file is stored outside of the report in a location that must be accessible from the RoleTailored client, such as on a file server or local computer. The image is referenced from the report and loads when the report opens. To use external images on a report, the **EnableExternalImages** property must be set to **true**.  
  
    > [!NOTE]  
    >  The **EnableExternalImages** property exposes the [LocalReport.EnableExternalImages property](http://go.microsoft.com/fwlink/?LinkId=222522&clcid=0x409) of the [Microsoft.ReportViewer.WebForms.LocalReport object](http://go.microsoft.com/fwlink/?LinkID=222521&clcid=0x409), which is embedded in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)]. The Microsoft.ReportViewer.WebForms.LocalReport object is part of the [ReportViewer controls](http://go.microsoft.com/fwlink/?LinkID=222518&clcid=0x409) that are available in Visual Studio for adding reports to your application.  
  
   <!-- //NAV
    > [!IMPORTANT]  
    >  To display an external image in the [!INCLUDE[nav_web](includes/nav_web_md.md)] or, if the network uses a proxy, then you have to configure the client to bypass the proxy. To do this, you modify the web.config file of the website that is running the [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. For more information, see [Adding Images to a Report \(Visual Studio Report Designer\)](http://go.microsoft.com/fwlink/?LinkID=262389).  
 --> 
 For information about how to add images using Visual Studio Report Designer, see [Adding Images to a Report \(Visual Studio Report Designer\)](http://go.microsoft.com/fwlink/?LinkID=184562&clcid=0x409).  
  
## Security Considerations  
 [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] cannot verify image sources and protect against malicious images or sources that may be harmful to your computer. You should set the **EnableExternalImages** property to **true** only if you can ensure that images on the report come from a trusted source.  
  
## See Also  
 [Properties](devenv-properties.md)   
 [Designing Reports](Designing-Reports.md)   
 [Configuring Microsoft Dynamics NAV Web Client by Modifying the Web.config File](Configuring-Microsoft-Dynamics-NAV-Web-Client-by-Modifying-the-Web.config-File.md)