---
external help file: Microsoft.Dynamics.Nav.Apps.Tools.dll-Help.xml
online version:
schema: 2.0.0
---

# Compare-NAVAppApplicationObjectLanguage

## SYNOPSIS
Compares the language text files in two folders (original and modified) and calculates the deltas.
The result of the comparison is a language text file per object with the calculated delta.

## SYNTAX

```
Compare-NAVAppApplicationObjectLanguage [-OriginalPath] <String[]> [-ModifiedPath] <String[]>
 [-DeltaPath] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Compare-NAVAppApplicationObjectLanguage cmdlet to calculate the delta between an original version and modified version of language text files.
The resulting delta language text files can then be included in a NAV App package by using the New-NAVAppPackage cmdlet.

The Compare-NAVAppApplicationObjectLanguage cmdlet compares all of the language text files in the two specified folders and creates a delta language text file per object that includes the differences. The language text files to compare must be in the format of exported multilanguage files created by using the Export-NAVApplicationObjectLanguage cmdlet or the Microsoft Dynamics NAV Development Environment. You can compare two language text files that contain multiple application objects or multiple language text files containing a single object, or any combination therein. The cmdlet will compare the translations for all objects across all of the language text files in the specified folders.

The cmdlet creates a language text file per object that includes all of the translated \*ML properties and text constants (deltas) for that object. For example, you export the text strings for the Microsoft Dynamics NAV objects that you will be providing translations for to text files in a MLORIGINAL folder. You then put a copy of the exported text file into a MLMODIFIED folder and add your translated strings directly to the file.

You then use the Compare-NAVAppApplicationObjectLanguage cmdlet to compare the language text files in the MLORIGINAL and MLMODIFIED folders, saving the resulting delta language text files to a MLDELTA folder. Then when using the New-NAVAppPackage cmdlet to create the NAV App package, the MLDELTA folder is provided for the -SourcePath parameter.

## EXAMPLES

### Example 1
```
Compare-NAVAppApplicationObjectLanguage -OriginalPath /MLORIGINAL -ModifiedPath /MLMODIFIED -DeltaPath /MLDELTA

          Page 70001: Added
          Table 70006: Modified
```

This example compares the language text files in the MLORIGINAL and MLMODIFIED folders, creating the resulting delta language text files in the MLDELTA folder.
When the comparison completes, a summary is shown.

### Example 2
```
Compare-NAVAppApplicationObjectLanguage -OriginalPath /MLORIGINAL -ModifiedPath /MLMODIFIED -DeltaPath /MLDELTA -Confirm

          Page 70001: Added
          Table 70006: Modified
```

This example compares the language text files in the MLORIGINAL and MLMODIFIED folders, creating the resulting delta language text files in the MLDELTA folder.
The -Confirm parameter specifies that the user must confirm the process.
When the comparison completes, a summary is shown.

### Example 3
```
Compare-NAVAppApplicationObjectLanguage -OriginalPath /MLORIGINAL -ModifiedPath /MLMODIFIED -DeltaPath /MLDELTA -Confirm

          Page 70001: Added
          Table 70006: Modified
```

This example compares the language text files in the MLORIGINAL and MLMODIFIED folders, creating the resulting delta language text files in the MLDELTA folder.
The -Force parameter specifies that an existing file in the delta folder with the same name will be overwritten without prompting the user.
When the comparison completes, a summary is shown.

### Example 4
```
Compare-NAVAppApplicationObjectLanguage -OriginalPath /MLORIGINAL -ModifiedPath /MLMODIFIED -DeltaPath /MLDELTA -PassThru

          Page 70001: Added
          Table 70006: Modified
```

This example compares the language text files in the MLORIGINAL and MLMODIFIED folders, creating the resulting delta language text files in the MLDELTA folder.
The -PassThru parameter returns a FileInfo object for each delta language file that is created by the comparison.
When the comparison completes, a summary is shown.

## PARAMETERS

### -Confirm
Specifies that the user must confirm the process before the cmdlet runs.

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

### -DeltaPath
Specifies the folder where the calculated delta language files will be placed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Delta

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation to overwrite an existing file at the given path.

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

### -ModifiedPath
Specifies the folder containing the modified language files to compare.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Modified

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginalPath
Specifies the folder containing the original language files to compare.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Original

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS
[Export-NAVApplicationObjectLanguage](../Microsoft.Dynamics.Nav.Model.Tools/Export-NAVApplicationObjectLanguage.md)  

[New-NAVAppPackage](New-NAVAppPackage.md)
