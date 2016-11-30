---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Export-NAVAppReportLayout

## SYNOPSIS
Exports the specified custom report layout from a Microsoft Dynamics NAV database to a file.

## SYNTAX

```
Export-NAVAppReportLayout -LayoutCode <String[]> [-Tenant <TenantId>] -Path <String> [-ServerInstance] <String>
 [-PassThru] [-Force]
```

## DESCRIPTION
Use the Export-NAVAppReportLayout cmdlet to export a custom report layout from a Microsoft Dynamics NAV database to a file.

## EXAMPLES

### Example 1
```
Export-NAVAppReportLayout -ServerInstance DynamicsNAV91 -Path .\ReportLayout.layoutdata -LayoutId MS-1016-DEFAULT
```

Description

-----------

This example exports the report layout with the code 'MS-1016-DEFAULT' in the database that is used by the DynamicsNAV91 server instance to the ReportLayout.layoutdata file.

### Example 2
```
Export-NAVAppReportLayout -ServerInstance DynamicsNAV91 -Path .\ReportLayout.layoutdata -LayoutId MS-1016-DEFAULT -PassThru

          Mode             LastWriteTime            Length Name
          ----             -------------            ------ ----
          -a---            11/25/2015   11:47 AM       450 ReportLayout.xml
```

Description

-----------

This example exports the report layout with the code 'MS-1016-DEFAULT' in the database that is used by the DynamicsNAV91 server instance to the ReportLayout.layoutdata file, then returns the location of the file.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing report layout file at the given path.

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

### -LayoutCode
Specifies the Code of the report layout that will be exported.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns the path to the report layout file.

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
Specifies the name and location of the file that the report layout is exported to.

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
Specifies the Microsoft Dynamics NAV Server instance that the report layout will be exported from, such as DynamicsNAV91.

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

### -Tenant
Specifies the tenant from which to export data.
If the server instance is configured for single tenant, do not set the parameter.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: 

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

