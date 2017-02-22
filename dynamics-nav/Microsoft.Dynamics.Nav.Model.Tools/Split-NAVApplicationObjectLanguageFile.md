---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=400545
schema: 2.0.0
---

# Split-NAVApplicationObjectLanguageFile

## SYNOPSIS
Splits a text file that contains multilanguage captions for two or more application objects into separate text files for each application object.

## SYNTAX

```
Split-NAVApplicationObjectLanguageFile [-Source] <String[]> [[-Destination] <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use the Split-NAVApplicationObjectLanguageFile cmdlet to split a text file that contains multilanguage captions for two or more application objects into separate text files for each application object.
For example, if you have exported captions for tables 18 and 27 to a single text file such as MySolution_Languages.txt, you can use the cmdlet to create two new text files, TAB18.txt and TAB27.txt.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Split-NAVApplicationObjectLanguageFile -Source single.txt -Destination .\RESULT\
```

This example splits the single.txt file into separate text files for each Microsoft Dynamics NAV application object that the file contains captions for, such as TAB18.txt and TAB27.txt.

## PARAMETERS

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

### -Destination
Specifies the text file or folder where you want the generated files to be put.
Optionally, do not set this parameter so that you can pipe the result to another Windows PowerShell cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Skips confirmation prompts when the cmdlet is run.

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

### -PassThru
Specifies if you want to return an object for each application object and language ID with their language text values.

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

### -Source
Specifies the text file or folder that contains the text files that you want to split.
The cmdlet does not modify these text files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

[Join-NAVApplicationObjectLanguageFile](Join-NAVApplicationObjectLanguageFile.md)

[Split-NAVApplicationObjectFile](Split-NAVApplicationObjectFile.md)
