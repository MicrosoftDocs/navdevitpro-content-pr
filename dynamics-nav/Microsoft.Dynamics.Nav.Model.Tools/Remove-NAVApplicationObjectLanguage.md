---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=400543
schema: 2.0.0
---

# Remove-NAVApplicationObjectLanguage

## SYNOPSIS
Deletes captions in the specified language from Microsoft Dynamics NAV application objects.

## SYNTAX

```
Remove-NAVApplicationObjectLanguage [-Source] <String[]> [-Destination] <String> [[-LanguageId] <String[]>]
 [-DevelopmentLanguageId <String>] [-RemoveRedundant] [-PassThru] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Use the Remove-NAVApplicationObjectLanguage cmdlet to remove a language from a set of Microsoft Dynamics NAV application objects.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-NAVApplicationObjectLanguage -Source TAB14.TXT, PAG9.TXT -Destination .\RESULT
```

This example removes all languages from the Microsoft Dynamics NAV application objects that are specified in the -Source parameter, TAB14.txt and PAG9.txt.
The updated text files are put in the RESULT folder.

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
Specifies the text file or folder where you want the updated objects to be put.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevelopmentLanguageId
Specifies the base development language that must always be available for all objects.
The default value is ENU.
If you do not specify any language in the LanguageId parameter, all available languages are removed from the objects except the development language.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -LanguageId
Specifies the language or list of languages that you want to remove, such as "DEU".
If you do not set this parameter, all available languages are removed except the language that is specified in the DevelopmentLanguageId parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

### -RemoveRedundant
Specifies if you want to remove captions that are the same as the name of the element.

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
Specifies the text file or folder that contains the Microsoft Dynamics NAV application objects that you want to remove a language from.
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

[Export-NAVApplicationObjectLanguage](Export-NAVApplicationObjectLanguage.md)

[Import-NAVApplicationObjectLanguage](Import-NAVApplicationObjectLanguage.md)

[Test-NAVApplicationObjectLanguage](Test-NAVApplicationObjectLanguage.md)
