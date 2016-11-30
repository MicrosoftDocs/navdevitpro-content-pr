---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Mount-NAVTenant

## SYNOPSIS
Mounts a tenant database against the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### UseNST
```
Mount-NAVTenant [-OverwriteTenantIdInDatabase] [-SkipUpdateScheduledTaskList]
 [-DatabaseCredentials <PSCredential>] [-ServerInstance] <String> [-EncryptionProvider <EncryptionProvider>]
 [-Force] [-WhatIf] [-Confirm] [-Id] <String> [-DatabaseName] <String> [-DatabaseServer <String>]
 [-AlternateId <System.Collections.ObjectModel.ReadOnlyCollection`1[System.String]>] [-AllowAppDatabaseWrite]
 [-NasServicesEnabled] [-RunNasWithAdminRights] [-DefaultCompany <String>] [-DefaultTimeZone <TimeZoneInfo>]
 [-ExchangeAuthenticationMetadataLocation <String>] [-AadTenantId <String>] [-DatabaseInstance <String>]
```

### UseDatabase
```
Mount-NAVTenant [-OverwriteTenantIdInDatabase] [-SkipUpdateScheduledTaskList]
 [-DatabaseCredentials <PSCredential>] [-ApplicationDatabaseServer <String>]
 [-ApplicationDatabaseCredentials <PSCredential>] [-ApplicationDatabaseName <String>]
 [-EncryptionProvider <EncryptionProvider>] [-Force] [-WhatIf] [-Confirm] [-Id] <String>
 [-DatabaseName] <String> [-DatabaseServer <String>]
 [-AlternateId <System.Collections.ObjectModel.ReadOnlyCollection`1[System.String]>] [-AllowAppDatabaseWrite]
 [-NasServicesEnabled] [-RunNasWithAdminRights] [-DefaultCompany <String>] [-DefaultTimeZone <TimeZoneInfo>]
 [-ExchangeAuthenticationMetadataLocation <String>] [-AadTenantId <String>] [-DatabaseInstance <String>]
```

## DESCRIPTION
Use the Mount-NavTenant cmdlet to mount a tenant database against the specified Microsoft Dynamics NAV Server instance.
The database must already exist, and it must be a valid Microsoft Dynamics NAV 2016 database.
Also, the Microsoft Dynamics NAV Server instance must be configured for multitenancy.
When a database is mounted against a Microsoft Dynamics NAV Server instance, the server can process requests for data for it.
When you mount a tenant database, the database is not synchronized against the application database.
To synchronize the tenant database against the application database, you must use the Sync-NAVTenant cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Mount-NAVTenant DynamicsNAV -Id 'Test' -DatabaseName 'Test_Database'
```

Description

-----------

This example mounts a tenant, 'Test', that is based on the tenant database 'Test_Database' on the specified Microsoft Dynamics NAV Server instance.

### EXAMPLE 2
```
Mount-NAVTenant DynamicsNAV Test Test_Database
```

Description

-----------

This example mounts a tenant, 'Test', that is based on the tenant database 'Test_Database' on the specified Microsoft Dynamics NAV Server instance.
The example uses positional arguments for the parameter values.

### EXAMPLE 3
```
Mount-NAVTenant DynamicsNAV -Id 'Test' -DatabaseName 'Test_Database' -DatabaseCredentials (Get-Credential)
```

Description

-----------

This example mounts a tenant, 'Test', that is based on the tenant database 'Test_Database' on the specified Microsoft Dynamics NAV Server instance.
The example configures SQL authentication on the connection to the database with credentials that are obtained from the Get-Credential cmdlet.

### EXAMPLE 4
```
Get-NAVTenant Server1 | Mount-NAVTenant Server2
```

Description

-----------

This example gets information about the tenants that are mounted against the Server1 Microsoft Dynamics NAV Server instance and mounts them against the Server2 instance.
You must then dismount the tenants from the Server1 instance.

### EXAMPLE 5
```
Get-NAVTenant Server1 | Dismount-NavTenant Server1 -Force | Mount-NAVTenant Server2
```

Description

-----------

This example gets information about the tenants that are mounted against the Server1 Microsoft Dynamics NAV Server instance, dismounts them, and then mounts them against the Server2 instance.

### EXAMPLE 6
```
Mount-NAVTenant DynamicsNAV -Id 'Test' -DatabaseName 'Test_Database'-AlternateId @( "test.mydomain.com", "http://mydomain.sharepoint.com/sites/teamsite" )
```

Description

-----------

This example mounts a tenant, 'Test', that is based on the tenant database 'Test_Database' on the specified Microsoft Dynamics NAV Server instance and adds a domain name and a SharePoint host URL to the alternative IDs.

### EXAMPLE 7
```
Mount-NAVTenant -Id 'Test' -DatabaseName 'Test_Database' -DatabaseCredentials (Get-Credential) -ApplicationDatabaseServer 'MySQLServer\NAV' -ApplicationDatabaseName 'MyNavAppDatabase' -ApplicationDatabaseCredentials (Get-Credential) -KeyFilePath 'C:\key\nav.key' -KeyFilePassword (Get-Credential).Password
```

Description

-----------

This example mounts a tenant, 'Test', which is based on the tenant database 'Test_Database', by specifying an application database instead of the Microsoft Dynamics NAV Server instance.
The application database server and instance is 'MySQLServer\NAV', and the application database is 'MyNavAppDatabase'.
The example configures SQL Authentication for accessing both the tenant application databases.
This example requires that you export the encryption key that is used by the Microsoft Dynamics NAV Server instance to a file with the path and file name 'C:\key\nav.key'.

## PARAMETERS

### -AadTenantId
Specifies the the GUID of the tenant in Azure Active Directory for the Dynamics NAV application.
The tenant ID is used for authenticating Dynamics NAV users with Azure AD.

The Azure AD Tenant ID identities the directory for the Microsoft Dynamics NAV application in Azure AD.
The tenant ID can be the tenant's domain name or GUID.
You can get the domain name from the Domain settings for the AD tenant (directory) in the Azure Management Portal.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllowAppDatabaseWrite
Specifies if the tenant can write to the application database.
The default value is false.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AlternateId
Specifies the alternative IDs for the tenant, such as host names for the Microsoft Dynamics NAV Web client, SOAP web services, OData web services, or the Microsoft Dynamics NAV Windows client.
If you use alternative IDs for tenant resolution in the Microsoft Dynamics NAV Web client, you must also enable some of the UrlRewrite rules in the Web.Config file for the Microsoft Dynamics NAV Web Server components.

```yaml
Type: System.Collections.ObjectModel.ReadOnlyCollection`1[System.String]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to access the application database in SQL Server.
This parameter configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the application database.
The login account must be a member of the db_owner role on the database.
This parameter is only relevant when you set with the ApplicationDatabaseServer and ApplicationDatabaseName parameters

```yaml
Type: PSCredential
Parameter Sets: UseDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseName
Specifies the name of the application database to use with the tenant database.
This parameter is only relevant if the Microsoft Dynamics NAV Server instance is configured for multitenancy.
This parameter, together with the ApplicationDatabaseServer parameter, enables you to mount a tenant to the same Microsoft Dynamics NAV Server instance as the application database without having to connect a running Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: UseDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseServer
Specifies the SQL Server name and instance, such as MyServer\MyInstance, that hosts the application database that you want to use with the tenant database,.
This parameter, together with the ApplicationDatabaseName parameter, enables you to mount a tenant to the same Microsoft Dynamics NAV Server instance as the application database without having to connect to a running Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: UseDatabase
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to access the tenant database in SQL Server.
This parameter configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the database.
The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseInstance
Specifies the name of the SQL Server instance that hosts the database.
You can also specify the instance in the DatabaseServer parameter, such as MyServer\MyInstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the Microsoft Dynamics NAV database that you want to mount against the Microsoft Dynamics NAV Server instance, such as 'Demo Database NAV (8-0)'.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the database server that hosts the Microsoft Dynamics NAV database that you want to mount against the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultCompany
Specifies the name of the company that NAS services, OData web services, and SOAP web services use if no other company is specified.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultTimeZone
Specifies the default time zone that is used by the NAS services, OData web services, and SOAP web services for this tenant.
You can set the parameter to UTC, 'Server Time Zone', or the ID of a Windows Time Zone.
UTC specifies that all business logic for services on the server instance runs in Coordinated Universal Time (UTC).
'Server Time Zone' specifies that services use the time zone of the computer that is running Microsoft Dynamics NAV Server instance.
ID of a Windows Time Zone specifies that services use a Windows time zone as defined in the system registry under HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.
For example, Romance Standard Time is a valid Windows time zone value.
If this parameter is not specified, the value is taken from the ServicesDefaultTimeZone setting in the CustomSetting.config file for the Microsoft Dynamics NAV Server instance.

```yaml
Type: TimeZoneInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionProvider
Specifies the name of the encryption provider.

```yaml
Type: EncryptionProvider
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExchangeAuthenticationMetadataLocation
Specifies the URL for Microsoft Exchange authentication metadata document of the service or authority that is trusted to sign Exchange identity tokens.
This URL is compared to the Exchange authentication metadata document URL in the Exchange identity token.
The scheme and host part of the two URLs must match to pass authentication.
Paths in the URLs require only partial match.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the tenant to mount, such as Tenant1.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Tenant

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NasServicesEnabled
Specifies to enable NAS services on the tenant.
The default value is false.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverwriteTenantIdInDatabase
Specifies if the Mount-NAVTenant cmdlet must overwrite the tenant ID in the database if the database has been mounted as a tenant earlier.
If this is false, and the tenant database has previously been mounted with a different tenant ID, an exception is thrown.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNasWithAdminRights
Specifies the NAS services to run with administrator rights.
This grants the NAS service the same permissions as the SUPER permission set in Microsoft Dynamics NAV without having to add the Microsoft Dynamics NAV Server service account as a user.
The default is false.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: UseNST
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipUpdateScheduledTaskList
Specifies if the Mount-NAVTenant cmdlet Should update the list of scheduled tasks when mounted.
If this is false the scheduled task list will not be updated.
The list of scheduled tasks can be updated with the Update-NavScheduledTaskList cmdlet

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
{{Fill Force Description}}

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### None

## NOTES
## RELATED LINKS
