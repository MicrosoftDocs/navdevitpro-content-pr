---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=723208
schema: 2.0.0
---

# Get-NAVTableConnection

## SYNOPSIS
Gets a list of connections to external database tables from a Microsoft Dynamics NAV application.

## SYNTAX

### UseNST
```
Get-NAVTableConnection [-ServerInstance] <String> [-Force] [<CommonParameters>]
```

### UseNSTSpecificConnection
```
Get-NAVTableConnection [-ServerInstance] <String> -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-Force] [<CommonParameters>]
```

### UseDatabase
```
Get-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] [-Force] [<CommonParameters>]
```

### UseDatabaseSpecificConnection
```
Get-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVTableConnection cmdlet to get a list of table connections from the specified Microsoft Dynamics NAV application.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVTableConnection -ServerInstance DynamicsNAV
```

This example returns a list of all connections to external database tables.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: UseNST, UseNSTSpecificConnection
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
Parameter Sets: UseDatabase, UseDatabaseSpecificConnection
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
Parameter Sets: UseDatabase, UseDatabaseSpecificConnection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance uses to access the application database in SQL Server when using SQL Server Authentication.

This parameter is only relevant when you set with the ApplicationDatabaseServer and ApplicationDatabaseName parameters

```yaml
Type: PSCredential
Parameter Sets: UseDatabase, UseDatabaseSpecificConnection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConnectionType
Specifies the type of table connection. In the current version of Microsoft Dynamics NAV, you can specify two types of connection: CRM or ExternalSQL.

```yaml
Type: TableConnectionType
Parameter Sets: UseNSTSpecificConnection, UseDatabaseSpecificConnection
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
Parameter Sets: UseNSTSpecificConnection, UseDatabaseSpecificConnection
Aliases: 

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-NAVTableConnection](New-NAVTableConnection.md)

[Remove-NAVTableConnection](Remove-NAVTableConnection.md)
