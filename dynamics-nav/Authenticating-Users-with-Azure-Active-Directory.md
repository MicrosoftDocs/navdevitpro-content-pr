---
title:"Authenticating Users with Azure Active Directory"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 24c99ff5-7c54-408c-94ff-13a151384b3f
caps.latest.revision: 17
---
# Authenticating Users with Azure Active Directory
Azure Active Directory \(Azure AD\) is a cloud service that provides identity and access capabilities, such as for applications on Microsoft Azure, Microsoft Office 365, and for applications that install on\-premises. If the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance is configured to use the AccessControlService credential type, you can associate the [!INCLUDE[navnow](includes/navnow_md.md)] user accounts with Azure AD accounts that users use to access the [!INCLUDE[nav_web](includes/nav_web_md.md)], [!INCLUDE[nav_windows](includes/nav_windows_md.md)], Office 365, and SharePoint.  
  
 For example, your users access a website, such as a SharePoint site. From there, they have single sign\-on access to [!INCLUDE[navnow](includes/navnow_md.md)] because you have configured [!INCLUDE[navnow](includes/navnow_md.md)] for Azure AD.  
  
## Azure AD and [!INCLUDE[navnow](includes/navnow_md.md)]  
 You can use the Azure AD service to associate your existing Microsoft account with your [!INCLUDE[navnow](includes/navnow_md.md)] user account and achieve single sign\-on between the [!INCLUDE[nav_web](includes/nav_web_md.md)] and Office 365. Also, if you use [!INCLUDE[navnow](includes/navnow_md.md)] in an app for SharePoint, you can use Azure AD to achieve single sign\-on between the [!INCLUDE[nav_web](includes/nav_web_md.md)] and SharePoint. You can still host the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance and [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]on\-premises. You do not have to deploy [!INCLUDE[navnow](includes/navnow_md.md)] on Azure to use Azure AD for user authentication.  
  
### Creating an Azure AD Tenant  
 If you have an Office 365 subscription that is based on a domain such as *solutions.onmicrosoft.com*, you are already using Azure AD because the user accounts are based on Azure AD. Then, if you add the email addresses for those user accounts to the user accounts in [!INCLUDE[navnow](includes/navnow_md.md)], the users experience seamless integration between your SharePoint site and the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
 If you want to sign up for an Office 365 plan, you can use a plan such as Office 365 Enterprise E1 as your test site, or sign up for a trial developer plan. A trial plan includes an administrative account which you will use to access the Azure management portal. For example, if your Office 365 site is *Solutions.onmicrosoft.com*, your administrative account can be *admin@solutions.onmicrosoft.com*. For more information, see [Select an Office 365 plan for business](http://go.microsoft.com/fwlink/?LinkId=309050).  
  
 Alternatively, you can sign up for an Azure subscription that is not associated with an Office 365 subscription. You can sign up in the Azure management portal at [http:\/\/manage.windowsazure.com](http://manage.windowsazure.com). Then, you can configure an Active Directory, which creates an Azure AD tenant. For more information, see [Administering your Azure AD tenant](http://go.microsoft.com/fwlink/?LinkId=317423).  
  
 When you create a directory in the Azure management portal, you must specify a domain name that identifies your Azure AD tenant, such as *solutions.onmicrosoft.com*. You will use the domain name when you add users to your Azure AD.  
  
 When you have created the Azure AD tenant, you must add users. For more information, see [User account management](http://go.microsoft.com/fwlink/?LinkId=317435).  
  
### Configuring [!INCLUDE[nav_server](includes/nav_server_md.md)] for Azure AD  
 The [!INCLUDE[nav_server](includes/nav_server_md.md)] instances that must support Azure AD must be configured to use AccessControlService as the credential type. The AccessControlService credential type for the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance includes support for Azure AD so that you can achieve single sign\-on between the SharePoint site and [!INCLUDE[navnow](includes/navnow_md.md)].  
  
 You must also specify the location of the federation metadata. The federation metadata is used to establish a trust relationship between [!INCLUDE[navnow](includes/navnow_md.md)] and Azure AD. You must specify the federation metadata document URL that you retrieved from the Azure AD overview page in the configuration settings for the [!INCLUDE[nav_server](includes/nav_server_md.md)] instances. The federation metadata location is part of the client services section of the [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration. For example, in the [!INCLUDE[nav_admin](includes/nav_admin_md.md)], on the **Client Services** tab, the **Federation Metadata Location** field specifies the location, such as **https:\/\/login.windows.net\/Solutions.onmicrosoft.com\/FederationMetadata\/2007\-06\/FederationMetadata.xml**.  
  
 To configure SOAP and OData web services for Azure AD authentication, in the [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration, you must specify the App ID URI that is registered for [!INCLUDE[navnow](includes/navnow_md.md)] in the Azure AD. The App ID URI is typically the same as the *wtrealm* parameter value of the **ACSUri** setting in the configuration files for the [!INCLUDE[nav_web](includes/nav_web_md.md)] and [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  
  
 You can configure the [!INCLUDE[nav_server](includes/nav_server_md.md)] instances in the [!INCLUDE[nav_admin](includes/nav_admin_md.md)] and by using [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets. For more information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md).  
  
### Configuring [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] for Azure AD  
 The [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)] that must support Azure AD must also be configured to use AccessControlService as the credential type.  
  
 Also, you must specify an ACSUri for Azure AD authentication. The ACSUri specifies the authentication page for your Azure AD tenant, such as the following: `https://login.windows.net/Solutions.onmicrosoft.com/wsfed?wa=wsignin1.0%26wtrealm=https%3a%2f%2fSolutions.onmicrosoft.com%2fNAV`, where *Solutions.onmicrosoft.com* is the domain of your Azure AD tenant, and *wtrealm\=https%3a%2f%2fSolutions.onmicrosoft.com* is the App ID URI.  
  
### Configuring [!INCLUDE[nav_windows](includes/nav_windows_md.md)] for Azure AD  
 The [!INCLUDE[nav_windows](includes/nav_windows_md.md)] must also be configured to use AccessControlService as the credential type in order to support Azure AD. The ACSUri for Azure AD authentication should have the following format `https://login.windows.net/<tenant>/wsfed?wa=wsignin1.0%26wtrealm=<realm>%26wreply=<reply>`. The \<reply\> parameter in the URL must be equal to the \<App URL\>, for example, **https:\/\/www.solutions.onmicrosoft.com\/DynamicsNAV\/WebClient**. For a list of parameters, see the section [Adding Microsoft Dynamics NAV to your Azure AD Tenant](#AddingToWAAD) later in this topic.  
  
### Associating the Azure AD Accounts with the [!INCLUDE[navnow](includes/navnow_md.md)] User Accounts  
 Each user in your Azure AD tenant that will access [!INCLUDE[navnow](includes/navnow_md.md)] must be set up in [!INCLUDE[navnow](includes/navnow_md.md)]. For example, create the users with Windows authentication or with user name\/password authentication, depending on your deployment scenario. But you must also specify an authentication email address on the **Office 365 Authentication** FastTab in the **User Card** window. The authentication email address is the email account for that user in your Azure AD tenant. When you combine this with the relevant configuration of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance, users achieve single sign\-on when they access [!INCLUDE[nav_web](includes/nav_web_md.md)] from the SharePoint site, for example. For more information, see [How to: Create Microsoft Dynamics NAV Users](../Topic/How%20to:%20Create%20Microsoft%20Dynamics%20NAV%20Users.md).  
  
> [!IMPORTANT]  
>  The single sign\-on means that users are still signed in to Azure AD when they sign out from [!INCLUDE[navnow](includes/navnow_md.md)], unless they close all browser windows. However, if a user selected the **Keep me signed in** field when they signed in, they are still signed in when they close the browser window. To fully sign out from Azure AD, the user must sign out from each application that uses Azure AD, including [!INCLUDE[navnow](includes/navnow_md.md)] and SharePoint.  
>   
>  We recommend that you provide guidance to your users for signing out of their account when they’re done, so that you can keep your [!INCLUDE[navnow](includes/navnow_md.md)] deployment more secure.  
  
### Adding [!INCLUDE[navnow](includes/navnow_md.md)] to your Azure AD Tenant  
 You must register your [!INCLUDE[navnow](includes/navnow_md.md)] solution as an application in Azure AD tenant. Then, you can choose to make it available to other Azure AD tenants.  
  
 When you access your Azure AD tenant in the Azure management portal at [http:\/\/manage.windowsazure.com](http://manage.windowsazure.com), in the **Applications** view, you can add an application. When you add an application to an Azure AD tenant, you must specify the following information in the **Add Application** wizard:  
  
|Wizard page|[!INCLUDE[bp_tablefield](includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-----------------|---------------------------------|---------------------------------------|  
|1|Name|The name of your application as it will display to your users, such as **Financial App by Solutions**.|  
|1|Type|Choose **Web application and\/or web app**.|  
|2|App URL|The URI for signing in to your [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)], such as **https:\/\/www.solutions.com\/DynamicsNAV\/WebClient\/**.|  
|2|App ID URI|The URI to a domain in your Azure AD tenant, such as **https:\/\/solutions.onmicrosoft.com\/Financials**. **Important:**  The App ID URI must be unique within the Azure AD tenant. However, if you want to share your [!INCLUDE[navnow](includes/navnow_md.md)] solution with other Azure AD tenants, the App ID URI must be unique in Azure AD. <br /><br /> This URI is appended to the ACSUri in the configuration settings for [!INCLUDE[nav_server](includes/nav_server_md.md)] and [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)]. Additionally, in the [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration, it must be specified in the **Azure Active Directory App ID URI** setting. For more information, see [Authenticate Users with Windows Azure Active Directory](Authenticating-Users-with-Azure-Active-Directory.md).|  
|3|Directory Access|Choose **Single Sign\-On**.|  
  
 Your [!INCLUDE[navnow](includes/navnow_md.md)] solution is now registered in your Azure AD tenant. To enable single sign\-on with Azure AD, you must copy the App ID URI and the federation metadata document URL to a document of your choice for future reference. Both values are available in the overview page for the application in Azure management portal, and you will use them to configure your [!INCLUDE[nav_server](includes/nav_server_md.md)] instances.  
  
 Next, you must configure the application to be externally available. Also, you can change the logo to reflect the functionality of the application. From the overview page for [!INCLUDE[navnow](includes/navnow_md.md)] as an application, you can change configuration settings by choosing **Configure**. Then, save your changes.  
  
## Making [!INCLUDE[navnow](includes/navnow_md.md)] Available to Azure AD Tenants  
 In the overview page for the application, the **URL for Granting Access** field contains a URL that you can send to users in other Azure AD tenants. Then, when they choose the link, a page displays where they must agree to trust the application. If they accept, the app is added to their SharePoint site.  
  
## See Also  
 [Users and Credential Types](Users-and-Credential-Types.md)   
 [How to: Create Microsoft Dynamics NAV Users](../Topic/How%20to:%20Create%20Microsoft%20Dynamics%20NAV%20Users.md)   
 [How to: Sign Up for a Microsoft Account](../Topic/How%20to:%20Sign%20Up%20for%20a%20Microsoft%20Account.md)   
 [How to: Sign Up for a Microsoft Azure Subscription](../Topic/How%20to:%20Sign%20Up%20for%20a%20Microsoft%20Azure%20Subscription.md)   
 [Integrating with Office 365 and SharePoint Online](../Topic/Integrating%20with%20Office%20365%20and%20SharePoint%20Online.md)   
 [How to: Set up Microsoft Dynamics NAV for Single Sign\-on With Office 365 using Windows PowerShell](../Topic/How%20to:%20Set%20up%20Microsoft%20Dynamics%20NAV%20for%20Single%20Sign-on%20With%20Office%20365%20using%20Windows%20PowerShell.md)