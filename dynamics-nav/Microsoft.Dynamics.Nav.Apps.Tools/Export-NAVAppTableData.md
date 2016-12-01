---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Export-NAVAppTableData

## SYNOPSIS
Exports data from a Microsoft Dynamics NAV database table to file.

## SYNTAX

```
Export-NAVAppTableData [-Tenant <TenantId>] -Path <String> -TableId <Int32> [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
Use the Export-NAVAppTableData cmdlet to export table data from a Microsoft Dynamics NAV database to a file.
The data must be for a new non-company table created as part of the extension package to which the exported file will be included.

## EXAMPLES

### Example 1
```
Export-NAVAppTableData -ServerInstance DynamicsNAV90 -Path '.\' -TableId 10000
```

Description

-----------

This example exports the data from the table with the ID 10000 in the default tenant database for server instance DynamicsNAV90 to a TAB10000.navxdata file in the current folder.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing export file at the given path.

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

### -Path
Specifies the path to the folder where the export file should be written.
A data file with a name of TAB\<TABLEID\>.navxdata will be created.
(Example: TAB10000.navxdata)

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the Microsoft Dynamics NAV Server instance from which the data will be exported, such as DynamicsNAV90.

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

### -TableId
Specifies the table ID to export.
The ID must be for a new non-company table created as part of the extension.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tenant
Specifies the tenant from which to export data.
If the server instance is configured for single tenant, do not set the parameter.

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS

