---
title: "Introduction to Dynamics CRM Integration Customization in Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 87918c6d-eb00-48bf-aaa8-b995ba718b5e
caps.latest.revision: 4
manager: edupont
---
# Introduction to Dynamics CRM Integration Customization in Dynamics NAV
This topic provides an overview about customizing [!INCLUDE[crm](includes/crm_md.md)] integration in [!INCLUDE[navnow](includes/navnow_md.md)].  
  
## Integration Objects  
 The following table describes the main objects in the [!INCLUDE[navnow](includes/navnow_md.md)] database that are related to customizing [!INCLUDE[crm](includes/crm_md.md)] integration.  
  
|Object|Description|  
|------------|-----------------|  
|Integration table|Table that represents an entity in [!INCLUDE[crm](includes/crm_md.md)]. The integration table includes fields that correspond to fields in the entity. The integration table acts as a link or connector between the [!INCLUDE[navnow](includes/navnow_md.md)] table and the [!INCLUDE[crm](includes/crm_md.md)] entity. For example, for integrating the [!INCLUDE[crm](includes/crm_md.md)] accounts entity, the [!INCLUDE[navnow](includes/navnow_md.md)] database includes the integration table **\($ T\_5341 CRM\_Accounts $\)**. There must be an integration table for each [!INCLUDE[crm](includes/crm_md.md)] entity that you want to integrate in [!INCLUDE[navnow](includes/navnow_md.md)].<br /><br /> You create an integration table by using the [T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.New\-NAVCrmTable](assetId:///T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.New-NAVCrmTable) in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)].|  
|Business data table|Table for [!INCLUDE[navnow](includes/navnow_md.md)] record type that will integrate with the [!INCLUDE[crm](includes/crm_md.md)] entity. For example, to integrate with the [!INCLUDE[crm](includes/crm_md.md)] Campaign entity, this would be the table **5071 \($ T\_5071 Campaign $\)**.|  
|Table **5335 \($ T\_5335 Integration Table Mappings $\)**|Contains the integration table mappings that link the business data table to the integration table for the [!INCLUDE[crm](includes/crm_md.md)] entity. For each entity in [!INCLUDE[crm](includes/crm_md.md)] that you want to synchronize with data in [!INCLUDE[navnow](includes/navnow_md.md)], there must be a corresponding integration table mapping.|  
|Table **5336 \($ T\_5335 Integration Field Mappings $\)**|Contains the integration field mappings that associate fields in [!INCLUDE[crm](includes/crm_md.md)] entity record with fields in a [!INCLUDE[navnow](includes/navnow_md.md)] record. The mapping is used to determine which data to synchronize between [!INCLUDE[crm](includes/crm_md.md)] and [!INCLUDE[navnow](includes/navnow_md.md)] records. The field mappings define which field in [!INCLUDE[navnow](includes/navnow_md.md)] corresponds to which field in [!INCLUDE[crm](includes/crm_md.md)].|  
|Coupling page|Provides the user interface that enables users to couple a [!INCLUDE[navnow](includes/navnow_md.md)] record to a [!INCLUDE[crm](includes/crm_md.md)] record. To integrate any [!INCLUDE[crm](includes/crm_md.md)] entity record with a [!INCLUDE[navnow](includes/navnow_md.md)] record the two records must be coupled. The default [!INCLUDE[crm](includes/crm_md.md)] integration includes several coupling pages, such as page **5241 \($ N\_5241 CRM Coupling Customer $\)** and **5242 \($ N\_5242 CRM Coupling Contact $\)**. You can create your own coupling page from scratch or use one of the existing coupling pages as a starting point.|  
|Codeunit **5150 Integration Management**|Contains logic that controls the integration between [!INCLUDE[crm](includes/crm_md.md)] and [!INCLUDE[navnow](includes/navnow_md.md)]. For example, to integrate a [!INCLUDE[navnow](includes/navnow_md.md)] table with [!INCLUDE[crm](includes/crm_md.md)] entity, the table must be registered as an integration record in the codeunit.|  
|Codeunit **5331 CRM Coupling Management**|Controls the coupling between [!INCLUDE[crm](includes/crm_md.md)] records and [!INCLUDE[navnow](includes/navnow_md.md)] records.|  
|Codeunit **5334 CRM Setup Defaults**|Controls the default [!INCLUDE[crm](includes/crm_md.md)] integration setup. For example, in order to be included in the default [!INCLUDE[crm](includes/crm_md.md)] setup, an integration table mapping must be is registered in this codeunit.|  
|Codeunit **5340 CRM Integration Table Synch.**|Contains complex table mappings and synchronization rules.|  
  
## Getting Started  
 The following list outlines the typical tasks required to integrate a [!INCLUDE[crm](includes/crm_md.md)] entity and a [!INCLUDE[navnow](includes/navnow_md.md)] table \(record type\). For step\-by\-step procedures for each of these tasks, see [Walkthrough: Customizing Microsoft Dynamics CRM Integration in Dynamics NAV](../Topic/Walkthrough:%20Customizing%20Microsoft%20Dynamics%20CRM%20Integration%20in%20Dynamics%20NAV.md).  
  
1.  Create an integration table for the [!INCLUDE[crm](includes/crm_md.md)] entity.  
  
     Use the New\-NAVCrmTable cmdlet in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] to create the table in your [!INCLUDE[navnow](includes/navnow_md.md)] database.  
  
2.  Create a list page that uses the integration table as its source.  
  
     This page can be used to display a list of all records in the [!INCLUDE[crm](includes/crm_md.md)] entity. You can then use this page in your coupling page to enable users to select which [!INCLUDE[crm](includes/crm_md.md)] record to couple to the [!INCLUDE[navnow](includes/navnow_md.md)] record.  
  
3.  Enable the coupling of [!INCLUDE[crm](includes/crm_md.md)] entity records and [!INCLUDE[navnow](includes/navnow_md.md)] records.  
  
    1.  Modify codeunit **5150 Integration Management** to enable integration records on the [!INCLUDE[navnow](includes/navnow_md.md)] business data table that will integrate with the [!INCLUDE[crm](includes/crm_md.md)] entity.  
  
    2.  Create a coupling page that end\-users can use to couple [!INCLUDE[crm](includes/crm_md.md)] records and [!INCLUDE[navnow](includes/navnow_md.md)] records.  
  
         You can base the new page on an existing coupling page.  
  
    3.  Add an action on the list page and card page for the [!INCLUDE[navnow](includes/navnow_md.md)] records that links to the new coupling page.  
  
    4.  Modify codeunit **5331 CRM Coupling Management** to include a function for handling the coupling of [!INCLUDE[crm](includes/crm_md.md)] records and [!INCLUDE[navnow](includes/navnow_md.md)].  
  
    5.  Add an action on the list page and card page for the [!INCLUDE[navnow](includes/navnow_md.md)] records that lets users open coupled records in [!INCLUDE[crm](includes/crm_md.md)].  
  
    6.  Modify codeunit **5334 CRM Setup Defaults**.  
  
         Add code to the `GetTableIDCRMEntityNameMapping` function to register the integration table and the business data table.  
  
4.  Add an integration table mapping for the [!INCLUDE[crm](includes/crm_md.md)] entity and the [!INCLUDE[navnow](includes/navnow_md.md)] business table.  
  
     You can do this by modifying table **5335 \($ T\_5335 Integration Table Mapping $\)** directly or by modifying codeunit **5334 CRM Setup Defaults**.  
  
5.  Add integration field mappings to map fields of the [!INCLUDE[crm](includes/crm_md.md)] entity and the [!INCLUDE[navnow](includes/navnow_md.md)] business data table.  
  
     For each integration table mapping entry, there must be one or more an integration field mappings to map the individual fields of the records in the business table and integration table. You only have to map the fields that you want synchronized.  
  
     You can do this by modifying table **5336 \($ T\_5336 Integration Field Mapping $\)** or by modifying codeunit **5334 CRM Setup Defaults**.  
  
6.  Add an action on the list page and card page for the [!INCLUDE[navnow](includes/navnow_md.md)] records that lets users synchronize data between coupled records.  
  
     To achieve this, you will add code to the action that calls codeunit **5330 CRM Integration Management**.  
  
7.  Use events to customize the synchronization process.  
  
     Certain events are published and raised by codeunit **5335 CRM Integration Table Synch.**. You can add code that subscribes to these events and runs code when the events are raised. This enables you to add custom logic at different stages of the synchronization process.  
  
## See Also  
 [Customizing Dynamics CRM and Dynamics NAV Integration](Customizing-Dynamics-CRM-and-Dynamics-NAV-Integration.md)   
 [Events in Microsoft Dynamics NAV](Events-in-Microsoft-Dynamics-NAV.md)