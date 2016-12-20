---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=723207
schema: 2.0.0
---

# Remove-NAVConfigurationPackageFile

## SYNOPSIS
Removes a configuration package file from the Microsoft Dynamics NAV app database.

## SYNTAX

```
Remove-NAVConfigurationPackageFile [-Code] <String> [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Removes a configuration package file from the Microsoft Dynamics NAV app database.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVConfigurationPackageFile -Code GB.ENU.TRIAL -ServerInstance DynamicsNAV
```

If a package with code GB.ENU.TRIAL is present in the application database of the DynamicsNAV90 instance, it will be removed.

## PARAMETERS

### -Code
Specifies the code of the configuration package file, uniquely identifying it.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

[Import-NavConfigurationPackageFile](Import-NavConfigurationPackageFile.md)
