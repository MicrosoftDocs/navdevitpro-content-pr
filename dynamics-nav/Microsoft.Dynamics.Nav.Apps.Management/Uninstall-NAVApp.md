---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Uninstall-NAVApp

## SYNOPSIS
Uninstall a NAV App for a tenant.

## SYNTAX

### Properties (Default)
```
Uninstall-NAVApp [-ServerInstance] <String> -Name <String> [-Publisher <String>] [-Version <Version>]
 [-Tenant <TenantId>] [-PassThru] [-DoNotSaveData] [-Force]
```

### Path
```
Uninstall-NAVApp [-ServerInstance] <String> [-Tenant <TenantId>] -Path <String> [-PassThru] [-DoNotSaveData]
 [-Force]
```

## DESCRIPTION
Use the Uninstall-NAVApp cmdlet to uninstall a NAV App for one or more tenants.

## EXAMPLES

### EXAMPLE 1
```
Uninstall-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 -Tenant 'Tenant1'
```

This example uninstalls the NAV App with the provided name and version for the tenant with the ID Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 | Uninstall-NAVApp -Tenant 'Tenant1'
```
This example uninstalls the NAV App returned from the Get-NAVAppInfo cmdlet for the tenant with the ID Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized.

### EXAMPLE 3
```
Uninstall-NAVApp -ServerInstance DynamicsNAV -Path '.\Proseware SmartApp.navx' -Tenant 'Tenant1'
```

This example uninstalls the NAV App at the provided path for the tenant with the ID Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized.

### EXAMPLE 4
```
Get-NAVAppInfo -ServerInstance DynamicsNAV -Tenant 'Tenant1' | Uninstall-NAVApp -Tenant 'Tenant1'
```

This example uninstalls all of the NAV Apps that have been installed for the tenant with the ID Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized.

### EXAMPLE 5
```
Uninstall-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 -Tenant 'Tenant1' -DoNotSaveData
```

This example uninstalls the NAV App with the provided name and version for the tenant with the ID Tenant1.
If the NAV App contains a schema change, the tenant database will be synchronized but since the DoNotSaveData switch was used any data in the NAV App fields being removed will not be saved.

### EXAMPLE 6
```
Uninstall-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500
```

This example uninstalls the NAV App with the provided name and version for a non-multitenant Dynamics NAV server instance.
If the NAV App contains a schema change, the tenant database will be synchronized.

## PARAMETERS

### -DoNotSaveData
Specifies that the install should be executed without saving the NAV App data for a future install/upgrade of the NAV App.

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
Forces the command to run without asking for user confirmation to uninstall NAV Apps with a dependency on the NAV App being uninstalled.

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

### -Name
Specifies the name of the NAV App to be uninstalled.

The results must return only a single NAV App to successfully uninstall.

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
Returns a NAV App object for the uninstalled NAV App.
The NAV App object contains the properties of the NAV App, such as name, publisher, version.

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
Specifies the path to a NAV App Package file that you want to uninstall for the tenant.
The NAV App must have already been published to the server instance before uninstalling it for the tenant.

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
Specifies the publisher of the NAV App to be uninstalled.

The results must return only a single NAV App to successfully uninstall.

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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that you want to uninstall the NAV App for, such as Tenant1.

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
Specifies the version of the NAV App to be uninstalled.

The results must return only a single NAV App to successfully uninstall.

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS
[Get-NavAppTenant](Get-NavAppTenant.md)

[Install-NAVApp](Install-NAVApp.md)  

[Publish-NAVApp](Publish-NAVApp.md)  

[Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)  

[Repair-NAVApp](Repair-NAVApp.md)  

[Unpublish-NAVApp](Unpublish-NAVApp.md)  
