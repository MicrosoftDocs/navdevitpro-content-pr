---
external help file: Microsoft.Dynamics.Nav.apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=618056
schema: 2.0.0
---

# Install-NAVApp

## SYNOPSIS
Installs a published NAV App for a tenant.

## SYNTAX

### Properties (Default)
```
Install-NAVApp [-ServerInstance] <String> -Name <String> [-Publisher <String>] [-Version <Version>]
 [-Tenant <TenantId>] [-Language <LanguageSetting>] [-PassThru] [-DoNotLoadData] [-Force] [<CommonParameters>]
```

### Path
```
Install-NAVApp [-ServerInstance] <String> [-Tenant <TenantId>] -Path <String> [-Language <LanguageSetting>]
 [-PassThru] [-DoNotLoadData] [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Install-NAVApp cmdlet to install an already published NAV App for a tenant.

## EXAMPLES

### EXAMPLE 1
```
Install-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 -Tenant 'Tenant1'
```

This example installs the NAV App with the specified name and version for the tenant with the ID Tenant1. If the NAV App includes a database schema change, the tenant database is automatically synchronized.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 | Install-NAVApp -Tenant 'Tenant1'
```

Description

-----------

This example installs a NAV App that is returned from the Get-NAVAppInfo cmdlet for the tenant with the ID Tenant1. If the NAV App contains a database schema change, the tenant database is automatically synchronized.

### EXAMPLE 3
```
Install-NAVApp -ServerInstance DynamicsNAV -Path '.\Proseware SmartApp.navx' -Tenant 'Tenant1'
```

This example installs the NAV App at the specified path for the tenant with the ID Tenant1.
The NAV App must have already been published to the server instance before you can install it for the tenant. If the NAV App contains a database schema change, the tenant database is automatically synchronized.

### EXAMPLE 4
```
Install-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 -Tenant 'Tenant1' -DoNotLoadData
```

This example installs the NAV App with the provided name and version for the tenant with an ID of Tenant1. If the NAV App contains a schema change, the tenant database will be synchronized but since the -DoNotLoadData switch was used any data backed up from a previous uninstall of this NAV App will not be loaded.

### EXAMPLE 5
```
Install-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500
```

This example installs the NAV App with the provided name and version on a single tenant NAV server instance. If the NAV App contains a schema change, the tenant database will be synchronized.

### EXAMPLE 6
```
Get-NAVTenant -ServerInstance DynamicsNAV | Install-NAVApp -ServerInstance DynamicsNAV110 -Name 'Proseware SmartApp' -Version 2.3.4.500
```

This example installs the NAV App with the provided name and version to all tenants of the DynamicsNAV NAV server instance.

## PARAMETERS

### -DoNotLoadData
Specifies that the installation must run without loading any NAV App data that was saved from an earlier installation of the NAV App.

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
Forces the command to run without asking for user confirmation to install a dependent NAV App.

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

### -Language
Specifies the language version of Dynamics NAV app. The value must be a valid culture name for a language in Microsoft Dynamics NAV, such as en-US or da-DK. If the specified language does not exist on the Microsoft Dynamics NAV Server instance, then en-US is used.

```yaml
Type: LanguageSetting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the NAV App that you want to install. The results must return only one NAV App, otherwise nothing installs.

```yaml
Type: String
Parameter Sets: Properties
Aliases: AppName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns a NAV App object for the installed NAV App. The NAV App object contains the properties of the NAV App, such as name, publisher, and version.

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

### -Path
Specifies the path to a NAV App package file that you want to install for the tenant. The NAV App must have already been published to the server instance before you can install it for the tenant.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App that you want to install. The results must return only one NAV App, otherwise nothing installs.

```yaml
Type: String
Parameter Sets: Properties
Aliases: AppPublisher

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance that the NAV App is published to, such as DynamicsNAV.

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

### -Tenant
Specifies the ID of the tenant that you want to install the NAV App for, such as Tenant1. You can specify the value default if the specified server instance is not configured for multiple tenants. Alternatively, do not set the parameter.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the NAV App that you want to install. The results must return only one NAV App, otherwise nothing installed.

```yaml
Type: Version
Parameter Sets: Properties
Aliases: AppVersion

Required: False
Position: Named
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

[Publish-NAVApp](Publish-NAVApp.md)

[Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)

[Repair-NAVApp](Repair-NAVApp.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)

[Unpublish-NAVApp](Unpublish-NAVApp.md)
