---
external help file: Microsoft.Dynamics.Nav.apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=618058
schema: 2.0.0
---

# Get-NAVAppInfo

## SYNOPSIS
Gets information about an NAV App based on the specified package file or the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### Properties (Default)
```
Get-NAVAppInfo [-Id <Guid>] [-Name <String>] [-Publisher <String>] [-Version <Version>]
 [-CompatibilityId <Version>] [-ServerInstance] <String> [<CommonParameters>]
```

### Tenant
```
Get-NAVAppInfo -Tenant <String> [-ServerInstance] <String> [<CommonParameters>]
```

### Path
```
Get-NAVAppInfo -Path <String> [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVAppInfo cmdlet to get information about a specific NAV App, or to get a list of NAV Apps that have been deployed. The list of deployed NAV Apps can include all NAV Apps that have been published to a Microsoft Dynamics NAV Server instance, filtered by NAV App properties, or NAV Apps that are installed for a specific tenant.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110

                    Id                                       Name                 Version    Publisher
                    --                                       ----                 -------    ---------
                    9a47a833-e22f-4812-ade314219c53          SmartApp Base        2.0.0.300  Proseware, Inc.
                    3c88160c-e0eb-4fe1-b4f6-011e45d74b10     Proseware SmartApp   2.3.4.500  Proseware, Inc.
```

This example returns information about all of the NAV Apps published on the DynamicsNAV110 server instance.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110 -Name 'Proseware SmartApp' -Version 2.3.4.500

                    Id                 : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
                    Name               : Proseware SmartApp
                    Version            : 2.3.4.500
                    Publisher          : Proseware, Inc.
                    Brief              : First Proseware App
                    Description        : First NAV App by Proseware
                    Compatibility Id   : 2.0.0.0
                    Privacy Statement  : http://www.proseware.com/SmartApp/privacypolicy.aspx
                    EULA               : http://www.proseware.com/SmartApp/EULA.aspx
                    Help               : http://www.proseware.com/SmartApp/Support.aspx
                    Url                : http://www.proseware.com/SmartApp/
                    Logo               : SmartLogo.png
                    ScreenShots        : SmartShot1.png, SmartShot2.png, SmartShot3.png
                    Capabilities       :
                    Prerequisites      :
                    Dependencies       :
```

This example returns information about the NAV App with the specified name and version on the DynamicsNAV110 server instance.

### EXAMPLE 3
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110 -Publisher 'Proseware, Inc.'

                    Id                                       Name                 Version    Publisher
                    --                                       ----                 -------    ---------
                    9a47a833-e22f-4812-ade314219c53          SmartApp Base        2.0.0.300  Proseware, Inc.
                    3c88160c-e0eb-4fe1-b4f6-011e45d74b10     Proseware SmartApp   2.3.4.500  Proseware, Inc.
```

This example returns information about all of the NAV Apps published on the DynamicsNAV110 server instance that are published by Proseware, Inc.

### EXAMPLE 4
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110 -Tenant 'Tenant1'

                    Id                 : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
                    Name               : Proseware SmartApp
                    Version            : 2.3.4.500
                    Publisher          : Proseware, Inc.
                    Brief              : First Proseware App
                    Description        : First NAV App by Proseware
                    Compatibility Id   : 2.0.0.0
                    Privacy Statement  : http://www.proseware.com/SmartApp/privacypolicy.aspx
                    EULA               : http://www.proseware.com/SmartApp/EULA.aspx
                    Help               : http://www.proseware.com/SmartApp/Support.aspx
                    Url                : http://www.proseware.com/SmartApp/
                    Logo               : SmartLogo.png
                    ScreenShots        : SmartShot1.png, SmartShot2.png, SmartShot3.png
                    Capabilities       :
                    Prerequisites      :
                    Dependencies       :
```

This example returns information about all of the NAV Apps installed for the tenant with an ID of Tenant1 on the DynamicsNAV110 server instance.

### EXAMPLE 5
```
Get-NAVAppInfo -Path '.\Proseware SmartApp.navx'

                    Id                 : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
                    Name               : Proseware SmartApp
                    Version            : 2.3.4.500
                    Publisher          : Proseware, Inc.
                    Brief              : First Proseware App
                    Description        : First NAV App by Proseware
                    Compatibility Id   : 2.0.0.0
                    Privacy Statement  : http://www.proseware.com/SmartApp/privacypolicy.aspx
                    EULA               : http://www.proseware.com/SmartApp/ULA.aspx
                    Help               : http://www.proseware.com/SmartApp/Support.aspx
                    Url                : http://www.proseware.com/SmartApp/
                    Logo               : SmartLogo.png
                    ScreenShots        : SmartShot1.png, SmartShot2.png, SmartShot3.png
                    Capabilities       :
                    Prerequisites      :
                    Dependencies       :
```

This example returns information about the NAV App from the package file provided.

### EXAMPLE 6
```
Get-NAVAppInfo -ServerInstance DynamicsNAV110 -Tenant default

                    Id                 : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
                    Name               : Proseware SmartApp
                    Version            : 2.3.4.500
                    Publisher          : Proseware, Inc.
                    Brief              : First Proseware App
                    Description        : First NAV App by Proseware
                    Compatibility Id   : 2.0.0.0
                    Privacy Statement  : http://www.proseware.com/SmartApp/privacypolicy.aspx
                    EULA               : http://www.proseware.com/SmartApp/ULA.aspx
                    Help               : http://www.proseware.com/SmartApp/Support.aspx
                    Url                : http://www.proseware.com/SmartApp/
                    Logo               : SmartLogo.png
                    ScreenShots        : SmartShot1.png, SmartShot2.png, SmartShot3.png
                    Capabilities       :
                    Prerequisites      :
                    Dependencies       :
```

This example returns information about all of the NAV Apps installed in a single tenant NAV server instance.

## PARAMETERS

### -CompatibilityId
Specifies the compatibility ID of the NAV App. The compatibility ID is a version string in the format of  Major.Minor.Build.Revision such as 1.0.0.0. The value is used to indicate if there are compatibility-related code changes between different versions of the NAV App.

```yaml
Type: Version
Parameter Sets: Properties
Aliases: AppCompatibilityId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the NAV App to be returned.

```yaml
Type: Guid
Parameter Sets: Properties
Aliases: AppId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the NAV App to be returned.

```yaml
Type: String
Parameter Sets: Properties
Aliases: AppName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to a NAV App Package file that you want to return.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App to be returned.

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
Specifies the Microsoft Dynamics NAV Server instance to which the NAV App is deployed, such as DynamicsNAV110.

```yaml
Type: String
Parameter Sets: Properties, Tenant
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that you want to get the installed NAV Apps for, such as Tenant1. Provide a value of 'default' if the specified server instance is not configured to run multiple tenants.

```yaml
Type: String
Parameter Sets: Tenant
Aliases: TenantId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Version
Specifies the version of the NAV App to be returned.

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

[Install-NAVApp](Install-NAVApp.md)

[Get-NavAppTenant](Get-NavAppTenant.md)

[Publish-NAVApp](Publish-NAVApp.md)

[Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)

[Unpublish-NAVApp](Unpublish-NAVApp.md)
