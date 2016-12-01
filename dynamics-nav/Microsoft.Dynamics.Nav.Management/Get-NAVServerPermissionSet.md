---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVServerPermissionSet

## SYNOPSIS
Returns a list of permission sets for the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVServerPermissionSet [-ServerInstance] <String> [-Force]
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

Description

-----------

Returns all the PermissionSets for the default ServerInstance.
...
means that are more data that shown in the console window.

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

## INPUTS

## OUTPUTS

### System.Data.DataTable

## NOTES
## RELATED LINKS

