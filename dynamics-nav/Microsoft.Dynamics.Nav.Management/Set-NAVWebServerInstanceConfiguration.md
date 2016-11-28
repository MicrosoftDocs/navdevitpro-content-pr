---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-NAVWebServerInstanceConfiguration

## SYNOPSIS
Changes configuration values for a named web server instance.

## SYNTAX

```
Set-NAVWebServerInstanceConfiguration [-WebServerInstance] <String> -KeyName <String> -KeyValue <String>
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use this cmdlet to change configuration values for a named web server instance.
These values are written directly to the configuration file.
The changes will be applied to the web server automatically since the application pool detects the configuration change and performs a recycle.
When the application pool is recycled by the IIS, static state such as client sessions in the Microsoft Dynamics NAV Web client will be lost.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Set-NAVWebServerInstanceConfiguration -WebServerInstance DynamicsNAV -KeyName CompanyName -KeyValue "CRONUS International Ltd."
```

Description

-----------

This example sets the web server instance configuration.

## PARAMETERS

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

### -WebServerInstance
Specifies the name of a Dynamics NAV web server instance for which to return the information.

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

### None

## NOTES
## RELATED LINKS

