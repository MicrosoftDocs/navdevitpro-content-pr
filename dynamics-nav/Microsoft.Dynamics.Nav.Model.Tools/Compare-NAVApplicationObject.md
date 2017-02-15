---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=398882
schema: 2.0.0
---

# Compare-NAVApplicationObject

## SYNOPSIS
Compares text files with Microsoft Dynamics NAV application objects and then calculates the delta between the two versions. The result of the comparison is a number of text files with the calculated delta. The deltas can later be applied to a third version by using the Update-NAVApplicationObject cmdlet.

## SYNTAX

```
Compare-NAVApplicationObject [-OriginalPath] <String[]> [-ModifiedPath] <String[]> [-DeltaPath] <String>
 [-PassThru] [-Legacy] [-NoCodeCompression] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the Compare-NAVApplicationObject cmdlet to calculate the delta between one version of Microsoft Dynamics NAV application objects and another version. The deltas can later be applied to a third version by using the Update-NAVApplicationObject cmdlet.

The Compare-NAVApplicationObject cmdlet compares the text files in the two specified folders and creates .delta files that describe the difference between the two versions. The text files must contain Microsoft Dynamics NAV application objects that have been exported from the Microsoft Dynamics NAV Development Environment.
You can compare two text files that contain multiple application objects, and you can compare text files in two folders where each text file can contain one or more application objects.

The cmdlet creates a text file for each application object that is different between the two versions. For example, you compare two versions of table 27: an original version and a modified version. The modified version has added a field to the table compared to the original version. In this example, the Compare-NAVApplicationObject cmdlet creates a delta file,TAB27.delta, that describes the difference that the extra field must be inserted into the table.
Then, you use the Update-NAVApplicationObject cmdlet to apply the delta to target files.

## EXAMPLES

### EXAMPLE 1
```
Compare-NAVApplicationObject -OriginalPath .\demodata\ORIGINAL\*.txt -ModifiedPath .\demodata\MODIFIED\*.txt -DeltaPath .\demodata\DELTA\

          Processed 14 objects:
          Inserted   0 objects
          Deleted    1 objects
          Changed    4 objects
          Identical  9 objects
          Failed     0 objects
```

This example compares the text files in the MODIFIED folder to the baseline in the ORIGINAL folder. The result of the comparison is put into the DELTA folder. When the comparison completes, a summary is shown.

### EXAMPLE 2
```
Compare-NAVApplicationObject -OriginalPath .\demodata\ORIGINAL\*.txt -ModifiedPath .\demodata\MODIFIED\*.txt -DeltaPath .\demodata\DELTA -Force -PassThru |
          Update-NAVApplicationObject -TargetPath .\demodata\TARGET\*.txt -ResultPath .\demodata\RESULT -Force

          Processed 14 objects:
          Inserted   0 objects
          Deleted    1 objects
          Updated    3 objects
          Identical  9 objects
          Conflict   1 objects
          Failed     0 objects
```

This example compares the text files in the MODIFIED folder to the baseline in the ORIGINAL folder. The result of the comparison is put into the DELTA folder and also piped to the Update-NAVApplicationObject cmdlet, which applies the updates. When the comparison completes, a summary is shown.

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
Specifies the folder where the result of the comparison between the two versions of application objects must be put. For example, to place the result of the comparison in the DELTA folder that is a subfolder to the current folder, type .\DELTA\*.txt.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Delta

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the cmdlet to overwrite any existing files in the Delta folder.

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

### -Legacy
Reduces the scope of the cmdlet.
Do not set this parameter.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: DevBaseCompatibility

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModifiedPath
Specifies the application objects that you want to compare to the original version.

For example, to compare all text files in the MODIFIED folder that is a subfolder to the current folder, type .\MODIFIED\*.txt.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Modified

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCodeCompression
Specifies if the files that are the result of the comparison must not be compressed.

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

### -OriginalPath
Specifies the application objects that are the baseline of the file comparison.

For example, to use all text files in the ORIGINAL folder that is a subfolder to the current folder, type .\ORIGINAL\*.txt.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Original

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies if the cmdlet must return a FileInfo object for each .delta file that is created by the comparison.
If you do not set this parameter, the cmdlet returns a list of the files.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### None or an object representing the .DELTA file that was created.
When you set the PassThru parameter, the Compare-NavApplicationObject cmdlet returns a FileInfo object for each created .DELTA file. Otherwise, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Merge-NAVApplicationObject](Merge-NAVApplicationObject.md)

[Update-NAVApplicationObject](Update-NAVApplicationObject.md)
