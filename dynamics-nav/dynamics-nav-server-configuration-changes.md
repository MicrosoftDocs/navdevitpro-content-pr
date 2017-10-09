---
title: "Changes to Microsoft Dynamics NAV Server instance configuration"
author: edupont04
ms.date: 08/24/2017
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# Configuring Microsoft Dynamics NAV Server
This article lists new configuration settings for [!INCLUDE[nav_server_md](includes/nav_server_md.md)] instance that have been added since the previous release. These settings are available in the [!INCLUDE[nav_admin_md](includes/nav_admin_md.md)] and directly in the CustomSettings.config file of a server instance. 

##  <a name="General"></a> General tab settings  
|Setting|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-------------|---------------------------------------|
|Default Language|Specifies which of the installed [!INCLUDE[navnow](includes/navnow_md.md)] languages on the server instance will be used as the default language in the clients. Set the value to a valid language culture name, such en-US or da-DK.<br /><br /> In the [!INCLUDE[navnow](includes/navnow_md.md)] Web and Tablet clients, the **Default Language** setting determines the language that is used if the web browser's language setting does not match any installed language or a language in the **Supported Languages** setting, if used. In the [!INCLUDE[navnow](includes/navnow_md.md)] Windows client, this is the language that is used if the language setting of the computer does not have a match.<br /><br />If there are application-specific configuration settings, this setting will be overridden by the default language setting that is specified in application-specific configuration file. For more information, see [Set-NAVServerAppConfiguration cmdlet](https://go.microsoft.com/fwlink/?linkid=827798).<br /><br /> Default: en-US|
|Enable Incremental Company Deletion|Specifies whether to delete companies incrementally. If you enable this setting, when you delete a company, the company record is deleted from the database immediately but the company data that is stored in the SQL tables will be deleted later by the task scheduler.<br /><br />You can override this setting when using the [Remove-NAVCompany cmldet](Microsoft.Dynamics.Nav.Management/remove-navcompany.md) by setting the -ForceImmediateDataDeletion parameter.<br /><br />  Default: Not enabled|  
|Supported Languages|Specifies which of the installed [!INCLUDE[navnow](includes/navnow_md.md)] languages on the server instance will be available for use in the clients. If you do not specify a language, then all installed languages will be available. In the client, users can switch among the supported languages.<br /><br />The setting's value is a semicolon-separated list that contains the language culture names for each language. For example, if you want client users to be able to choose among da-DK, en-US, and en-CA, set the value to da-DK;en-US;en-CA.<br /><br />If you specify any languages in this setting, then you must include the language that you specified in the Default Language setting.<br /><br />If there are application-specific configuration settings, this setting will be overridden by the supported language setting that is specified in application-specific configuration file. For more information, see [Set-NAVServerAppConfiguration cmdlet](https://go.microsoft.com/fwlink/?linkid=827798).|

### <a name="AzureAd"></a>Azure Active Directory (Azure AD) tab settings
|  Setting  |  Description  |
|-----------|---------------|  
|  Valid Audiences |  Specifies the allowed audiences for Azure AD authentication. This setting is used to authenticate other Azure AD applications that will communicate with the server instance.<BR /><BR />The value is a semicolon-separated list of audiences. You specify an audience by using the the App URI ID or App ID that is assigned to the application in Azure AD.|

### Development tab settings (New)
The **Development** tab applies to the new [!INCLUDE[navnow](includes/navnow_md.md)] Developer for creating extensions.

|  Setting  |  Description  |
|-----------|---------------|  
| Allows Extension Target level  | Specifies the allowed target level when publishing extensions.<BR /><BR />Default: Internal|
|  Enable Developer Service Endpoint  |  Specifies whether the Developer service endpoint will be enabled.<BR /><BR />Default: Enabled|
|  Enable SSL |  Specifies whether SSL (https) is enabled for the Developer web service port.<BR /><BR />Default: Not enabled|
| HttpClient AL Function Maximum Timeout Value  |  Specifies the maximum allowed timeout value in minutes that can be set for the HttpClient Timeout AL function.<BR /><BR />Default: 00:05:00|
| HttpClient AL Function Response Size  |  Specifies the maximum size in megabytes of a response buffer used by the HttpClient AL function.<BR /><BR />Default: 15|
| Port  |  The listening HTTP port for Developer web services.<BR /><BR />Default: 7049|

## See Also  
[Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md)  
[Microsoft Dynamics NAV Server Administration Tool](Microsoft-Dynamics-NAV-Server-Administration-Tool.md) 

