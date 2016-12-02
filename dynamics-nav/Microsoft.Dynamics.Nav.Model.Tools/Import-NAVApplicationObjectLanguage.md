---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version:
schema: 2.0.0
---

# Import-NAVApplicationObjectLanguage

## SYNOPSIS
Imports strings in the specified language into text files that contain Microsoft Dynamics NAV application objects.

## SYNTAX

```
Import-NAVApplicationObjectLanguage [-Source] <String[]> [-LanguagePath] <String[]> [-Destination] <String>
 [[-LanguageId] <String[]>] [-Encoding <FileEncoding>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Import-NAVApplicationObjectLanguage cmdlet to import a language into the Microsoft Dynamics NAV application objects.
For example, if you have exported multilanguage files in the Microsoft Dynamics NAV Development Environment, or by using the Export-NAVApplicationObjectLanguage cmdlet, you can import the strings into another version of the same application objects.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Import-NAVApplicationObjectLanguage -Source .\TAB14.TXT -LanguageId "ESP" -LanguagePath .\ALL-ESP.TXT -Destination .\RESULT\
```

This example imports the ESP language into the Microsoft Dynamics NAV application object that is specified in the -Source parameter, TAB14.txt.
The strings are imported from the text files in the ALL-ESP.txt file, and the result of the command is a text file in the RESULT folder, TAB14.txt, that includes captions in Spanish.

## PARAMETERS

### -Destination
Specifies the text file or folder where you want the result of the import to be put.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding
Specifies the encoding for the exported file.
Valid values are Unicode, UTF7, UTF8, ASCII, UTF32, BigEndianUnicode, Default, and OEM.
The default value is OEM, which is the default encoding for the Microsoft Dynamics NAV Development Environment.

```yaml
Type: FileEncoding
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

### -LanguagePath
Specifies the text file or files or folder with text files that contain the language-specific strings.
The text files must have been exported from Microsoft Dynamics NAV in the development environment or by using the Export-NAVApplicationObjectLanguage cmdlet.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath, Language

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LanguageId
Specifies the language or list of languages that you want to import, such as "DEU".
If you do not set this parameter, all available languages are imported.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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
Specifies the text file or folder that contains the Microsoft Dynamics NAV application objects that you want to import a language into.
The cmdlet does not modify these text files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
[Export-NAVApplicationObjectLanguage](Export-NAVApplicationObjectLanguage.md)  

[Remove-NAVApplicationObjectLanguage](Remove-NAVApplicationObjectLanguage.md)  

[Test-NAVApplicationObjectLanguage](Test-NAVApplicationObjectLanguage.md)
