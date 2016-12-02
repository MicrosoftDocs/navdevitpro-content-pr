---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Dismount-NAVTenant

## SYNOPSIS
Dismounts a tenant on the specified Microsoft Dynamics NAV Server instance.
All active user sessions that access the tenant will end.

## SYNTAX

### UseNST
```
Dismount-NAVTenant [-Tenant] <TenantId> [-ServerInstance] <String>
 [-InputTenantRuntimeSettings <NavTenantRuntimeSettings>] [-InputTenantSettings <NavTenantSettings>] [-Force]
 [-WhatIf] [-Confirm]
```

### UseDatabase
```
Dismount-NAVTenant [-Tenant] <TenantId> -ApplicationDatabaseServer <String> -ApplicationDatabaseName <String>
 [-InputTenantRuntimeSettings <NavTenantRuntimeSettings>] [-InputTenantSettings <NavTenantSettings>] [-Force]
 [-WhatIf] [-Confirm]
```

### UseDatabaseSqlAuth
```
Dismount-NAVTenant [-Tenant] <TenantId> -ApplicationDatabaseServer <String>
 -ApplicationDatabaseCredentials <PSCredential> -ApplicationDatabaseName <String>
 [-InputTenantRuntimeSettings <NavTenantRuntimeSettings>] [-InputTenantSettings <NavTenantSettings>] [-Force]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Dismount-NAVTenant cmdlet to dismount a tenant on the specified Microsoft Dynamics NAV Server instance.
All active user sessions that access the tenant will end.

## EXAMPLES

### EXAMPLE 1
```
Dismount-NAVTenant DynamicsNAV -Tenant 'Test'
```

This example dismounts the tenant Test from the specified server instance.

### EXAMPLE 2
```
Dismount-NAVTenant DynamicsNAV Test
```

This example dismounts the tenant Test from the specified server instance without being explicit about parameter names.

### EXAMPLE 3
```
Get-NAVTenant DynamicsNAV | Dismount-NAVTenant
```

This example gets the tenant information from the DynamicsNAV90Microsoft Dynamics NAV Server instance and passes the information to the Dismount-NAVTenant cmdlet.
The tenant default is then dismounted.
The output is a list of the tenant information about all dismounted tenants.

### EXAMPLE 4
```
Dismount-NAVTenant -Tenant 'Test' -ApplicationDatabaseServer 'MySQLServer\NAV' -ApplicationDatabaseName 'MyNavAppDatabase' -ApplicationDatabaseCredentials (Get-Credential)
```

This example mounts a tenant, 'Test' by specifying an application database instead of the Microsoft Dynamics NAV Server instance.
The application database server and instance is 'MySQLServer\NAV', and the application database is 'MyNavAppDatabase'.
SQL Server authentication is configured for accessing the application database.

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
Specifies the SQL Server name and instance, such as MyServer\MyInstance, that hosts the application database that you want to use with the tenant database.
This parameter, together with the ApplicationDatabaseName parameter, enables you to dismount a tenant from a Microsoft Dynamics NAV Server instance without having a running connection to the Microsoft Dynamics NAV Server instance.

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

### -InputTenantRuntimeSettings
Specifies the Microsoft.Dynamics.Nav.Types.NavTenantSettings object that identifies the tenant that you want to dismount.
You can pass this object from the Tenant parameter on the Get-NAVTenant cmdlet to the Dismount-NAVTenant cmdlet.

```yaml
Type: NavTenantRuntimeSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputTenantSettings
Specifies the Microsoft.Dynamics.Nav.Types.NavTenantSettings object that identifies the tenant that you want to dismount.
You can pass this object from the Tenant parameter on the Get-NAVTenant cmdlet to the Dismount-NAVTenant cmdlet.

```yaml
Type: NavTenantSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies the ID of the tenant that you want to dismount from the Microsoft Dynamics NAV Server instance, such as Tenant1.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Forces the command to run without asking for user confirmation.

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

### System.String
You can pass the value of the ServerInstance parameter as a string to this cmdlet.

### Microsoft.Dynamics.Nav.Types.NavTenantRuntimeSettings
You can pass a Microsoft.Dynamics.Nav.Types.NavTenantRuntimeSettings object from the Tenant parameter on the Get-NAVTenant cmdlet to the Dismount-NAVTenant cmdlet.

### Microsoft.Dynamics.Nav.Types.NavTenantSettings
You can pass a Microsoft.Dynamics.Nav.Types.NavTenantSettings object from the Tenant parameter on the Get-NAVTenant cmdlet to the Dismount-NAVTenant cmdlet.

## OUTPUTS

### Microsoft.Dynamics.Nav.Types.NavTenantSetting
If the InputObject parameter has been bound to a value, it will be passed through to the pipeline. Otherwise no output value is returned.

## NOTES

## RELATED LINKS
[Mount-NAVTenant](Mount-NAVTenant.md)  

[Get-NAVTenant](Get-NAVTenant.md)  

[Sync-NAVTenant](Sync-NAVTenant.md)  
