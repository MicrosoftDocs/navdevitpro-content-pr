---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=517208
schema: 2.0.0
---

# Remove-NAVWebServerInstance

## SYNOPSIS
Removes an existing Microsoft Dynamics NAV Web Server instance.

## SYNTAX

```
Remove-NAVWebServerInstance [-WebServerInstance] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Remove-NAVWebServerInstance cmdlet deletes all virtual folders, web applications, and physical folders on IIS for a Microsoft Dynamics NAV Web Server instance that was created by the New-NAVWebServerInstance cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVWebServerInstance -WebServerInstance MyNavApp
```

This example removes the Microsoft Dynamics NAV Server instance that is named MyNavApp.

## PARAMETERS

### -WebServerInstance
Specifies the name of the Microsoft Dynamics NAV Web Server instance to delete. This is the name that is used by the web application on IIS and is specified as the virtual directory alias for the Microsoft Dynamics NAV Web Server instance.

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
You can pipe a string that contains a Microsoft Dynamics NAV Web Server instance name to the cmdlet.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NAVWebServerInstance](Get-NAVWebServerInstance.md)

[New-NAVWebServerInstance](New-NAVWebServerInstance.md)

[Set-NAVWebServerInstanceConfiguration](Set-NAVWebServerInstanceConfiguration.md)
