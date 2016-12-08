---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401389
schema: 2.0.0
---

# Remove-NAVServerUser

## SYNOPSIS
Deletes a Microsoft Dynamics NAV user.

## SYNTAX

### WindowsAccount (Default)
```
Remove-NAVServerUser [-Tenant <TenantId>] -WindowsAccount <String> [-ServerInstance] <String> [-Force]
 [-WhatIf] [-Confirm]
```

### Sid
```
Remove-NAVServerUser [-Tenant <TenantId>] -Sid <String> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

### InputObject
```
Remove-NAVServerUser [-Tenant <TenantId>] -InputObject <DataRow> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

### UserName
```
Remove-NAVServerUser [-Tenant <TenantId>] -UserName <String> [-ServerInstance] <String> [-Force] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Remove-NAVServerUser cmdlet to delete a Microsoft Dynamics NAV user from a specified database or tenant database that is connected to a Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Remove-NAVServerUser MicrosoftDynamicsNavServer -Sid S-1-5-20
```

This example deletes a Microsoft Dynamics NAV user from the database that is connected to the Microsoft Dynamics NAV Server server instance that has the name MicrosoftDynamicsNavServer.
The user is identified by the security identifier.

### EXAMPLE 2
```
Remove-NAVServerUser MicrosoftDynamicsNavServer -WindowsAccount cronus\chris
```

This example deletes a Microsoft Dynamics NAV.
The user is identified by the Windows account user name.

### EXAMPLE 3
```
Remove-NAVServerUser MicrosoftDynamicsNavServer -UserName USER2
```

This example deletes a Microsoft Dynamics NAV.
The user is identified by the user name in Microsoft Dynamics NAV.

### EXAMPLE 4
```
Get-NAVServerUser MicrosoftDynamicsNavServer | Remove-NAVServerUser MicrosoftDynamicsNavServer
```

This example uses piping to delete all Microsoft Dynamics NAV users for the Microsoft Dynamics NAV Server instance with the name MicrosoftDynamicsNavServer.

## PARAMETERS

### -InputObject
Specifies the DataRow object that identifies the user to remove.
You can pass this object from the Get-NAVServerUser cmdlet.

```yaml
Type: DataRow
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

### -Sid
A security identifier (SID) for the Microsoft Dynamics NAV user to delete. The SID is a unique value that identifies a Windows user account. You can use the Sid, UserName, or WindowsAccount parameters to identify the  user. If you use the Sid parameter, then do not set the UserName or WindowsAccount parameters.

```yaml
Type: String
Parameter Sets: Sid
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that the user is stored in, such as Tenant1. This parameter is required unless the specified service instance is not configured to run multiple tenants.

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

### -UserName
Specifies the user name of a Microsoft Dynamics NAV user to delete. The user name is defined by the User Name field in a user's account in Microsoft Dynamics NAV. You can use the UserName, WindowsAccount or Sid parameters to identify the user. If you use the Username parameter, then you cannot use the Windows Account or Sid parameters.

```yaml
Type: String
Parameter Sets: UserName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowsAccount
Specifies the Windows user name of the Microsoft Dynamics NAV user to delete. The value has the domain\username format. You can use the WindowsAccount, UserName, or Sid parameters to identify the user. If you use the WindowsAccount parameter, then you cannot use the UserName or Sid parameters.

```yaml
Type: String
Parameter Sets: WindowsAccount
Aliases:

Required: True
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
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name and tenant ID, if applicable, to the cmdlet.

### System.Data.DataRow
You can pass this object from the Get-NAVServerUser cmdlet to remove a user.


## OUTPUTS

### None

## NOTES
## RELATED LINKS

[Get-NAVServerUser](Get-NAVServerUser.md)

[New-NAVServerUser](New-NAVServerUser.md)

[Set-NAVServerUser](Set-NAVServerUser.md)

[Get-NAVServerUserPermissionSet](Get-NAVServerUserPermissionSet.md)

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)

[Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)
