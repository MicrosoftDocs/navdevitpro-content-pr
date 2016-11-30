---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Remove-NAVServerSession

## SYNOPSIS
Closes the specified client connection to a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Remove-NAVServerSession [-Tenant <TenantId>] -SessionId <Int32> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerSession cmdlet to close a client connection, as identified by the SessionId parameter.
You can use the Get-NAVServerSession cmdlet to obtain information about current Microsoft Dynamics NAV sessions.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVServerSession -ServerInstance DynamicsNAV -Tenant default -SessionId 11
```

Description

-----------

This example closes the session with Session ID 11 in the on the DynamicsNAV90 instance.

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

### -SessionId
A number that identifies a Microsoft Dynamics NAV Server session.
You can obtain a list of current sessions using the Get-NAVServerSession cmdlet.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant you want to remove the connection from, such as Tenant1.
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

