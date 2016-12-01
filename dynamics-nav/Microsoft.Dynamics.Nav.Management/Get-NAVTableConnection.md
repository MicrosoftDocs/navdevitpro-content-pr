---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVTableConnection

## SYNOPSIS
Gets a list of connections to external database tables from a Microsoft Dynamics NAV application.

## SYNTAX

### UseNST
```
Get-NAVTableConnection [-ServerInstance] <String> [-Force]
```

### UseNSTSpecificConnection
```
Get-NAVTableConnection [-ServerInstance] <String> -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-Force]
```

### UseDatabase
```
Get-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] [-Force]
```

### UseDatabaseSpecificConnection
```
Get-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-Force]
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

### -ConnectionType
Specifies the type of table connection. In the current version of Microsoft Dynamics NAV, you can specify two types of connection: CRM or ExternalSQL.

```yaml
Type: TableConnectionType
Parameter Sets: UseNSTSpecificConnection, UseDatabaseSpecificConnection
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
Parameter Sets: UseNST, UseNSTSpecificConnection
Aliases:

Required: True
Position: 1
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
## RELATED LINKs
[New-NAVTableConnection](New-NAVTableConnection.md)  

[Remove-NAVTableConnection](Remove-NAVTableConnection.md)  
