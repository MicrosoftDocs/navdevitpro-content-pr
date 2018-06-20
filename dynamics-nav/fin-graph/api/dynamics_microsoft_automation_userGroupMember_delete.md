---
title: Delete userGroupMember | Microsoft Docs
description: Delete  userGroupMember objects in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: henrikwh, SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/19/2018
ms.author: henrikwh, solsen
---

# delete userGroupMembers
Removes a user from userGroupMembers object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```json
DELETE /microsoft/automation/{apiVersion}/companies({companyId})/users({userSecurityID})/userGroupMembers('{code}',{userSecurityID},'{companyName}')

```

## Request headers
|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |
|If-Match|*|
## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```204 No Content``` response code.

## Example

**Request**

Here is an example of the request.
```json
DELETE https://api.businesscentral.dynamics.com/v1.0/api/microsoft/automation/beta/companies({{companyId}})/users({{securityId}})/userGroupMembers('D365%20EXT.%20ACCOUNTANT',82ae94d5-3445-47de-8668-714b5113a9c2,'mycompany')
If-Match:*
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "code": "D365 EXT. ACCOUNTANT",
    "userSecurityID": "5bb78dd8-9b40-4fc5-bc79-a28918f9d70e",
    "companyName": "CRONUS Danmark A/S",
    "displayName": ""
}
```
<!-- 
```xml
<EntityType Name="userGroupMember">
    <Key>
        <PropertyRef Name="code" />
        <PropertyRef Name="userSecurityID" />
        <PropertyRef Name="companyName" />
    </Key>
    <Property Name="code" Type="Edm.String" Nullable="false" MaxLength="20" />
    <Property Name="userSecurityID" Type="Edm.Guid" Nullable="false" />
    <Property Name="companyName" Type="Edm.String" Nullable="false" MaxLength="30" />
    <Property Name="displayName" Type="Edm.String" MaxLength="50" />
    <NavigationProperty Name="userGroup" Type="Microsoft.NAV.userGroup" ContainsTarget="true" />
    <NavigationProperty Name="user" Type="Microsoft.NAV.user" ContainsTarget="true" />
    <NavigationProperty Name="automationCompany" Type="Microsoft.NAV.automationCompany" ContainsTarget="true" />
</EntityType>
```
 -->

## See Also
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[UserGroupMembers entity](../resources/dynamics_microsoft_automation_userGroupMembers.md)  
