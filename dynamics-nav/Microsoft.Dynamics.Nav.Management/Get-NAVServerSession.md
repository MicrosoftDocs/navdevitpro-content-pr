---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401363
schema: 2.0.0
---

# Get-NAVServerSession

## SYNOPSIS
Returns information about active sessions for a Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerSession [-Tenant <TenantId>] [-ServerInstance] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVServerSession cmdlet to return information about active sessions for a Microsoft Dynamics NAV Server instance.
The following information is returned for each session:

Server Instance ID  
Session ID  
User SID  
Server Instance Name  
Server Computer Name  
User ID  
Client Type  
Client Computer Name  
Login Datetime  
Database Name  

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerSession -ServerInstance DynamicsNAV -Tenant default

ServerInstanceID   : 1

SessionID                 : 1

UserSID                   : DE8B398E-C154-45BC-931A-3A74A8AF5A85

ServerInstanceName : DynamicsNAV90

ServerComputerName : MyServer

UserID                    : CRONUSNavUser1

ClientType                : WindowsClient

ClientComputerName : MyComputer

LoginDatetime             : 21-09-2013 13:06:24

DatabaseName              : Demo Database NAV


ServerInstanceID   : 1

SessionID                 : 2

UserSID                   : DE8B398E-C154-45BC-931A-3A74A8AF5A85

ServerInstanceName : DynamicsNAV90

ServerComputerName : MyServer

UserID                    : CRONUSNavUser2

ClientType                : WindowsClient

ClientComputerName : MyOtherComputer

LoginDatetime             : 21-09-2013 10:28:40

DatabaseName              : Demo Database NAV
```

The example returns a list of all client connections for the Microsoft Dynamics NAV Server instance DynamicsNAV.
The return data shows two Windows client users.

## PARAMETERS

### -Tenant
Specifies the ID of the tenant that you want to get the active sessions for, such as Tenant1.
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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

### System.Data.DataTable
Returns the active session information as a table.

## NOTES

## RELATED LINKS

[Remove-NAVServerSession](Remove-NAVServerSession.md)
