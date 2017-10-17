---
external help file: Microsoft.Dynamics.Nav.apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616082
schema: 2.0.0
---

# Repair-NAVApp

## SYNOPSIS
Repairs a NAV App by recompiling it against the current base application.
Use this cmdlet if the base application has changed since publishing the NAV App.
It is recommended that the NAV Server instance is restarted after running the repair.

## SYNTAX

### None (Default)
```
Repair-NAVApp [-Name] <String> [[-Publisher] <String>] [[-Version] <Version>] [-ServerInstance] <String>
 [<CommonParameters>]
```

### SandboxDB
```
Repair-NAVApp [-Name] <String> [[-Publisher] <String>] [[-Version] <Version>] -SandboxDatabaseName <String>
 [-SandboxDatabaseServer <String>] [-SandboxDatabaseCredentials <PSCredential>] [-SqlTimeout <UInt32>] [-Force]
 [-ServerInstance] <String> [<CommonParameters>]
```

## DESCRIPTION
Use the Repair-NAVApp cmdlet to recompile a NAV App that has been published in the app catalog of the specified Microsoft Dynamics NAV Server instance.

If you have deployed your NAV database to Azure SQL Database, you will need to create a new database to use as the sandbox for completing the publishing process. Use the SandboxDatabaseName, SandboxDatabaseServer, and SandboxDatabaseCredentials parameters to specify the connection information for the database to use as the sandbox.

## EXAMPLES

### EXAMPLE 1
```
Repair-NAVApp -ServerInstance DynamicsNAV110 -Name 'Proseware SmartApp' -Version 2.3.4.500
```

This example repairs the NAV App with a name of Proseware SmartApp and version of 2.3.4.500.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110 | Repair-NAVApp
```

This example repairs all of the NAV Apps in the DynamicsNAV110 server instance's app catalog.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation about the data in the provided sandbox database being overwritten.

```yaml
Type: SwitchParameter
Parameter Sets: SandboxDB
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the NAV App to be repaired.

The search must return only a single NAV App to successfully repair.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 20
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App to be repaired.

The results must return only a single NAV App to successfully repair.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 21
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SandboxDatabaseCredentials
Specifies the user name and password of a SQL Server Authentication login account that provides access to the sandbox database in SQL Server. You use this parameter to access the database by using SQL Server Authentication.

If you want to use Windows Authentication, then you can omit this parameter.

The login account must be a member of the db_owner role on the database.

For sandboxes hosted on Azure SQL, the user name must follow the pattern \<username\>@\<azureserverid\>, e.g. navadmin@z8bdostg9d.

```yaml
Type: PSCredential
Parameter Sets: SandboxDB
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SandboxDatabaseName
The name of the Azure SQL Database that you want to use as a sandbox for completing the publishing process, such as 'DynamicsNAV_Sandbox'.
This must be used if publishing to a NAV Server instance that is deployed to Azure SQL Database.
The current content of the sandbox database will be overwritten.

```yaml
Type: String
Parameter Sets: SandboxDB
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SandboxDatabaseServer
Specifies the name of the computer on which the SQL Server instance for the sandbox database is installed.

```yaml
Type: String
Parameter Sets: SandboxDB
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance for which the NAV App should be repaired, such as DynamicsNAV.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SqlTimeout
The time (in seconds) to wait before terminating an attempt to execute a command on SQL Server, such as reading content or restoring the database from a .bak file.

```yaml
Type: UInt32
Parameter Sets: SandboxDB
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Version
Specifies the version of the NAV App to be repaired.

The results must return only a single NAV App to successfully repair.

```yaml
Type: Version
Parameter Sets: (All)
Aliases: 

Required: False
Position: 22
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NavAppTenant](Get-NavAppTenant.md)

[Install-NAVApp](Install-NAVApp.md)

[Publish-NAVApp](Publish-NAVApp.md)

[Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)

[Unpublish-NAVApp](Unpublish-NAVApp.md)
