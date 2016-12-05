---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Mount-NAVApplication

## SYNOPSIS
Mounts the Microsoft Dynamics NAV application against the specified server instance.

## SYNTAX

```
Mount-NAVApplication [-DatabaseServer <String>] [-DatabaseInstance <DatabaseInstance>] -DatabaseName <String>
 [-DatabaseCredentials <PSCredential>] [-DoNotSaveConfiguration] [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Mount-NAVApplication cmdlet to mount a Microsoft Dynamics NAV database that contains the application tables against a Microsoft Dynamics NAV Server instance. You can only mount one Microsoft Dynamics NAV application at a time.

The database can be a dedicated application database, or a database that contains all Microsoft Dynamics NAV tables.

## EXAMPLES

### EXAMPLE 1
```
Mount-NAVApplication DynamicsNAV -DatabaseServer dbserver1 -DatabaseName 'NAV App'
```

This example mounts the Microsoft Dynamics NAV application on the DynamicsNAV server instance.
The application is contained in the NAV App database, which is hosted on the dbserver1 database server.

### EXAMPLE 2
```
Mount-NAVApplication DynamicsNAV -DatabaseServer dbserver1 -DatabaseName 'NAV App' -DatabaseCredentials (Get-Credential)
```

This example mounts the Microsoft Dynamics NAV application on the DynamicsNAV server instance and configures the Microsoft Dynamics NAV Server instance to use SQL authentication with the application database. The database credentials (user name and password) are provided in a dialog box that results from the call to the Get-Credential cmdlet.

## PARAMETERS

### -DatabaseCredentials
The user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to connect to the Microsoft Dynamics NAV database in SQL Server.
Setting parameter is configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the application database.
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

### -DatabaseInstance
Specifies the name of the SQL Server instance that hosts the database.
You can also specify the instance in the DatabaseServer parameter, such as like MyServer\MyInstance.

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
Specifies the name of the application database that you want to mount against the Microsoft Dynamics NAV Server instance, such as 'NAV App'.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the database server that hosts the application database that you want to mount against the Microsoft Dynamics NAV Server instance.

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

### -DoNotSaveConfiguration
Specifies if the configuration must not be saved when the cmdlet has completed the task.
If the parameter is not set, the configuration settings are automatically saved.

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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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
You can pipe the value of the ServerInstance parameter as a string to this cmdlet.

## OUTPUTS

### None

## NOTES
## RELATED LINKS

[Export-NAVApplication](Export-NAVApplication.md)  

[Get-NAVApplication](Get-NAVApplication.md)  

[Remove-NAVApplication](Remove-NAVApplication.md)  
