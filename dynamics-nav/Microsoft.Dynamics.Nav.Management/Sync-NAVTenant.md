---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Sync-NAVTenant

## SYNOPSIS
Synchronizes a tenant database schema with an application database.

## SYNTAX

```
Sync-NAVTenant [[-Tenant] <TenantId>] [[-Mode] <SyncMode>] [-CommitPerTable] [-ServerInstance] <String>
 [-Force]
```

## DESCRIPTION
Use the Sync-NAVTenant cmdlet to synchronize the database schema in a tenant database with the schema in the application database. The application database contains tables that define the application. The tenant database must contain the SQL Server tables that the application prescribes.

## EXAMPLES

### EXAMPLE 1
```
Sync-NAVTenant -ServerInstance DynamicsNAV -Tenant 'Tenant1'
```

This example synchronizes a tenant, 'Tenant1', with the application that is mounted against the specified Microsoft Dynamics NAV Server instance.

## PARAMETERS

### -CommitPerTable
Specifies that database schema modifications are committed by separate transactions on each affected table. Transactions are run one at a time, as they occur.

With the default behavior (that is, without using the -CommitPerTable parameter), all modifications are committed in a single transaction. Using this method provides better protection against leaving the database in an inconsistent state than using the -CommitPerTable parameter. If the synchronization process is terminated before it is completed, any changes that were made before the problem occurred are rolled back, returning the database to its original state. The drawback is that for large databases, the synchronization process can take a long time and consume considerable computer resources.

The advantage of setting the -CommitPerTable is that it will decrease the time that is required to complete the synchronization process and consume less computer resources, which can be useful for large databases when performance is a concern. However, when you set this parameter, committed changes are not rolled back if the synchronization process is terminated before it is completed. This can result in a partial synchronization of the database, which might leave the database inoperable. We recommend that you make a backup of the database before you run the Sync-NavTenant cmdlet. Also, tables are not always locked during synchronization. Therefore, you should prohibit users from connecting to the database during synchronization.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Specifies how the database schema for the tenant database is synchronized with the database schema that the mounted application database defines. The default value is Sync.
You can specify the parameter value by name or by integer as described in the following list:

ForceSync = 0  
The database schema in the tenant database is updated with the application database schema even if data is lost. For example, if a table or a field has been deleted in the current application, the table or field is removed from the tenant database even if it contains data.

Sync = 2  
The database schema in the tenant database will be updated unless data is lost. For example, if a table or a field has been deleted in the current application, and it contains data in the tenant database, the tenant cannot be mounted against the Microsoft Dynamics NAV Server instance.

CheckOnly = 3  
Microsoft Dynamics NAV Server tests if a change in the current application will result in data loss in the tenant database if the tenant is mounted with Mode set to ForceSync. An example of this is when a table or a field has been deleted in the current application.
and it contains data in the tenant database.

```yaml
Type: SyncMode
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that you want to synchronize with the application, such as Tenant1. The tenant will be synchronized with the Microsoft Dynamics NAV application that is mounted against the same Microsoft Dynamics NAV Server instance.

This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES
## RELATED LINKS
[Dismount-NAVTenant](Dismount-NAVTenant.md)  

[Get-NAVTenant](Get-NAVTenant.md)  

[Mount-NAVTenant](Mount-NAVTenant.md)  
