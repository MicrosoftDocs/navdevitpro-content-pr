---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Remove-NAVApplication

## SYNOPSIS
Removes the tables that define the application from a Microsoft Dynamics NAV database.
When you have removed the application tables from the database, you cannot import them again.
Make sure that you have a full backup available.

## SYNTAX

```
Remove-NAVApplication [-DatabaseServer <DatabaseServer>] [-DatabaseInstance <DatabaseInstance>]
 -DatabaseName <DatabaseName> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVApplication cmdlet to delete the application tables from the specified Microsoft Dynamics NAV database.
Use this cmdlet after you have extracted the application tables to a new application database by using the Export-NAVApplication cmdlet.
For example, if you are upgrading to the current version of Microsoft Dynamics NAV, you can use the Export-NAVApplication cmdlet and the Remove-NAVApplication cmdlet during the upgrade.
Also, if you migrate to a multitenant deployment architecture, you can use the Export-NAVApplication cmdlet and the Remove-NAVApplication cmdlet when you set up the application and tenant databases.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVApplication -DatabaseName 'Demo Database NAV'
```

This example removes the application tables from the specified database on the local server.

### EXAMPLE 2
```
Remove-NAVApplication -DatabaseServer 'MyServer' -DatabaseInstance 'NAVDemo' -DatabaseName 'Demo Database NAV'
```

This example shows how to remove the application-wide tables from the demonstration database on the specified server and instance.

### EXAMPLE 3
```
Export-NAVApplication -DatabaseServer 'MyServer' -DatabaseInstance 'NAVDEMO' -DatabaseName 'Demo Database NAV' -DestinationDatabaseName 'NAV App'| Remove-NAVApplication -DatabaseName 'Demo Database NAV' -Force
```

This example shows how you can combine the Export-NAVApplication cmdlet and the Remove-NAVApplication cmdlet when you set up the application and tenant databases.
The example extracts the application tables to a new database, NAV App, and then removes the tables from the original database.
Next, you mount the two databases against a Microsoft Dynamics NAV Server instance by using the Mount-NAVApplication cmdlet and the Mount-NAVTenant cmdlet.

## PARAMETERS

### -DatabaseInstance
Specifies the name of the SQL Server instance where the Microsoft Dynamics NAV database is located.
The default value is MSSQLSERVER.

```yaml
Type: DatabaseInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name of the database that the application tables must be removed from.

```yaml
Type: DatabaseName
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer that is running SQL Server.
The default value is localhost.

```yaml
Type: DatabaseServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

## OUTPUTS

### System.String ServerName
Returns the value of the DatabaseServer parameter.

### System.String ServerInstance
Returns the value of the DatabaseInstance parameter.

### System.String DatabaseName
Returns the value of the DatabaseName parameter.

## NOTES
## RELATED LINKS
[Export-NAVApplication](Export-NAVApplication.md)  

[Mount-NAVTenant](Mount-NAVTenant.md)  
