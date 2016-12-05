---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVServerInstance

## SYNOPSIS
Removes a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Remove-NAVServerInstance [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerInstance cmdlet to remove a Microsoft Dynamics NAV Server instance.
This cmdlet uninstalls an existing ServerInstance, including supporting directories, firewall exceptions, and supporting access control lists.
The service is unregistered.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVServerInstance myInstance -VERBOSE

VERBOSE: NavCommand.BeginProcessing

VERBOSE: NavCommand.ProcessRecord

VERBOSE: Performing operation "Remove-NAVServerInstance" on Target "ServerInstance = MicrosoftDynamicsNavServer$myInstance".

VERBOSE: Attempting to stop service MicrosoftDynamicsNavServer$myInstance

VERBOSE: Service MicrosoftDynamicsNavServer$myInstance is stopped

VERBOSE: Removing Windows Firewall Rule for ServerInstance MicrosoftDynamicsNavServer$myInstance

VERBOSE: Removing UrlAcl Rule for Server Instance MicrosoftDynamicsNavServer$myInstance

VERBOSE: Removing UrlAcl Rule for Server Instance MicrosoftDynamicsNavServer$myInstance

VERBOSE: Un-installing Server Instance MicrosoftDynamicsNavServer$myInstance 

VERBOSE: Removing Instance directory C:\Program Files\Microsoft Dynamics NAV\80\Service\Instances\myInstance

VERBOSE: NavCommand.EndProcessing
```

Description

-----------

This example removes the Microsoft Dynamics NAV Server instance myInstance.

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

