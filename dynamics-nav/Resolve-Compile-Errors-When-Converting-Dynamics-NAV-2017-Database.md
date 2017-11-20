---
title: "Compilation Errors When Converting a Microsoft Dynamics NAV 2016 Database"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
manager: edupont
author: jswymer
---
# Resolving Compilation Errors When Converting a Dynamics NAV 2017 Database
When you convert a [!INCLUDE[nav2017](includes/nav2017.md)] database, you will receive compilation errors in several standard [!INCLUDE[navnow](includes/navnow_md.md)] objects. This article describes how to resolve these errors.

## Compilation Errors
The following table lists the compilation errors that might occur when you build the server application objects during the database conversion, with a link to a solution for fixing the problem.

|  Object Type  |  Object ID  |  Object Name  |  Function/Trigger  |  Error Message  |  Solution  |
|---------------|-------------|---------------|--------------------|------------|------------|
|Codeunit|700|Page Management|CheckAnyRoleAssignedToUser|Type conversion is not possible because 1 of the operators contains an invalid type. Text = Integer.|See [Resolving Table 5330 CRM Connection Setup Error](Resolve-Table-5330-Error-Converting-Database.md). |
|Codeunit|5330|CRM Integration Management|CheckAnyRoleAssignedToUser|You have specified an unknown variable. Entities Define the variable under 'Global C/AL symbols'.|See [Resolving Table 5330 CRM Connection Setup Error](Resolve-Table-5330-Error-Converting-Database.md). |
|Codeunit|6303|Azure AD Auth Flow|Initialize|Type conversion is not possible because 1 of the operators contains an invalid type. DotNet := GUID|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Page|9621|New Page Patterns List Part| - |TableData 2000000174 does not exist.|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|

## Codeunit 700 Page Management

In the codeunit's C/AL code, on the  `LOCAL VerifyPageID(TableID : Integer;PageID : Integer) : Boolean` function, change the `PageMetadata.APIVersion` variable to `PageMetadata.SourceTable`. 

**Before:**

```
EXIT(PageMetadata.GET(PageID) AND (PageMetadata.APIVersion = TableID));
```

**After:**

```
EXIT(PageMetadata.GET(PageID) AND (PageMetadata.SourceTable = TableID));
```

## Codeunit 5330 CRM Integration Management

In C/AL of the `LOCAL CheckRoleAssignedToUser` function, change the `PageMetadata.APIVersion` variable change the version number of the DotNet parameters and variables from 7.0.0.0 to 8.0.0.


**OrganizationServiceProxy parameter - before**
```
Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**OrganizationServiceProxy parameter - after**
```
Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```


**QueryExpression variable - before**
```
Microsoft.Xrm.Sdk.Query.QueryExpression.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**QueryExpression variable - after**
```
Microsoft.Xrm.Sdk.Query.QueryExpression.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```


**EntityCollection variable - Before:**

```
Microsoft.Xrm.Sdk.EntityCollection.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**EntityCollection variable - After**
```
Microsoft.Xrm.Sdk.EntityCollection.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```








:
Microsoft.Xrm.Sdk.EntityCollection.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'


LOCAL CheckRoleAssignedToUser(VAR OrganizationServiceProxy : DotNet "Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy";UserIDGUID : GUID;RoleIDGUID : GUID) : Boolean
CreateRoleToUserIDQueryExpression(UserIDGUID,RoleIDGUID,QueryExpression);
IF NOT ProcessQueryExpression(OrganizationServiceProxy,EntityCollection,QueryExpression) THEN
  ProcessConnectionFailures;
EXIT(EntityCollection.Entities.Count > 0);

LOCAL CheckRoleAssignedToUser(VAR OrganizationServiceProxy : DotNet "Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy";UserIDGUID : GUID;RoleIDGUID : GUID) : Boolean
CreateRoleToUserIDQueryExpression(UserIDGUID,RoleIDGUID,QueryExpression);
IF NOT ProcessQueryExpression(OrganizationServiceProxy,EntityCollection,QueryExpression) THEN
  ProcessConnectionFailures;
EXIT(EntityCollection.Entities.Count > 0);
```

**After:**

```
EXIT(PageMetadata.GET(PageID) AND (PageMetadata.SourceTable = TableID));
```





## See Also  
 [Converting a Database](Converting-a-Database.md)
