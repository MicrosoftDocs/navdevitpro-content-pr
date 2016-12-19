---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401362
schema: 2.0.0
---

# Get-NAVServerPermissionSet

## SYNOPSIS
Returns a list of permission sets for the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerPermissionSet [-ServerInstance] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVServerPermissionSet cmdlet to return a list of permission sets for the specified Microsoft Dynamics NAV Server instance.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVServerPermissionSet MicrosoftDynamicsNavServer

PermissionSetID                         Name
---------------                         ----
ADCS ALL                                ADCS User
ADCS SETUP                              ADCS Set-up
BASIC                                   Basic User (All Inclusive)
CASHFLOW                                Cash Flow Total
CHANGELOG-DELETE                        Delete Change Log Entries
CHANGELOG-SETUP                         Setup Change Log
CHANGELOG-VIEW                          View Change Log Entries
COST                                    Cost Accounting
DOC-APP-SETUP                           Document Approval Setup
DOC-APP-USER                            Document Approval
FA-FIXED ASSET                          Read fixed assets and entries
FA-FIXED ASSET, EDIT                    Edit fixed assets
FA-INS JOURNAL                          Create entries in ins. jnls.
FA-INS JOURNAL, POST                    Post insurance journals
FA-INS REGISTER                         Read insurance registers
...
```

Returns all the PermissionSets for the default ServerInstance.
The ellipse ... means that are more data than is shown in the console window.

## PARAMETERS

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
Returns the permission sets as a table.

## NOTES

## RELATED LINKS

[New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)

[Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)

[Set-NAVServerPermissionSet](Set-NAVServerPermissionSet.md)

[New-NAVServerPermission](New-NAVServerPermission.md)

[Get-NAVServerPermission](Get-NAVServerPermission.md)

[Remove-NAVServerPermission](Remove-NAVServerPermission.md)

[Set-NAVServerPermission](Set-NAVServerPermission.md)
