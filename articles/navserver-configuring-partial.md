<properties
                pageTitle="Configuring Microsoft Dynamics NAV Server" | Dynamics NAV"
                description="Describes the how to configure a Dynamics NAV Server instance."
                services=""
                documentationCenter=""
                authors="jswymer"/>



<!-- These updates have been done!! This article can be deleted. -->
<!-- The content in this article supports Madeira changes to the Dynamics NAV Server settings (NAV Administration Tool and CustomeSettings.config file). The content here becomes part of the ""Configuring Microsoft Dynamics NAV Server". -->

<!-- Change 1: In the section "Configuring Microsoft Dynamics NAV Server After Installation" section, in the last bullet, update the path CustomSetting.config file as follows:-->

By default, this file is located in C:\Program Files\Microsoft Dynamics NAV\91\Service\Instances\<instancename>

<!-- Change 2: In the "General Tab Settings" section, after the "Default Client" setting, add the following row for the "Diagnostic Trace Level" setting : -->

|  Diagnostic Trace Level  |  Specifies the lowest severity level of telemetry events to be recorded in the event log for the Dynamics NAV Server. Telemetry events have IDs from  700-706. <BR /><BR />The setting has the following values, which correspond to the event severity levels (listed from highest to lowest level): **Critical**, **Error**, **Warning**, **Normal** (this corresponds to the **Information** level), and **Verbose**.<BR /><BR />You use this setting to filter out lower-level events from the log. For example, if you set this setting to **Error**, only **Error** and **Critical** events will be logged.<BR /><BR />**Note:** Events are recorded in the Microsoft Dynamics NAV Server channel logs, which you can see in Event Viewer, under **Applications and Services Logs**.|

<!-- Change 3: In the "General Tab Settings" section, after the "Enable Full C/AL Function Tracing" setting, add the following row for the "Encryption KEY Provider" setting: -->

|  Encryption Key Provider  |  Specifies the encryption provider as either **LocalKeyFile** or **AzureKeyVault** values. If you use **AzureKeyVault**, see **Azure Key Vault Encryption Provider** tab settings. <BR /><BR />Default: LocalKeyFile |

<!-- Change 4: Move the "Max Data Rows Allowed to Send to Excel" row from the "Client Services" tab to the "General" tab, after the "Max Concurrent Calls" row.-->

<!-- Change 5: In the "Management Services" tab, after the "Idle Client Timeout" row, add the following row for the "Keep Alive Interval". Important: Remove the "ClientServicesKeepAliveInterval" setting from the "
Configuring the Windows Client" topic.-->
|  Keep Alive Interval  |  Specifies the time interval between keep-alive messages that are sent from the Dynamics NAV Windows client to the server instance. This setting is used to keep inactive sessions alive until the time that is specified by the **Idle Client Timeout** setting expires. You should use a time interval that is less than the **Idle Client Timeout** setting. For more information, see [Understanding Session Timeouts](administration-understanding-session-timeouts.md).<BR /><BR />
Time interval format: [dd.]hh:mm:ss[.ff] <BR /><BR />Default: 120
  |
<!-- Change 6: Add the following sections after the "Management Services" tab.-->

## Azure Key Vault Encryption Provider Tab Settings
The following table describes fields on the **Azure Key Vault Encryption Provider** tab in the Dynamics NAV Server Administration tool.

|  Setting  |  Description  |
|-----------|---------------|  
|  Client Certificate Store Location|  Specifies the location of the certificate store for the Key Vault client certificate.<BR /><BR />**LocalMachine** specifies that the certificate is stored in a certificate store for the computer that the Dynamics NAV Server is running on.<BR /><BR />**CurrentUser** specifies that the certificate is stored in a certificate store for your account on the computer that the Dynamics NAV Server is running on.<BR /><BR />Default: **LocalMachine** |
|  Client Certificate Store Name|  Specifies the certificate store where the Key Vault client certificate is stored.<BR /><BR />Default: **My** |
|  Client Certificate Thumbprint|  Specifies the thumbprint of the Key Vault client certificate<BR /><BR />Default: **My** |
|  Client ID  |  Specifies the unique identifier (GUID) of the Key Vault client application in Microsoft Azure. |
|  Key URI  |  Specifies the URI of the key in the Key Vault encryption provider setup. |

## Azure Active Directory (Azure AD) Tab Settings
The following table describes fields on the **Azure Active Directory (Azure AD)** tab in the Dynamics NAV Server Administration tool.

The settings in this tab configure the Dynamics NAV Server instance to use Azure AD authentication. The settings are only relevant when the server instance is configured Access Control Service, that is, when the **Credential Type** is set to **AccessControlService**. For more information about authenticating using Azure AD, see [Authenticating Users with Azure Active Directory](authentication-authenticatingusersazuread.md).

|  Setting  |  Description  |
|-----------|---------------|  
|  Application Client Certificate Thumbprint|  Specifies the thumbprint of the x509 certificate that is used with the Azure AD application client for authentication.<BR /><BR />A public certificate file (.cer) must be installed on the application client and associated with an Azure AD service principal.<BR /><BR />A private certificate file (.pfx) must be installed on the computer on which the Dynamics NAV Server instance is installed. The Dynamics NAV Server instance service account must have access to the private key of that certificate.|
|  Application Client ID|  Specifies the ID of the application tenant. The ID is used when accessing data in Azure AD.<BR /><BR />The authentication token for communicating with Azure AD should be retrieved by specifying the **Application Client Certificate Thumbprint**, with a fallback to use the **Application Client Secret**. |
|  Application Client Secret|  Specifies the secret to use with **Application Client ID** for Azure AD authentication. |
|  Azure AD App ID URI |  Specifies the App ID URI that is registered for Dynamics NAV in the Azure AD tenant.<BR /><BR />The App ID URI is a logical identifier for Dynamics NAV. It is used to validate the security tokens that the Dynamics NAV Server instance receives in SOAP and OData calls when the server instance is configured with Access Control Service (ACS) credential type. |
|  Enable Membership Entitlement|  Configures the server instance to use membership entitlement for controlling access the Dynamics NAV.<BR /><BR />This setting is typically only used for software as a service (SaaS) solutions .|
|  WS-Federation Login Endpoint  |  Specifies the URL for the federation sign-on page that Dynamics NAV redirects to when configured for single sign-on.<BR /><BR />You must specify a URL in the following format:<BR /><BR /> https://login.windows.net/[AADTENANTID]/wsfed?wa=wsignin1.0%26wtrealm=...%26wreply=....<BR /><BR /> The placeholder [AADTENANTID] represents the GUID of your Azure AD tenant. If the Dynamics NAV Server instance has to support multiple Azure AD tenants, then the **Azure AD Tenant ID** parameter that is specified when mounting a tenant replaces the placeholder.|
|  WS-Federation Metadata Location  |  Specifies the URL for the federation metadata document that describes the configuration information for your Azure AD tenant. The federation metadata document is used to validate the security tokens that the Dynamics NAV Web client and Dynamics NAV Tablet client receive.<BR /><BR /> You must specify a URL in the following format:<BR /><BR />https://login.windows.net/[AADTENANTID]/FederationMetadata/2007-06/FederationMetadata.xml<BR /><BR />The placeholder [AADTENANTID] represents the GUID of your Azure AD tenant. If the Dynamics NAV Server instance has to support multiple Azure AD tenants, then the Azure AD Tenant ID parameter that is specified when mounting a tenant replaces the placeholder.|

## Task Scheduler Tab Settings
The following table describes fields on the **Task Scheduler** tab in the Dynamics NAV Server Administration tool.

The task scheduler processes jobs and other processes on a scheduled basis. For more information about task scheduler, see [Task Scheduler](taskscheduler.md).

|  Setting  |  Description  |
|-----------|---------------|  
|  Enable Task Scheduler  |  Specifies whether the Dynamics NAV Server instance starts with the task scheduler enabled. <BR /><BR />If this option is enabled, the server instance will process scheduled tasks.<BR /><BR />Default: Enabled |
|  Maximum Concurrent Running Tasks  |  Specifies the maximum number of tasks that can run simultaneously on the server instance.<BR /><BR />The value that you specify will depend on the hardware (CPUs) of the deployment environment and what you want to prioritize: client performance or scheduled tasks (such as job queue entries). The setting is particularly relevant when the Dynamics NAV Server instance is used for both scheduled tasks and client services. If there are many jobs running at the same time, you might experience that the response time for clients gets slower. In which case, you could decrease the value. However, if the value is too low, it might take longer than desired for scheduled tasks to process. When you have a dedicated server instance for scheduled tasks, this setting is less important with respect to client performance. <BR /><BR />Default: 10 |

## Reports Tab Settings
The following table describes fields on the **Reports** tab in the Dynamics NAV Server Administration tool.

|  Setting  |  Description  |
|-----------|---------------|  
|  Enable Save as Excel on Request Pages of RDLC-layout Reports  |  Specifies whether users can open or save a report as an Microsoft Excel document if the report uses an RDLC layout.<BR /><BR />If you clear this check box, the **Excel** option is removed from the **Print** menu on the request page.<BR /><BR />Default: Enabled|
|  Enable Save as Word on Request Pages of RDLC-layout Reports  |  Specifies whether users can open or save a report as a Microsoft Word document if the report uses an RDLC layout.<BR /><BR /> If you clear this check box, the **Word** option is removed from the **Print** menu on the request page.<BR /><BR />Default: Enabled|
|  Enable Save from Report Preview  |  Specifies whether users can save a report as a PDF, Microsoft Word, or Microsoft Excel document from the report preview window.<BR /><BR />If you clear this check box, the **Save As** icon is removed from the report preview window.<BR /><BR />Default: Enabled|
| Report PDF Font Embedding  |  Specifies whether fonts are embedded in PDF files that are generated for reports when the report uses an RDLC report layout at runtime. This setting applies when reports are run and saved as PDF files on the Dynamics NAV client (from the report request page or print preview window) or on the Dynamics NAV Server instance (by the [SAVEAS function](function-reportsaveas.md) or [SAVEASPDF function](function-reportsaveaspdf.md) in C/AL code).<BR /><BR />**Note:** This setting does not apply when a report uses a Word report layout at runtime.<br/><br/>Embedding fonts in a PDF of a report makes sure that the PDF will use the same fonts as the original file, regardless of where the PDF is opened and which fonts are installed on the computer. However, embedding fonts can significantly increase the size of the PDF files. By disabling font embedding, you can decrease the size of the report PDF files.<BR /><BR />**Note:** This is a global setting for font embedding in report PDF files. You can override this setting on a report basis by the specifying the [PDFFontEmbedding property](property-reportpdffontembedding.md).<BR /><BR />Default: Enabled|
