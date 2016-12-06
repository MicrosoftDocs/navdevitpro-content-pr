---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616079
schema: 2.0.0
---

# Publish-NAVApp

## SYNOPSIS
Publishes an Extension to the app catalog of the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### None (Default)
```
Publish-NAVApp [-Path] <String> [-PassThru] [[-LogPath] <String>] [-SkipVerification] [[-PackageType] <String>]
 [-ServerInstance] <String> [-WhatIf] [-Confirm]
```

### SandboxDB
```
Publish-NAVApp [-Path] <String> [-PassThru] [[-LogPath] <String>] [-SkipVerification] [[-PackageType] <String>]
 -SandboxDatabaseName <String> [-SandboxDatabaseServer <String>] [-SandboxDatabaseCredentials <PSCredential>]
 [-SqlTimeout <UInt32>] [-Force] [-ServerInstance] <String> [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Publish-NAVApp cmdlet to publish an Extension from a package file (.navx) to the app catalog of the specified Microsoft Dynamics NAV Server instance.
Once published, you can install the Extension for individual tenants.

If you have deployed your NAV database to Azure SQL Database, you will need to create a new database to use as the sandbox for completing the publishing process. Use the SandboxDatabaseName, SandboxDatabaseServer, and SandboxDatabaseCredentials parameters to specify the connection information for the database to use as the sandbox.

## EXAMPLES

### EXAMPLE 1
```
Publish-NAVApp -ServerInstance DynamicsNAV91 -Path '.\Proseware SmartApp.navx'
```

This example publishes the Extension from the Proseware SmartApp.navx package to the DynamicsNAV91 server instance.

### EXAMPLE 2
```
Publish-NAVApp -ServerInstance DynamicsNAV91 -Path '.\Proseware SmartApp.navx' -PassThru

          Name                  Publisher              Version                   ServerInstance
          ----                  ---------              -------                   --------------
          Proseware SmartApp    Proseware, Inc.        2.3.4.500                 DynamicsNAV90
```

This example publishes the Extension from the Proseware SmartApp.navx package to the DynamicsNAV91 server instance and then returns an Extension object.

### EXAMPLE 3
```
Publish-NAVApp -ServerInstance DynamicsNAV91 -Path '.\Proseware SmartApp.navx' -LogPath c:\temp\myerror.log
```

Description

-----------

This example will attempt to publish the Extension from the Proseware SmartApp.navx package to the DynamicsNAV91 server instance.
The -LogPath will specify the path to a file where errors will be written.
If the file exists then errors will be appended.

### EXAMPLE 4
```
Publish-NAVApp -ServerInstance DynamicsNAV91 -Path '.\Proseware SmartApp.navx' -SandboxDatabaseName DynamicsNAV90_Sandbox -SandboxDatabaseServer NAV_SQLServer -SandboxDatabaseCredentials (Get-Credential)
```

This example publishes the Extension from the Proseware SmartApp.navx package to the DynamicsNAV91 server instance by using the DynamicsNAV90_Sandbox database on the NAV_SQLServer in Azure as a sandbox.
All data within the DynamicsNAV91_Sandbox database will be overwritten.

### EXAMPLE 5
```
Publish-NAVApp -ServerInstance DynamicsNAV91 -Path '.\Proseware SmartApp.navm' -PackageType SymbolsOnly
```

This example publishes the Symbols package from the Proseware SmartApp.navm package to the DynamicsNAV91 server instance.

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

### -LogPath
Specifies the path where you want to save the log file for any potential publication errors.
If the file exists, any errors are added to the log file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 41
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PackageType
Specifies the Extension Package type that you want to publish  to the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 246944
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an Extension object for the published Extension.
The Extension object contains the properties of the Extension, such as name, publisher, version.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 22
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path to the Extension Package file that you want to publish to the Microsoft Dynamics NAV Server instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 21
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SandboxDatabaseCredentials
Specifies the user name and password of a SQL Server Authentication login account that provides access to the sandbox database in SQL Server.

You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter.

The login account must be a member of the db_owner role on the database.

If the sandbox database is an Azure SQL Database, the user name must follow the pattern \<username\>@\<azureserverid\>, e.g. navadmin@z8bdostg9d.

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
The name of an existing SQL database that you want to use as a sandbox for completing the publishing process, such as 'DynamicsNAV91_Sandbox'.
A database will automatically be created on the same SQL Server as the NAV application database if not provided.
If your NAV application database is deployed as an Azure SQL Database, then you must provide an existing database since the cmdlet isn't able to automatically create a new sandbox database.
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
Specifies the Microsoft Dynamics NAV server instance that the Extension will be published to, such as DynamicsNAV91.

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

### -SkipVerification
Forces the command to run without verifying the authenticode signature.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 246943
Default value: None
Accept pipeline input: False
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

[Get-NavAppTenant](Get-NavAppTenant.md)

[Install-NAVApp](Install-NAVApp.md)

[Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)

[Repair-NAVApp](Repair-NAVApp.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)

[Unpublish-NAVApp](Unpublish-NAVApp.md)
