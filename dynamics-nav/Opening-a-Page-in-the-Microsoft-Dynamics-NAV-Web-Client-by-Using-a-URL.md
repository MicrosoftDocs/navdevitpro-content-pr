---
title: "Opening a Page in the Microsoft Dynamics NAV Web Client by Using a URL"
ms.custom: na
ms.date: 12/22/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: d59e6e32-dc24-47ee-a541-0534f021074d
caps.latest.revision: 29
manager: edupont
---
# Opening a Page in the Microsoft Dynamics NAV Web Client by Using a URL
You can open a specific page in the [!INCLUDE[nav_web](includes/nav_web_md.md)] by typing the page's URL in the address of a web browser. You can use the URL as a hyperlink to the page, which you can include in other sources, such as emails or Word documents, or you can it send to other users.  
  
> [!IMPORTANT]  
>  Certain data in the URL, such as company name, could be considered sensitive information. Use discretion if you distribute URLs that contain the company name, or if it is possible, exclude this information from the address.  
  
 This topic includes the following sections:  
  
-   [Example](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Example)  
  
-   [Page Address Syntax](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Syntax)  
  
-   [Building the Page Address](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Building)  
  
-   [URL Parameters](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Paramters)  
  
-   [Filtering Data on the Page](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Filtering)  
  
##  <a name="Example"></a> Example  
 The following URL displays page 9305 Sales Order List for the [!INCLUDE[demoname](includes/demoname_md.md)] company. The page is displayed in a [!INCLUDE[nav_web](includes/nav_web_md.md)] that is running on port 8080 of a computer that has the name MyWebServer.  
  
```  
http://MyWebServer:8080/nav_server_instance/WebClient/default.aspx?company=CRONUS%20International%20Ltd.&page=9305  
```  
  
 There are several parameters that define the address for the page. These parameters are described in the [URL Parameters](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Paramters) section of this topic. You can also filter the data on specific fields of the page. For information about how to filter the data, see [Filtering Data on the Page](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Filtering).  
  
##  <a name="Syntax"></a> Page Address Syntax  
 The address to open a page in the [!INCLUDE[nav_web](includes/nav_web_md.md)] has the following syntax.  
  
```  
<http|https>://<webserver>[:<port>]/<webserverinstance>/WebClient/<default|blank>.aspx?<page>=<ID>&[tenant=<tenantID>]&[company=<companyname>]&[mode=<View|Edit|Create>]  
```  
  
 The URL consists of two parts, the web server part and the [!INCLUDE[navnow](includes/navnow_md.md)] content part. The web server part targets a specific site on the computer that is running [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] and includes the following syntax.  
  
```  
<http|https>://<webserver>[:<port>]/<webserverinstance>/WebClient  
```  
  
 The [!INCLUDE[navnow](includes/navnow_md.md)] content part includes the rest of the address after `WebClient`. This part of the address is composed of an active server page extended (ASPX) file and a query string that specifies the page to display.  
  
### Syntax Key  
 The following table describes the notation that is used to indicate address syntax.  
  
|Notation|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|Text without brackets|Parameters that you must type as shown.|  
|<>|A placeholder for values that you must supply. Do not include the brackets in the address.|  
|[]|Optional parameters. Do not include the brackets in the address.|  
|&#124;|A set of values from which to choose. Use one of the options and do not include &#124; in the address.|  
  
###  <a name="Building"></a> Building the Page Address  
 Use the following guidelines to write page URL syntax and create a URL:  
  
-   Place parameters in any order after `aspx?` because the order is not important. For example, the following URLs will yield the same results.  
  
    ```  
    http://MyWebServer:8080/nav_server_instance/WebClient/default.aspx?company=CRONUS%20International%20Ltd.&page=9305&mode=View  
    ```  
  
    ```  
    http://MyWebServer:8080/nav_server_instance/WebClient/default.aspx?page=9305&mode=View&company=CRONUS%20International%20Ltd.  
    ```  
  
-   Separate parameters after `aspx?` with the ampersand symbol (`&`).  
  
-   Use `-` for any spaces in values and names.  
  
-   Enclose values in single quotation marks (`''`).  
  
##  <a name="Paramters"></a> URL Parameters  
 The following table describes the parameters of the URL for displaying a page.  
  
|Parameter|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|---------------|---------------------------------------|  
|`http`&#124;`https`|Specifies the Internet protocol to use. Valid options are `http` and `https`.<br /><br /> The `https` protocol helps secure the [!INCLUDE[navnow](includes/navnow_md.md)] data that is transmitted over the Internet. To use https, Secure Sockets Layer \(SSL\) must be enabled on the connection to [!INCLUDE[nav_web](includes/nav_web_md.md)]. For more information, see [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](How-to--Configure-SSL-to-Secure-the-Connection-to-Microsoft-Dynamics-NAV-Web-Client.md).|  
|`webserver`|Specifies the name of the computer that is running [!INCLUDE[nav_web](includes/nav_web_md.md)].|  
|`port`|Specifies the server port on which the [!INCLUDE[nav_web](includes/nav_web_md.md)] is running. The default port is 8080.|  
|`webserverinstance`|Specifies the name of the web server instance for the [!INCLUDE[nav_web](includes/nav_web_md.md)]. On IIS, this is the alias of the virtual directory of the web server instance.<br /><br /> When you install the [!INCLUDE[nav_web](includes/nav_web_md.md)] using [!INCLUDE[navnow](includes/navnow_md.md)] Setup, the web server instance is given the same name as the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that it connects to. If you use the New-NAVWebServerInstance cmdlet to add [!INCLUDE[nav_web](includes/nav_web_md.md)] instances, then you specify the web server instance name. For more information, see [How to: Set Up Multiple Web Server Instances for the Microsoft Dynamics NAV Web Client](How-to--Set-Up-Multiple-Web-Server-Instances-for-the-Microsoft-Dynamics-NAV-Web-Client.md).|  
|`default`&#124;`blank`|Specifies the name of the active server page file to use to display the page. You can use either of the following types, regardless what the page type is: `default` or, `blank`.<br /><br /> The type that you set is not important because the [!INCLUDE[nav_web](includes/nav_web_md.md)] will automatically redirect to the appropriate page. **Important:**  You cannot use `blank` to open a RoleCenter type page. Use `default` instead.|  
|`company`|The name of the company in [!INCLUDE[navnow](includes/navnow_md.md)] for which you want to display the page.<br /><br /> If you do not choose a company, then [!INCLUDE[nav_web](includes/nav_web_md.md)] uses the company that is defined in its web.config file. If no company is defined in the web.config file, then the company last opened by the user is used.|  
|`bookmark`|Specifies a record in the underlying table of the page. The value of a bookmark is an alphanumeric string of characters, for example, 27%3bEgAAAAJ7CDAAMQA5ADAANQA4ADkAMw%3d%3.<br /><br /> For the page types Card, CardPart, and Document, the bookmark specifies the record that is shown in the page. For page types List, ListPart, and Worksheet, the bookmark specifies the record that is selected in the list on the page. **Important:**  Bookmarks are generated automatically. You can only determine a value for the bookmark by displaying the page in the [!INCLUDE[nav_web](includes/nav_web_md.md)] and looking at its address. Therefore, a bookmark is only relevant when the address you are working with has been copied from another instance of the page in the [!INCLUDE[nav_web](includes/nav_web_md.md)].|  
|`page`|The ID of the page in [!INCLUDE[navnow](includes/navnow_md.md)].|  
|`mode`|Specifies the mode in which to display the page.<br /><br /> -   `View`<br />     The page can only be viewed. The user cannot change data on the page. **Note:**      Worksheet page types only display in the edit mode, even if the value is set to `View`.<br />-   `Edit`<br />     The user can change data on the page. **Note:**      To use the edit mode, the [Editable Property](Editable-Property.md) of the page in Page Designer must be set to **Yes**.     This mode is not supported for pages of the type List, RoleCenter, and CardPart. If you set the value to `Edit`, pages of these types still display in the view mode.     For List type pages, the user can modify the list by choosing **Edit List** in the ribbon of the page in [!INCLUDE[nav_web](includes/nav_web_md.md)].<br />-   `Create`<br />     Opens a blank page that enables the user to create a new item. **Note:**      This mode is not supported for pages of the type CardPart, List, ListPart, RoleCenter, and Worksheet. For pages of the type CardPart, List, and ListPart, the page displays in the view mode. Do not use this mode for Worksheet pages; otherwise you will get an error when you try to open the page.|  
|`showribbon`|Specifies whether or not to show the ribbon when the specified page opens. The default value, if the parameter is not specified, is `1` which displays the ribbon. Use the value `0` to not show the ribbon. **Note:**  This parameter only works for pages of the list page type.|  
|`shownavigation`|Specifies whether or not to show the navigation pane when the specified page opens. The default value, if the parameter is not specified, is `1` which displays the navigation pane. Use the value `0` to not show the navigation pane. **Note:**  This parameter only works for pages of the list page type.|  
|`showuiparts`|Specifies whether or not to show UI parts when the specified page opens. The default value, if the parameter is not specified, is `1` which displays the UI parts. Use the value `0` to not show UI parts. **Note:**  This parameter only works for pages of the list page type.|  
|`tenant`|Specifies the ID of the tenant to connect to. You must provide this parameter when [!INCLUDE[navnow](includes/navnow_md.md)] is deployed in multitenant architecture. The tenant that you specify must be mounted on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that the [!INCLUDE[nav_web](includes/nav_web_md.md)] connects to. For more information, see [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md).|  
|`profile`|Specifies the ID of the profile to open in [!INCLUDE[navnow](includes/navnow_md.md)]. For more information, see [How to: Open the Microsoft Dynamics NAV Web Client](How-to--Open-the-Microsoft-Dynamics-NAV-Web-Client.md).|  
|`captionhelpdisabled`|Specifies that the ability to look up Help by clicking a field caption is disabled. By default Help is always available from field captions. Set `captionhelpdisabled=1` to have this parameter take effect. **Note:**  The parameter needs to be added at the first request when the user logs on to take effect, adding the parameter on an existing session has no effect.|
|`redirect`|When users run the [!INCLUDE[nav_web_md](includes/nav_web_md.md)] in a browser, they will be presented with an option to download the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] instead in order to improve the user experience. However, if this is not a wanted scenario, this experience can be manually overridden by adding the parameter ```?redirect=0``` to the URL.|    
  
 For more information about framing the Web client, see [Embedding Microsoft Dynamics NAV Web Client Pages in Other Websites](Embedding-Microsoft-Dynamics-NAV-Web-Client-Pages-in-Other-Websites.md).  
  
##  <a name="Filtering"></a> Filtering Data on the Page  
 You can filter the data that is displayed in the page by using the filter parameter in the address. The filter parameter enables you to display only records from the underlying table of the page that have specific values for one or more fields.  
  
### Example  
 The following address displays data in page 9305 only for the customer who has the Sell-to Customer No. 10000 and the Location Code Blue.  
  
```  
http://MyWebServer:8080/nav_server_instance/WebClient/default.aspx?company=CRONUS%20International%20Ltd.&page=9305&filter='Sell-to-Customer-No.'-IS-'10000'-AND-'Location-Code'-IS-'BLUE'  
```  
  
### Filter Syntax  
 The filter has the following syntax.  
  
```  
&filter='<field>'-IS-'<value>'[-AND-'<field>'-IS-'<value>']  
```  
  
 You can add the filter anywhere in the address after `.aspx?`.  
  
> [!TIP]  
>  The filter syntax for a page in the [!INCLUDE[nav_web](includes/nav_web_md.md)] is the same as a page in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)], which you can see by choosing the **Copy Link to Page** action on the **Application** menu in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  
  
### Filter Parameters  
 The following table describes the filter parameters.  
  
|Parameter|Description|  
|---------------|-----------------|  
|`field`|The name of the table field on which to filter.|  
|`-IS-`|Specifies the equal operator.|  
|`value`|The value of the table field on which to filter.|  
|`-AND-`|Use this parameter to specify more than one filter. It specifies an “and” operator for adding additional filters. Place `-AND-` between each additional filter.<br /><br /> To be included in the page data, the table record must match values for all fields in the filter.|  
  
## See Also  
 [Deploying the Microsoft Dynamics NAV Web Server Components](Deploying-the-Microsoft-Dynamics-NAV-Web-Server-Components.md)   
 [How to: Install the Web Server Components](How-to--Install-the-Web-Server-Components.md)   
 [Developing for the Microsoft Dynamics NAV Web Client](Developing-for-the-Microsoft-Dynamics-NAV-Web-Client.md)   
 [How to: Open the Microsoft Dynamics NAV Web Client](How-to--Open-the-Microsoft-Dynamics-NAV-Web-Client.md)