---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=398889
schema: 2.0.0
---

# Set-NAVApplicationObjectProperty

## SYNOPSIS
Sets Microsoft Dynamics NAV application object properties in the specified application object text files.

## SYNTAX

```
Set-NAVApplicationObjectProperty [-TargetPath] <String[]> [-VersionListProperty <String>]
 [-ModifiedProperty <SetModifiedPropertyAction>] [-DateTimeProperty <String>] [-PassThru] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Set-NAVApplicationObjectProperty cmdlet to change the values of the Version List, Date, Time, or Modified properties in the specified text files.
You can use the Get-NAVApplicationObjectProperty cmdlet to extract information about the application objects before you change them.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-NAVApplicationObjectProperty -TargetPath .\COD1.txt -VersionListProperty "DemoV1" -ModifiedProperty Yes -DateTimeProperty (Get-Date -Format g)
```

This example sets new the values for the Version List, Date, Time, and Modified properties in the specified target file.
The date and time is set to the current date and time.
When the update completes, the status is shown, including the updated values of the properties.

### EXAMPLE 2
```
PS C:\>Set-NAVApplicationObjectProperty -TargetPath .\COD1.TXT -DateTimeProperty (Get-Date -Year 2017 -Month 1 -Day 1 -Hour 0 -Minute 0 -Format g) }
```

This example sets a new value for the Date and Time properties in the specified target file.
The date and time is set to a specific, locale-agnostic date and time, January 1st, 2017.
When the update completes, the status is shown, including the updated values of the properties.

### EXAMPLE 3
```
PS C:\>Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\*.txt -ModifiedPath .\MODIFIED\*.txt -TargetPath .\TARGET\*.txt -ResultPath .\RESULT -Force -PassThru |
          Where-Object MergeResult -eq 'Merged' |
          foreach { Set-NAVApplicationObjectProperty -TargetPath $_.ResultPath -DateTimeProperty (Get-Date -Year 2017 -Month 1 -Day 1 -Hour 0 -Minute 0 -Format g) }
```

This example sets a new value for the Date and Time properties in the target files that are passed through by the Merge-NAVApplicationObject cmdlet.
The date and time is set to a specific, locale-agnostic date and time, January 1st, 2017.
When the update completes, the status is shown, including the updated values of the properties.

### EXAMPLE 4
```
PS C:\>$result = Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\*.txt -ModifiedPath .\MODIFIED\*.txt -TargetPath .\TARGET\*.txt -ResultPath .\RESULT -Force
          $result |
          (Get-NAVApplicationObjectProperty -Source .\MODIFIED\COD9999.txt).VersionList
          (Get-NAVApplicationObjectProperty -Source .\TARGET\COD9999.txt).VersionList
          (Get-NAVApplicationObjectProperty -Source .\RESULT\COD9999.txt).VersionList

          Where-Object MergeResult -eq 'Merged' |
          foreach { Set-NAVApplicationObjectProperty -TargetPath $_.Result -VersionListProperty ($_.Modified.VersionList + "," + $_.Target.VersionList + "!");
          Get-NAVApplicationObjectProperty -Source $_.Result }
```

This example merges application objects, gets the VersionList property for the same application object in three different versions, and then sets a new value for the version list.
When the update completes, the status is shown, including the updated values of the properties.

## PARAMETERS

### -DateTimeProperty
Specifies the value of the Date and Time properties that you want to apply to the specified application objects, such as 01-01-2017.
You must specify date and time according to the locale of the computer that you are running Microsoft Dynamics NAV 2017 Development Shell on.
For example, you can use the Get-Date Windows PowerShell cmdlet to get the date before you set the parameter, such as by typing the following command:

Get-Date -Format g

For more information, see the example section.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ModifiedProperty
Sets a value for the Modified property for the application object.
The following options are available:

Yes

The Modified property is set to Yes.

No

The Modified property is set to No.

```yaml
Type: SetModifiedPropertyAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies if the cmdlet must return an object that contains the application object properties for each updated application object.
If you do not set this parameter, the cmdlet returns a list of the changes.

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

### -TargetPath
Specifies the folder where the application objects are stored that you want to update.
You can specify a single text file or all text files in the specified folder.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath, Target

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VersionListProperty
Sets the Version List property for the application objects.
You can specify a value that will overwrite any existing values.
For example, use a command such as the following:

Set-NavApplicationObjectProperty - TargetPath .\COD1.txt -VersionListProperty "MyUpdate"

Alternatively, you can get the property values from the objects first and then add a new value.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NAVApplicationObjectProperty](Get-NAVApplicationObjectProperty.md)
