---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Get-NAVDataFile

## SYNOPSIS
Gets information from a Microsoft Dynamics NAV data file.

## SYNTAX

```
Get-NAVDataFile [-FilePath] <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVDataFile cmdlet to extract information from a Microsoft Dynamics NAV data file.
The file must have been exported from a Microsoft Dynamics NAV database and can contain company-specific data, global data, application data, and application objects.
The following information is returned from the .navdata file:
ExportVersion
DatabaseVersion
Description
IncludeApplication
IncludeApplicationData
TenantId
IncludeGlobalData
CompanyName
ExportDateTime

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
Get-NAVDataFile -FilePath C:\file\Customer.navdata
```

Description

-----------

This example extracts information from the specified file to show an overview of what is in the file (*.navdata).
The extracted information includes a list of the companies and specifies if global data, application data, or application objects are included.
If a description was added to the file when the data was exported, this description is also shown.

## PARAMETERS

### -FilePath
Specifies the path and name of the file that you want to import data from.
The file must be a .navdata file type that has been exported from Microsoft Dynamics NAV.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FileName

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

## NOTES
## RELATED LINKS

