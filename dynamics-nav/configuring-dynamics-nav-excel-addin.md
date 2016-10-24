---
title: "Configuring Dynamics NAV and the Excel Add-In"
author: edupont04
manager: edupont
ms.author: edupont
ms.custom: na
ms.date: 10/22/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
---
# Configuring Dynamics NAV and the Excel Add-In
In [!INCLUDE[navnow](includes/navnow_md.md)], users can work with data in Excel, get fresh data from [!INCLUDE[navnow](includes/navnow_md.md)], and update the data in [!INCLUDE[navnow](includes/navnow_md.md)] based on their work in Excel. But this requires you to configure the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance in your deployment first.  

## Prerequisites
Your deployment must meet the following prerequisites:

-   Your deployment uses Azure Active Directory to authenticate users. For more information, see [Authenticating Users with Azure Active Directory](Authenticating-Users-with-Azure-Active-Directory.md).  
-   Your deployment uses Secure Sockets Layer (SSL) for authentication for SOAP and OData web services. For more information, see [Walkthrough: Configuring Web Services to Use SSL (SOAP and OData)](Walkthrough--Configuring-Web-Services-to-Use-SSL--SOAP-and-OData-.md).  
-   If your deployment is multitenant, [!INCLUDE[nav_web](includes/nav_web_md.md)] must accept host names for tenants. For more information, see [How to: Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](How-to--Configure-the-Microsoft-Dynamics-NAV-Web-client-to-Accept-Host-Names-for-Tenants.md).  

Of those 3 prerequisites, the first two apply to all deployments. The third applies only to multitenant deployments. If these prerequisites are in place, you can proceed.  

## Creating the Excel Add-In as an Application in the Azure Management Portal
When you access your Azure AD tenant in the Azure management portal at [http://manage.windowsazure.com](http://manage.windowsazure.com), in the **Applications** view, you can add an application. When you add an application to an Azure AD tenant, you must specify the following information in the **Add Application** wizard:  

|Wizard page|[!INCLUDE[bp_tablefield](includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-----------------|---------------------------------|---------------------------------------|  
|1|Name|The name of your application as it will display to your users, such as *Excel Add-in for Dynamics NAV*.|  
|1|Type|Choose **Web application and/or web app**.|  
|2|App URL|The URI for signing in to your [!INCLUDE[nav_web_server](includes/nav_web_server_md.md)], such as *https://www.solutions.com/DynamicsNAV/WebClient/*.|  
|2|App ID URI|The URI to a domain in your Azure AD tenant, such as *https://solutions.onmicrosoft.com/ExcelAddinforDynamicsNAV*. **Important:**  The App ID URI must be unique within the Azure AD tenant and not the same as you specified for your [!INCLUDE[navnow](includes/navnow_md.md)] solution.|  
|3|Directory Access|Choose **Single Sign-On**.|  

### Grant access to your [!INCLUDE[navnow](includes/navnow_md.md)] application
When you have created the Excel add-in application, you must give it permission to access the [!INCLUDE[navnow](includes/navnow_md.md)] application in Azure AD. This allows users of the Excel add-in to access the OData web services to read and write data.  

In the configuration page for your new Azure AD application, in the section for permissions to other application, you can add the application for your [!INCLUDE[navnow](includes/navnow_md.md)] application. You must set delegated permission to the [!INCLUDE[navnow](includes/navnow_md.md)] application.  

### Configure OAuth2 authentication
The Excel add-in requires OAuth2 implicit grant flow to be enabled on the application. In the Azure portal, in the application's Configure page, the Manage Manifest button is used to download the manifest, make the necessary changes, and upload the manifest back to Azure.

The downloaded manifest for the application is a .json file. You can edit it in Notepad or similar, so that you change the *oauth2AllowImplicitFlow* key to *true*. Then, you must upload the manifest again.  

Additionally, you must make sure that the *ReplyUrl* setting is set to the following URL:
```  
https://az689774.vo.msecnd.net/dynamicsofficeapp/v1.3.0.0/*
```  

Finally, you must copy the values of the **Client ID** field for the Excel add-in application. You'll need that in the last step.

This completes the work you have to do in the Azure Management Portal. The final configuration is to add the Excel add-in to the [!INCLUDE[nav_server](includes/nav_server_md.md) instances.

## Configuring the [!INCLUDE[nav_server](includes/nav_server_md.md)] Instances
You can use either [!INCLUDE[nav_admin](includes/nav_admin_md.md)] or [!INCLUDE[nav_shell](includes/nav_shell_md.md)] to add the Excel add-in to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instances in your deployment.

In the [!INCLUDE[nav_admin](includes/nav_admin_md.md)], you must set the **Excel add-in AAD client ID** field to the client ID that you copied from the Azure Management Portal. In the [!INCLUDE[nav_shell](includes/nav_shell_md.md)], use the **Set-NAVServerConfiguration** cmdlet to set the ```ExcelAddInAzureActiveDirectoryClientId``` key to the  value that you copied from the Azure Management Portal.

## Using the Excel Add-In
Your users can now use the Excel add-in. When a list page shows the **Edit in Excel** action, then users can open lists such as the **Customers** page in Excel and work with the data there. They can use the add-in to update data in [!INCLUDE[navnow](includes/navnow_md.md)], and they can get fresh data from the database.  

> [!NOTE]  
>  The pages that your users want to work on in Excel must be published as web services.

## See Also
[Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV.md)  
[Authenticating Users with Azure Active Directory](Authenticating-Users-with-Azure-Active-Directory.md)  
[Walkthrough: Configuring Web Services to Use SSL (SOAP and OData)](Walkthrough--Configuring-Web-Services-to-Use-SSL--SOAP-and-OData-.md)  
[How to: Publish a Web Service](How-to--Publish-a-Web-Service.md)  
[How to: Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](How-to--Configure-the-Microsoft-Dynamics-NAV-Web-client-to-Accept-Host-Names-for-Tenants.md)  
