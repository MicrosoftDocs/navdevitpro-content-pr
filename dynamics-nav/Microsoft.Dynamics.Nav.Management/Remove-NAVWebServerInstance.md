---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVWebServerInstance

## SYNOPSIS
Removes an existing Microsoft Dynamics NAV Web Server instance.

## SYNTAX

```
Remove-NAVWebServerInstance [-WebServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
The Remove-NAVWebServerInstance cmdlet deletes all virtual folders, web applications, and physical folders on IIS for a Microsoft Dynamics NAV Web Server instance that was created by the New-NAVWebServerInstance cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Remove-NAVWebServerInstance -WebServerInstance MyNavApp
```

Description

-----------

This example removes the Microsoft Dynamics NAV Server instance that is named MyNavApp.

## PARAMETERS

### -WebServerInstance
Specifies the name of the Microsoft Dynamics NAV Web Server instance to delete.
This is the name that is used by the web application on IIS and is specified as the virtual directory alias for the Microsoft Dynamics NAV Web Server instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

