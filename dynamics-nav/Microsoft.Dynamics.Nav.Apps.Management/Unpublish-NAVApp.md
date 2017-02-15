---
external help file: Microsoft.Dynamics.Nav.apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=616080
schema: 2.0.0
---

# Unpublish-NAVApp

## SYNOPSIS
Unpublishes a NAV App from the app catalog of the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### Properties (Default)
```
Unpublish-NAVApp [-Name] <String> [[-Publisher] <String>] [[-Version] <Version>] [-ServerInstance] <String>
 [<CommonParameters>]
```

### Path
```
Unpublish-NAVApp [-Path] <String> [-ServerInstance] <String> [<CommonParameters>]
```

## DESCRIPTION
Use the Unpublish-NAVApp cmdlet to remove a NAV App from the app catalog of the specified Microsoft Dynamics NAV Server instance.
The NAV App cannot be unpublished if it is currently installed for a tenant of the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Unpublish-NAVApp -ServerInstance DynamicsNAV -Name 'Proseware SmartApp'
```

This example removes the NAV App with the specified name from the DynamicsNAV server instance's app catalog.

### EXAMPLE 2
```
Get-NAVAppInfo -ServerInstance DynamicsNAV -Name 'Proseware SmartApp' -Version 2.3.4.500 | Unpublish-NAVApp
```

This example removes the NAV App returned from the Get-NAVAppInfo cmdlet from the DynamicsNAV server instance's app catalog.

### EXAMPLE 3
```
Unpublish-NAVApp -ServerInstance DynamicsNAV -Path '.\Proseware SmartApp.navx'
```

This example removes the NAV App at the provided path from the DynamicsNAV server instance's app catalog.

## PARAMETERS

### -Name
Specifies the name of the NAV App to be unpublished.

The results must return only a single NAV App to successfully unpublished.

```yaml
Type: String
Parameter Sets: Properties
Aliases: 

Required: True
Position: 20
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to a NAV App Package file that you want to unpublish.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: 20
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Specifies the publisher of the NAV App to be unpublished.

The results must return only a single NAV App to successfully unpublish.

```yaml
Type: String
Parameter Sets: Properties
Aliases: 

Required: False
Position: 21
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance that the NAV App will be unpublished from, such as DynamicsNAV90.

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

### -Version
Specifies the version of the NAV App to be unpublished.

The results must return only a single NAV App to successfully unpublish.

```yaml
Type: Version
Parameter Sets: Properties
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

[Repair-NAVApp](Repair-NAVApp.md)

[Uninstall-NAVApp](Uninstall-NAVApp.md)
