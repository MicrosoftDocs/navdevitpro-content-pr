---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVTableConnection

## SYNOPSIS
Removes a connection to an external database table from the Microsoft Dynamics NAV application.

## SYNTAX

### UseNST
```
Remove-NAVTableConnection [-ServerInstance] <String> -ConnectionType <TableConnectionType>
 -ConnectionId <String> [-Force] [-WhatIf] [-Confirm]
```

### UseDatabase
```
Remove-NAVTableConnection [-ApplicationDatabaseServer <String>] -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -ConnectionType <TableConnectionType> -ConnectionId <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVTableConnection cmdlet to remove an external table connection from the application/service.
You can connect to a Microsoft Dynamics NAV database by specifying the Microsoft Dynamics NAV Server instance or the application database.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```

```

Description

-----------

## PARAMETERS

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

### -ConnectionType
Specifies the type of table connection.
In Microsoft Dynamics NAV 2016, you can specify two types of connection: CRM or ExternalSQL.

```yaml
Type: TableConnectionType
Parameter Sets: (All)
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

## NOTES
## RELATED LINKS

