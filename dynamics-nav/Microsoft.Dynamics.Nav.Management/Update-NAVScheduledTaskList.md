---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=730509
schema: 2.0.0
---

# Update-NAVScheduledTaskList

## SYNOPSIS
Updates the application-wide list of scheduled tasks with the information from the tenant database.

## SYNTAX

### UseNST
```
Update-NAVScheduledTaskList [-ServerInstance] <String> [-Tenant] <TenantId> [-Force]
```

### UseDatabase
```
Update-NAVScheduledTaskList -ApplicationDatabaseServer <String> -ApplicationDatabaseName <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -DatabaseServer <String> [-DatabaseName <String>]
 [-DatabaseCredentials <PSCredential>] [-Force]
```

## DESCRIPTION

## EXAMPLES

### Example 1
```
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ApplicationDatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance uses to access the application database in SQL Server when using SQL Server Authentication.
This parameter is only relevant when you set with the ApplicationDatabaseServer and ApplicationDatabaseName parameters

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
Specifies the name of the database that is used by the tenant database.
This parameter is only relevant if the Microsoft Dynamics NAV Server instance is configured for multitenancy.
This parameter, together with the ApplicationDatabaseServer parameter, enables you to update the application-wide list of scheduled tasks on a Microsoft Dynamics NAV Server instance without having a running connection to the Microsoft Dynamics NAV Server instance.

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
Even if you are not importing application data to the application database, you must specify this parameter in a multitenant deployment.

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

### -DatabaseCredentials
Specifies the user name and password of the login account that the Microsoft Dynamics NAV Server instance will use to access the tenant database in SQL Server.
This parameter configures the Microsoft Dynamics NAV Server instance to use SQL Server Authentication instead of Windows Authentication on the connection to the database.
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

### -DatabaseName
Specifies the name of the tenant database that you want to update the application-wide list of scheduled task with.

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

### -DatabaseServer
Specifies the name of the database server that hosts the tenant database that you want to update the global list scheduled tasks with.

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
Specifies the ID of the tenant that you want to update the application-wide list of scheduled task with, such as Tenant1.
A scheduled task in the tenant will be added to the application-wide list of scheduled tasks if it doesn't exist.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: UseNST
Aliases: Id

Required: True
Position: 2
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
