---
external help file: Microsoft.Dynamics.Nav.Apps.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=827845
schema: 2.0.0
---

# Get-NAVAppTableModification

## SYNOPSIS
Gets information about the tabled added or modified by an Extension based on the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

### Properties (Default)
```
Get-NAVAppTableModification [-Id <Guid>] [-Name <String>] [-Publisher <String>] [-Version <Version>]
 [-CompatibilityId <Version>] [-ServerInstance] <String>
```

### Tenant
```
Get-NAVAppTableModification -Tenant <String> [-ServerInstance] <String>
```

## DESCRIPTION
Use the Get-NAVAppTableModifications cmdlet to get information about tables modified or added by  one or more Extension that have been deployed.

The list of deployed Extensions can include all Extensions that have been published to a Microsoft Dynamics NAV Server instance, filtered by Extension properties, or Extensions that are installed for a specific tenant.

## EXAMPLES

### EXAMPLE 1
```
Get-NavAppTableModifications -ServerInstance DynamicsNAV91

          Id             : 9a47a833-e22f-4812-03f2-ade314219c53
          Name           : SmartApp Base
          Publisher      : Proseware, Inc.
          Version        : 2.0.0.300
          TablesModified : {3, 4}
          TablesAdded    : {42001}
          Dependencies   : {}

          Id             : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
          Name           : Proseware SmartApp
          Publisher      : Proseware, Inc.
          Version        : 2.3.4.500
          TablesModified : {3, 4}
          TablesAdded    : {42002}
          Dependencies   : {SmartApp Base}
```

This example returns table modifications from all of the Extensions published on the DynamicsNAV91 server instance.

### EXAMPLE 2
```
Get-NavAppTableModifications -ServerInstance DynamicsNAV91 -Name 'Proseware SmartApp' -Version 2.3.4.500

          Id             : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
          Name           : Proseware SmartApp
          Publisher      : Proseware, Inc.
          Version        : 2.3.4.500
          TablesModified : {3, 4}
          TablesAdded    : {42002}
          Dependencies   : {SmartApp Base}
```

This example returns table modifications from the Extension with the specified name and version on the DynamicsNAV91 server instance.

### EXAMPLE 3
```
Get-NavAppTableModifications -ServerInstance DynamicsNAV91 -Publisher 'Proseware, Inc.'

          Id             : 9a47a833-e22f-4812-03f2-ade314219c53
          Name           : SmartApp Base
          Publisher      : Proseware, Inc.
          Version        : 2.0.0.300
          TablesModified : {3, 4}
          TablesAdded    : {42001}
          Dependencies   : {}

          Id             : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
          Name           : Proseware SmartApp
          Publisher      : Proseware, Inc.
          Version        : 2.3.4.500
          TablesModified : {3, 4}
          TablesAdded    : {42002}
          Dependencies   : {SmartApp Base}
```

This example returns table modifications from the Extensions on the DynamicsNAV91 server instance that are published by Proseware, Inc.

### EXAMPLE 4
```
Get-NavAppTableModifications -ServerInstance DynamicsNAV91 -Tenant 'Tenant1'

          Id             : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
          Name           : Proseware SmartApp
          Publisher      : Proseware, Inc.
          Version        : 2.3.4.500
          TablesModified : {3, 4}
          TablesAdded    : {42002}
          Dependencies   : {SmartApp Base}
```

This example returns table modifications from the Extensions installed for Tenant1 on the DynamicsNAV91 server instance.

### EXAMPLE 5
```
Get-NavAppTableModifications -ServerInstance DynamicsNAV91 -Tenant default

          Id             : 3c88160c-e0eb-4fe1-b4f6-011e45d74b10
          Name           : Proseware SmartApp
          Publisher      : Proseware, Inc.
          Version        : 2.3.4.500
          TablesModified : {3, 4}
          TablesAdded    : {42002}
          Dependencies   : {SmartApp Base}
```

This example returns table modifications from the Extensions installed in a single tenant NAV server instance.

## PARAMETERS

### -CompatibilityId
Specifies the compatibility ID of the Extension. The compatibility ID is a version string in the format of  Major.Minor.Build.Revision such as 1.0.0.0. The value is used to indicate if there are compatibility-related code changes between different versions of the Extension.

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
Specifies the ID of the Extension whose table modifications are to be returned.

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
Specifies the name of the Extension whose table modifications are to be returned.

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

### -Publisher
Specifies the publisher of the Extension whose table modifications are to be returned.

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
Specifies the Microsoft Dynamics NAV Server instance to which the Extension is deployed, such as DynamicsNAV91.

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
Specifies the ID of the tenant whose installed Extensions you want to get table modifications for, such as Tenant1. Provide a value of 'default' if the specified server instance is not configured to run multiple tenants.

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
Specifies the version of the Extension whose table modifications are to be returned.

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

[Publish-NAVApp](Publish-NAVApp.md)  

[Get-NAVTableSynchSetupForDataUpgrade](Get-NAVTableSynchSetupForDataUpgrade.md)  
