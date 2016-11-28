---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVTenant

## SYNOPSIS
Gets the tenants that are mounted against the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### UseNST
```
Get-NAVTenant [[-Tenant] <TenantId>] [-ServerInstance] <String> [-Force]
```

### UseDatabase
```
Get-NAVTenant [[-Tenant] <TenantId>] -ApplicationDatabaseServer <String> -ApplicationDatabaseName <String>
 [-Force]
```

### UseDatabaseSqlAuth
```
Get-NAVTenant [[-Tenant] <TenantId>] -ApplicationDatabaseServer <String>
 -ApplicationDatabaseCredentials <PSCredential> -ApplicationDatabaseName <String> [-Force]
```

## DESCRIPTION
Gets the tenants that are mounted against the specified Microsoft Dynamics NAV Server instance.
You can use the Mount-NAVTenant and Dismount-NAVTenant cmdlets to mount and dismount tenants.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVTenant -ServerInstance 'DynamicsNAV'

State                  : Mounted
ServerInstance         : MicrosoftDynamicsNavServer$DynamicsNAV
Id                     : Tenant1
DatabaseName           : Demo Database NAV
DatabaseServer         : localhost
AlternateIds           : {}
AllowAppDatabaseWrites : True
NasServicesEnabled     : False
DefaultCompany         : 
DefaultTimeZone        : UTC
```

Description

-----------

This example gets the tenant information from the Dynamics NAV Server instance called DynamicsNAV.
The output is a list of the tenant information about all mounted tenants.

## PARAMETERS

### -ApplicationDatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance uses to access the application database in SQL Server when using SQL Server Authentication.
This parameter is only relevant when you set with the ApplicationDatabaseServer and ApplicationDatabaseName parameters

```yaml
Type: PSCredential
Parameter Sets: UseDatabaseSqlAuth
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseName
Specifies the name of the application database that is used by the tenant database.
This parameter is only relevant if the Microsoft Dynamics NAV Server instance is configured for multitenancy.
This parameter, together with the ApplicationDatabaseServer parameter, enables you to dismount a tenant from a Microsoft Dynamics NAV Server instance without having a running connection to the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: UseDatabase, UseDatabaseSqlAuth
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseServer
Specifies the SQL Server name and instance, such as MyServer\MyInstance, that hosts the application database that is used with the tenant database.
This parameter, together with the ApplicationDatabaseName parameter, enables you to get the tenants that are mounted on a Microsoft Dynamics NAV Server instance without having a running connection to the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: UseDatabase, UseDatabaseSqlAuth
Aliases: 

Required: True
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

### -Tenant
Specifies the ID of the specific tenant that you want to get information about, such as Tenant1.
If you do not set the Tenant parameter, the Get-NAVTenant cmdlet returns all tenants that are mounted against the Microsoft Dynamics NAV Server instance.
When using Get-NAVTenant through a connection to a Microsoft Dynamics NAV Server instance, if the specified tenant ID is not found, then an error occurs.
When using Get-NAVTenant through a connection to the application database, if the specified tenant ID is not found, then all mounted tenants are returned in the results.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Dynamics.Nav.Types.NavTenantSettings

## NOTES
## RELATED LINKS

