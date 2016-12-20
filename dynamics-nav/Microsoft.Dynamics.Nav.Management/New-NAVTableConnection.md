---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=623193
schema: 2.0.0
---

# New-NAVTableConnection

## SYNOPSIS
Registers a connection to an external database table so the table can be used by the Microsoft Dynamics NAV application.

## SYNTAX

### UseNST
```
New-NAVTableConnection [-ServerInstance] <String> -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ConnectionTimeout <Int32>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UseDatabase
```
New-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ConnectionTimeout <Int32>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the New-NAVTableConnection cmdlet to create a new set of connection settings for the application/service.

The connection settings are stored along with the application and can be used by all Microsoft Dynamics NAV Server instances that are connected to the specified application.

Code in your application can then use tables at the specified destination. You can connect to a Microsoft Dynamics NAV database by specifying the Microsoft Dynamics NAV Server instance or the application database.

## EXAMPLES

### EXAMPLE 1
```
New-NAVTableConnection -ServerInstance DynamicsNAV ConnectionType CRM -ConnectionId myCRM
```

This example creates a connection to a Dynamics CRM table.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: UseNST
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database that contains the application tables is installed in the multitenant deployment.

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

### -ApplicationDatabaseName
Specifies the name of the Microsoft Dynamics NAV database that contains the application tables in a multitenant deployment.

```yaml
Type: String
Parameter Sets: UseDatabase
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseCredentials
Specifies the user name and password of an SQL Server Authentication login account that provides access to the Microsoft Dynamics NAV application database in SQL Server.
You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter
The login account must be a member of the db_owner role on the database.

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

### -ConnectionType
Specifies the type of table connection.
In the current Microsoft Dynamics NAV version, you can specify two types of connection: CRM or ExternalSQL.

```yaml
Type: TableConnectionType
Parameter Sets: (All)
Aliases: 
Accepted values: CRM, ExternalSQL, Exchange, MicrosoftGraph

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionId
Specifies the name of the table connection.

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
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database is installed.

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
Specifies the name of the Microsoft Dynamics NAV database, such as 'Demo Database NAV ', that you want to establish the table connection to.

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
Specifies the user name and password for an SQL Server Authentication login account that provides access to the database or, in a multitenant deployment, the tenant database in SQL Server.
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

### -ConnectionTimeout
{{Fill ConnectionTimeout Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NAVTableConnection](Get-NAVTableConnection.md)

[Remove-NAVTableConnection](Remove-NAVTableConnection.md)
