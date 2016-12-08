---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=521783
schema: 2.0.0
---

# Remove-NAVAddIn

## SYNOPSIS
Removes an add-in that is registered in the system table 2000000069 Add-ins of the Microsoft Dynamics NAV database.

## SYNTAX

```
Remove-NAVAddIn -AddInName <String> [-Version <String>] -PublicKeyToken <String> [-ServerInstance] <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Removes an add-in that is registered in the system table 2000000069 Add-ins of the Microsoft Dynamics NAV database.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVAddIn -ServerInstance DynamicsNAV -AddinName MyNavAddin -PublicKeyToken 31bf3856ad364e35
```

This example removes the MyNavAddin add-in from the system table 2000000069 Add-ins.

## PARAMETERS

### -AddInName
Specifies the name of the add-in that you want to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicKeyToken
Specifies a public token key of the add-in that you want to remove.
The public key token is a 16-character key that is given to the add-in assembly when it is built and signed in Microsoft Visual Studio.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Version
Specifies a version number for the add-in.
The version number must have the format N.N.N.N, such as 8.0.0.0.
Use this parameter when there is more than one version of the add-in and you want to remove a specific version.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES
## RELATED LINKS

[Get-NAVAddIn](Get-NAVAddIn.md)

[New-NAVAddIn](New-NAVAddIn.md)

[Set-NAVAddIn](Set-NAVAddIn.md)
