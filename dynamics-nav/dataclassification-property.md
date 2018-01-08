---
title: "DataClassification Property"
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

# DataClassification Property
Sets the classification of the data in the table or field. The data classification can be used to adhere to security, compliance, and privacy requirements and processes for collecting, storing, and using user personal information.  

## Applies to  

-   Table objects
-   Table field controls that are not specified as FlowFields or FlowFilters.

## Property Values  
|Value|Description| 
|---------------|---------------------|
|CustomerContent|Content directly provided/created by admins and users. This is the default value.|
|EndUserIdentificationInformation|(EUII) Data that identifies or could be used to identify the user of a Microsoft service. EUII does not contain Customer content. | 
|AccountData|Customer billing information and payment instrument information, including administrator contact information, such as tenant administrator’s name, address, or phone number.|  
|EndUsePseudonymousIdentifiers|(EUPI) An identifier created by Microsoft tied to the user of a Microsoft service. When EUPI is combined with other information, such as a mapping table, it identifies the end user. EUPI does not contain information uploaded or created by the customer (Customer content or EUII). |
|OrganizationIdentifiableInformation|(OII) Data that can be used to identify a tenant, generally config or usage data. This data is not linkable to a user and does not contain Customer content.| 
|SystemMetadata|Data generated in the course of running the service or program that is not linkable to a user or tenant. | 

<!--


The following table lists the possible data classification values along with a description about their intended use.

|Value|Description| Example |
|---------------|---------------------|----|  
|CustomerContent|Data that admin, licensed users, and customers (unlicensed users) provide to, transfer in, store in, or process in.| <ul><li>Customer-owned/provided secrets (for example, passwords, certificates, encryption keys, storage keys)</li><li>Customer generated blob or structured storage data</li><li>Inferences when CustomerContent data remains</li><li>Machine learning built models with data that is private/unique to a customer (for example, tenant specific dictionaries).</li><li>Contact lists</li><li>Email body or attachments</li><li>IM or Voice communications</li><li>SharePointSite content</li></ul>|
|EndUserIdentificationInformation|Data that directly identifies or could be used to identify the authenticated user. This does not contain admin data, which is considered AccountData data. This does not extend to other personal information found in CustomerContent data. Data about unauthenticated users is considered CustomerContent data. |<ul><li>User-specific IP address (IPv4)</li><li>Interface ID (last 64 bits of IPv6 address)</li><li>User Principle Name  (name@company.com)</li><li>Local-part of e-mail address (name@contoso.com)</li><li>Email subject line</li><li> User name or display name, Office number, Employee ID</li><li>Address book data</li><li>Location information of a person (including latitude/longitude)</li><li>User’s machine name </li><li>Behavioral/usage data that is linkable to an individual user</li><li>Customer-created Active Directory data (for example, identities or user names of AD end-users)</li><li>Customer Global Address List (GAL) Data (for example, name, office address, phone numbers, manager/direct reports, job title, distribution group memberships). </li><li>Full browser fingerprint</li><li>E-mail attachment names and pathh information for users’ documents. </li></ul>| 
|AccountData|Contact and billing/purchase/payment/license information for the enterprise, including the admin and any subdelegated admins.|<ul><li>Customer’s provisioning information</li><li>Account configuration and billing data </li><li>Tenant administrator contact information (for example, tenant administrator’s name, address, e-mail address, phone number).  Note: Contact information for users other than the tenant admin is considered EndUserIdentificationInformation.</li><li>Information about service health of customer machines and applications, registry data, and error-tracking files.</li><li>Licensing and purchase information.  </li></ul>|  
|EndUsePseudonymousIdentifiers|An identifier created by Microsoft that is tied to the user and customer of a Microsoft service.  When EndUsePseudonymousIdentifiers is combined with other information (such as a mapping table), it identifies the end user. EndUsePseudonymousIdentifiers does not contain information uploaded or created by the customer (that is CustomerContent or EndUserIdentificationInformation data). |<ul><li>User GUIDs or PUIDs. Other common GUIDs include: machine IDs, device IDs - Session IDs </li><li>Salted hashed EndUserIdentificationInformation data, while Microsoft retains the salt</li><li>Encrypted EEndUserIdentificationInformation data for which Microsoft retains the encryption key and can decrypt.</li></ul>|
|SystemMetadata|Data generated in the course of running the service or program that is not linkable to a user or tenant.  This does not contain CustomerContent, EndUserIdentificationInformation, AccountData, or EndUsePseudonymousIdentifiersPublic data.| <ul><li>Event logs</li><li>Access Control logs</li><li>Account information belonging to Microsoft operations personnel</li><li>Microsoft server names/server IPs</li><li>Behavioral/Usage Data</li><li>Server patching and vulnerability data</li><li>Service configuration data</li><li>Telemetry (on-prem or cloud)</li><li>SQM Data</li><li>Telecomunication region specific SHORT CODE phone numbers (for example, 911 )</li></ul>|  

-->


## Remarks  
FlowField and FlowFilter fields are automatically set the **SystemMetadata** data classification.  
  
## See Also
[Table Properties](table-properties.md)  
