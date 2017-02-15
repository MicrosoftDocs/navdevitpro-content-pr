---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401356
schema: 2.0.0
---

# Export-NAVServerLicenseInformation

## SYNOPSIS
Exports license information from the Microsoft Dynamics NAV database.

## SYNTAX

```
Export-NAVServerLicenseInformation [-Tenant <TenantId>] [-ServerInstance] <String> [-Force]
 [<CommonParameters>]
```

## DESCRIPTION
Use the Export-NAVServerLicenseInformation cmdlet to export license information from the Microsoft Dynamics NAV database.

If theMicrosoft Dynamics NAV Server account does not have access to the location where the global license file is stored, an error results. Check the Windows Event Log on the Microsoft Dynamics NAV Server computer to see what permissions are required.

## EXAMPLES

### EXAMPLE 1
```
Export-NAVServerLicenseInformation MyInstance

*************************
  THE LICENSE FILE INFO
*************************
```

This example exports license info to the console window.

## PARAMETERS

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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### System.String
Returns license information as well-formatted text.

## NOTES

## RELATED LINKS

[Import-NAVServerLicense](Import-NAVServerLicense.md)
