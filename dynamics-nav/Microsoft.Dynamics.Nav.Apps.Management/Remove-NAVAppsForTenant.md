---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-NAVAppsForTenant

## SYNOPSIS
Removes all NAV Apps from the specified, unmounted tenant. This cmdlet should be run against tenants that are not mounted.

## SYNTAX

```
Remove-NAVAppsForTenant [-DatabaseServer <String>] [-DatabaseName <String>]
 [-DatabaseCredentials <PSCredential>] [-ApplicationDatabaseServer <String>]
 [-ApplicationDatabaseName <String>] [-ApplicationDatabaseCredentials <PSCredential>] [-DoNotSaveData] [-Force]
```

## DESCRIPTION
Use the Remove-NAVAppsForTenant cmdlet to remove all NAV Apps from a tenant database that cannot be mounted due to metadata conflicts.
This cmdlet should be run against tenants that are not mounted.
This may change the database schema so you must specify if you do not want to save data, otherwise if will be saved.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVAppsForTenant -ApplicationDatabaseName 'Demo Database NAV' -ApplicationDatabaseServer NAVSQLServer -DatabaseName Tenant1 -DatabaseServer NAVSQLServer
```

Description

-----------

This example uninstalls all of the NAV Apps in the unmounted tenant database with the name of Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized and the data will be saved.

### EXAMPLE 2
```
Remove-NAVAppsForTenant -ApplicationDatabaseName 'Demo Database NAV)' -ApplicationDatabaseServer NAVSQLServer -DatabaseName Tenant1 -DatabaseServer NAVSQLServer -DoNotSaveData
```

Description

-----------

This example uninstalls all of the NAV Apps in the unmounted tenant database with the name of Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized and the data will not be saved since the -DoNotSaveData parameter switch was provided.

## PARAMETERS

### -ApplicationDatabaseCredentials
Specifies the user name and password of a SQL Server Authentication login account that provides access to the Microsoft Dynamics NAV application database in SQL Server.

You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter.

The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseName
Specifies the name of the Microsoft Dynamics NAV database that contains the application tables in the multitenant deployment.

You must also set the ApplicationDatabaseServer parameter.

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

### -ApplicationDatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database that contains the application tables is installed in the multitenant deployment.
The default value is "." for the current machine.

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

### -DatabaseCredentials
Specifies the user name and password for a SQL Server Authentication login account that provides access to the database or tenant database (in a multitenant deployment) in SQL Server.

You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter.

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

### -DatabaseName
Specifies the name of the Microsoft Dynamics NAV database, such as 'Demo Database NAV', that stores the business data.

In a multitenant deployment, this is the name of the tenant database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TenantDatabaseName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database is installed.
The default value is "." for the current machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TenantDatabaseServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DoNotSaveData
Specifies that you do not want to copy data to an archive table if the removal of a NAV App changes the database schema.
if you set this parameter, the data will not be archived and you will not be able to restore it if you need to reinstall the NAV App.

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

### -Force
Forces the command to run without asking for user confirmation about the tenant that you are removing NAV Apps from.

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
[Get-NavAppTenant](Get-NavAppTenant.md)

[Install-NAVApp](Install-NAVApp.md)  

[Publish-NAVApp](Publish-NAVApp.md)  

[Repair-NAVApp](Repair-NAVApp.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)  

[Unpublish-NAVApp](Unpublish-NAVApp.md)  
