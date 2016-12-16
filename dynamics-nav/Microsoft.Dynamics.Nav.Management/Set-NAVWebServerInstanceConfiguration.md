---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401403
schema: 2.0.0
---

# Set-NAVWebServerInstanceConfiguration

## SYNOPSIS
Changes configuration values for a named web server instance.

## SYNTAX

```
Set-NAVWebServerInstanceConfiguration [-WebServerInstance] <String> -KeyName <String> -KeyValue <String>
 [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use this cmdlet to change configuration values for a named web server instance. These values are written directly to the configuration file. The changes will be applied to the web server automatically since the application pool detects the configuration change and performs a recycle. When the application pool is recycled by the IIS, static state such as client sessions in the Microsoft Dynamics NAV Web client will be lost.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVWebServerInstanceConfiguration -WebServerInstance DynamicsNAV -KeyName CompanyName -KeyValue "CRONUS International Ltd."
```

This example sets the web server instance configuration.

## PARAMETERS

### -WebServerInstance
Specifies the name of a Dynamics NAV web server instance for which to return the information.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -KeyName
Specifies the configuration key name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyValue
Specifies the configuration key value.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV web server instance name to the cmdlet.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NAVWebServerInstance](Get-NAVWebServerInstance.md)

[New-NAVWebServerInstance](New-NAVWebServerInstance.md)

[Remove-NAVWebServerInstance](Remove-NAVWebServerInstance.md)
