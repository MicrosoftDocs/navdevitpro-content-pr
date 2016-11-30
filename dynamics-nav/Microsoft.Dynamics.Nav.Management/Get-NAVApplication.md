---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVApplication

## SYNOPSIS
Gets information about the application database that is mounted against the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVApplication [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVApplication cmdlet to get information about the application database that is mounted against the specified Microsoft Dynamics NAV Server instance.
If no application is mounted, use the Mount-NAVApplication cmdlet to mount an application.
The cmdlet returs the name of the database server and the name of the application database.
If you have not exported the application tables to a dedicated application database, the Get-NAVApplication cmdlet returns the database that contains the application tables, such as 'Demo Database NAV (10-0)'.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVApplication -ServerInstance DynamicsNAV
```

Description

-----------

This example returns information about the application database that is mounted against the DynamicsNAV server instance.

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

### System.Data.DataRow

## NOTES
## RELATED LINKS

