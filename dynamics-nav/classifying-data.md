---
title: "Classifying Data in Dynamics NAV"
ms.author: jswymer
ms.custom: na
ms.date: 01/05/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---

# Classifying Data in [!INCLUDE[navnow_md](includes/navnow_md.md)]
[!INCLUDE[navnow_md](includes/navnow_md.md)] includes development features for tagging business data with specific classifications. Specifically, this includes data that is stored in table fields of the database and telemetry data that is emitted from the application.    

## About Data Classification
Classifying data serves different purposes. It can make data easier and more efficient to locate and retrieve, and also help to add another layer of protection and security for handling private and sensitive data. It can supplement your process for making the application compliant with legislative and regulatory requirements for collecting, storing, and using personal information. 

>[!IMPORTANT]
> You should consider the data classification features offered in [!INCLUDE[navnow_md](includes/navnow_md.md)] as the first layer of classification - done by developers (Dynamics NAV and partners) on customizations, add-ons, and extensions. The second layer is the end-users, and how they handle data they provide and that is made available to them.

## <a name="DataClassifications"></a>What are the different data classifications?
The following table describes the differents classifications that you can apply to data:

[!INCLUDE[data_classifications](includes/data_classifications.md)] 
  
## Classifying data in tables and fields
Table objects and field controls include the **DataClassification** property that you can use to tag data with one of the classifications prevously described.

-   When you add a new field to a table, the field is assigned an initial value of **ToBeClassified**.
-   FlowField and FlowFilter fields are automatically set to the **SystemMetadata** data classification. 

For more information about this property, see the following articles:
-   [DataClassification Property in C/AL](dataclassification-property.md)
-   [DataClassification Property in AL](developer/properties/devenv-dataclassification-property.md) 

### Data classification on upgrade
When you upgrade an application from a [!INCLUDE[navnow_md](includes/navnow_md.md)] version that does not contain the DataClassification property, existing tables and fields (except for FlowFields and FlowFilters) will automatically be assigned the **CustomerContent** classification. You can then access the **DataClassification** property on these tables and fields, and change the classification as needed. FlowFields and FlowFilters will be assigned the **SystemMetadata** classification automatically.

## <a name="ViewDataClassifications"></a>Viewing the current field classifications
To view the data classification on all fields, you can do one of the following:

-   From [!INCLUDE[nav_dev_long_md](includes/nav_dev_long_md.md)], in the **Tools** menu, select **Show Field Data Classification**. 
-   From the client, search for and open the **Field Data Classification** page. 
-   Create a page that has the virtual table **Field** (ID 2000000041) as its source, and open the page in the client.

To view the data classification on all tables, create a page that has the virtual table **Table Metadata** (ID 2000000136)  as its source, and open the page in the client.


## Classifying data in custom telemetry trace events
Custom telemetry trace events are defined by calls to the SENDTRACETAG function/method in the application code. The SENDTRACETAG function/method includes an optional parameter called `DataClassification` that you can use to tag the telemetry trace event with a data classification.

For more information, see the following articles:

-   [Instrumenting an Application for Telemetry](instrumenting-application-for-telemetry.md) 
-   [SENDTRACETAG Function (C/AL)](sendtracetag-function.md)
-   [SENDTRACETAG Method (AL)](developer/methods/devenv-sendtracetag-method.md)

## See Also
[How to: Create a Page to View a Virtual Table](How-to--Create-a-Page-to-View-a-Virtual-Table.md)    
