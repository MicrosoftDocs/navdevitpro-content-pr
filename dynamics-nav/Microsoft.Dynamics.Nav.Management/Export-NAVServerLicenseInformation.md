---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Export-NAVServerLicenseInformation

## SYNOPSIS
Exports license information from the Microsoft Dynamics NAV database.

## SYNTAX

```
Export-NAVServerLicenseInformation [-Tenant <TenantId>] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Export-NAVServerLicenseInformation cmdlet to export license information from the Microsoft Dynamics NAV database.
If theMicrosoft Dynamics NAV Server account does not have access to the location where the global license file is stored, an error results.
Check the Windows Event Log on the Microsoft Dynamics NAV Server computer to see what permissions are required.

## EXAMPLES

### EXAMPLE 1
```
Export-NAVServerLicenseInformation MyInstance

*************************
  THE LICENSE FILE INFO
*************************
```

Description

-----------

This example exports license info to the console window.

## PARAMETERS

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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
Specifies the ID of the tenant that the license is stored in, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

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

### System.String

## NOTES
## RELATED LINKS

