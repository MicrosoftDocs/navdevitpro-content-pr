---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=401357
schema: 2.0.0
---

# Get-NAVApplication

## SYNOPSIS
Gets information about the application database that is mounted against the specified Microsoft Dynamics NAV Server instance.

## SYNTAX

```
Get-NAVApplication [-ServerInstance] <String> [-Force] [<CommonParameters>]
```

## DESCRIPTION
Use the Get-NAVApplication cmdlet to get information about the application database that is mounted against the specified Microsoft Dynamics NAV Server instance.

If no application is mounted, use the Mount-NAVApplication cmdlet to mount an application.
The cmdlet returns the name of the database server and the name of the application database.

If you have not exported the application tables to a dedicated application database, the Get-NAVApplication cmdlet returns the database that contains the application tables, such as 'Demo Database NAV (10-0)'.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVApplication -ServerInstance DynamicsNAV
```

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
You can pass the value of the ServerInstance parameter as a string to this cmdlet.

## OUTPUTS

### System.Data.DataRow
The cmdlet returns the name of the database server and the name of the application database as a data row.

## NOTES

## RELATED LINKS

[Mount-NAVApplication](Mount-NAVApplication.md)

[Remove-NAVApplication](Remove-NAVApplication.md)
