---
title:"Opening a Report in the Microsoft Dynamics NAV Web Client by Using a URL"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 2c2b3120-69ce-4c40-bf22-8e385fefd64f
caps.latest.revision: 16
manager: edupont
---
# Opening a Report in the Microsoft Dynamics NAV Web Client by Using a URL
You can open a specific report in the [!INCLUDE[nav_web](includes/nav_web_md.md)] by typing the report's URL in the address of a web browser. After you have the URL of a report, you can use it as a hyperlink to the report, which you can include in other sources, such as emails or Word documents, or send to other users.  
  
> [!IMPORTANT]  
>  Certain data in the URL, such as company name, could be considered sensitive information. Use discretion if you distribute URLs that contain the company name, or if it is possible, exclude this information from the URL.  
  
 This topic includes the following sections:  
  
-   [Example](Opening-a-Report-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Example)  
  
-   [Report Address Syntax](Opening-a-Report-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Syntax)  
  
-   [Building the Report Address](Opening-a-Report-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Building)  
  
-   [Report Address Parameters](Opening-a-Report-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Paramters)  
  
##  <a name="Example"></a> Example  
 The following address displays report 5 Receivables – Payables for the [!INCLUDE[demoname](includes/demoname_md.md)] company. The page is displayed in a [!INCLUDE[nav_web](includes/nav_web_md.md)] that is running on port 8080 of a computer that has the name MyWebServer.  
  
```  
http://MyWebServer:8080/nav_server_instance/WebClient/default.aspx?report=5&company=CRONUS%20International%20Ltd.   
```  
  
 There are several parameters that define the URL for the report. These parameters are described in the [URL Parameters](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Paramters) section of this topic.  
  
> [!NOTE]  
>  Unlike pages, you cannot filter the data in a report using the URL.  
  
##  <a name="Syntax"></a> Report Address Syntax  
 The address for opening a report in the [!INCLUDE[nav_web](includes/nav_web_md.md)] has the following syntax.  
  
```  
<http|https>://<webserver>[:<port>]/<webserverinstance>/WebClient/default.aspx?report=<ID>&[tenant=<tenantID>]&[company=<companyname>]  
```  
  
### Syntax Key  
 The following table describes the notation that is used to indicate address syntax.  
  
|Notation|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|Text without brackets|Parameters that you must type as shown.|  
|\<\>|A placeholder for values that you must supply. Do not include the brackets in the address.|  
|\[ \]|Optional parameters. Do not include the brackets in the address.|  
|&#124;|A set of values from which to choose. Use one of the options and do not include `&#124;` in the address.|  
  
###  <a name="Building"></a> Building the Report Address  
 Use the following guidelines to write report URL syntax and create a URL:  
  
-   Place parameters in any order after `.aspx?` because the order is not important. For example, `default.aspx?company=CRONUS%20International%20Ltd.&report=5` yields the same as `default.aspx? report=5&company=CRONUS%20International%20Ltd.`.  
  
-   Separate parameters after `aspx?` with the ampersand symbol \(`&`\).  
  
-   Use `%20` for any spaces in values and names.  
  
##  <a name="Paramters"></a> Report Address Parameters  
 The following table describes the parameters of the URL for displaying a report.  
  
|Parameter|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|---------------|---------------------------------------|  
|`http&#124;https`|Specifies the Internet protocol to use. Valid options are `http` and `https`.<br /><br /> The `https` protocol helps secure the [!INCLUDE[navnow](includes/navnow_md.md)] data that is transmitted over the Internet. To use https, Secure Sockets Layer \(SSL\) must be enabled on the connection to [!INCLUDE[nav_web](includes/nav_web_md.md)]. For more information, see [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Configure%20SSL%20to%20Secure%20the%20Connection%20to%20Microsoft%20Dynamics%20NAV%20Web%20Client.md).|  
|`webserver`|Specifies the name of the computer that is running [!INCLUDE[nav_web](includes/nav_web_md.md)].|  
|`port`|Specifies the server port on which the [!INCLUDE[nav_web](includes/nav_web_md.md)] is running. The default port is 8080.|  
|`webserverinstance`|Specifies the name of the web server instance for the [!INCLUDE[nav_web](includes/nav_web_md.md)]. On IIS, this is the alias of the virtual directory of the web server instance.<br /><br /> When you install the [!INCLUDE[nav_web](includes/nav_web_md.md)] using [!INCLUDE[navnow](includes/navnow_md.md)] Setup, the web server instance is given the same name as the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that it connects to. If you use the [T:Microsoft.Dynamics.Nav.Management.Cmdlets.New\-NAVWebServerInstance](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVWebServerInstance) cmdlet to add [!INCLUDE[nav_web](includes/nav_web_md.md)] instances, then you specify the web server instance name. For more information, see [How to: Set Up Multiple Web Server Instances for the Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Set%20Up%20Multiple%20Web%20Server%20Instances%20for%20the%20Microsoft%20Dynamics%20NAV%20Web%20Client.md).|  
|`default.aspx`|Specifies the name of the active server page \(.aspx\) file to use to display the report.|  
|`ID`|The ID of the report in [!INCLUDE[navnow](includes/navnow_md.md)].|  
|tenant|Specifies the ID of the tenant to connect to. You must provide this parameter when [!INCLUDE[navnow](includes/navnow_md.md)] is deployed in multitenant architecture. The tenant that you specify must be mounted on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that the [!INCLUDE[nav_web](includes/nav_web_md.md)] connects to. For more information, see [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md).|  
|`company`|The name of the company in [!INCLUDE[navnow](includes/navnow_md.md)] for which you want to display the page.<br /><br /> If you do not choose a company, then [!INCLUDE[nav_web](includes/nav_web_md.md)] uses the company that is defined in the web.config file. If no company is defined in the web.config file, then the last company opened by the user is displayed.|  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Install the Web Server Components](../Topic/How%20to:%20Install%20the%20Web%20Server%20Components.md)   
 [Developing for the Microsoft Dynamics NAV Web Client](Developing-for-the-Microsoft-Dynamics-NAV-Web-Client.md)   
 [How to: Open the Microsoft Dynamics NAV Web Client](../Topic/How%20to:%20Open%20the%20Microsoft%20Dynamics%20NAV%20Web%20Client.md)