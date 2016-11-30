---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-NAVServerInstance

## SYNOPSIS
Changes the service state of a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Set-NAVServerInstance [-Stop] [-Start] [-Restart] [-ServiceAccount <ServiceAccount>]
 [-ServiceAccountCredential <PSCredential>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Set-NAVServerInstance cmdlet to change the service state of a Microsoft Dynamics NAV Server instance.
For example, you can change the service state from Stopped to Running.
You can also use this cmdlet to change the service account for a server instance.

## EXAMPLES

### EXAMPLE 1
```
Set-NAVServerInstance MyInstance -Restart -Verbose

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Performing operation "Set-NAVServerInstance" on Target "ServerInstance = MicrosoftDynamicsNavServer$MyInstance, Start = False, Stop = False, Restart = True".
VERBOSE: Attempting to stop service MyInstance
VERBOSE: Service MicrosoftDynamicsNavServer$MyInstance is stopped
VERBOSE: Service HTTP is already running
VERBOSE: Attempting to start service MicrosoftDynamicsNavServer$NewInstance
VERBOSE: Service MicrosoftDynamicsNavServer$NewInstance is running
VERBOSE: NavCommand.EndProcessing
```

Description

-----------

This example uses the Set-NAVServerInstance cmdlet to restart a Microsoft Dynamics NAV Server instance.
The Verbose parameter specifies that progress information is to be written to the console.

## PARAMETERS

### -Restart
Restarts the Microsoft Dynamics NAV Server instance.

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

### -ServiceAccount
Specifies the Windows-based computer account that the Microsoft Dynamics NAV Server instance is to use to log on.
Only NetworkService and Windows User values are supported.

```yaml
Type: ServiceAccount
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceAccountCredential
Specifies a set of security credentials that must be used when configuring the service account.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Start
Starts the Microsoft Dynamics NAV Server instance.

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

### -Stop
Stops the Microsoft Dynamics NAV Server instance.

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

