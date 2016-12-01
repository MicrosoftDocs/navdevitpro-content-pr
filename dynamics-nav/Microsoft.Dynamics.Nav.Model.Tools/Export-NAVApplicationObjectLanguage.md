---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Export-NAVApplicationObjectLanguage

## SYNOPSIS
Exports captions from the specified text files with Microsoft Dynamics NAV application objects.
The captions are exported to text files.

## SYNTAX

```
Export-NAVApplicationObjectLanguage [-Source] <String[]> [-Destination] <String> [[-LanguageId] <String[]>]
 [-Encoding <FileEncoding>] [-DevelopmentLanguageId <String>] [-PassThru] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Export-NAVApplicationObjectLanguage cmdlet to export multilanguage captions from text files that contain Microsoft Dynamics NAV application objects.
The resulting text files are similar to the multilanguage files that you can export in the Microsoft Dynamics NAV Development Environment.
If your source files contain more than one language, you can choose to export one language, multiple languages, or all languages.

For example, you export 4 Microsoft Dynamics NAV objects to a text file, and they have captions in English (US), German, and French.
You then use the Export-NAVApplicationObjectLanguage cmdlet to export the German and French captions.
The cmdlet creates a language-specific text file for each object, such as TAB18-DEU.txt and TAB18-FRA.txt.
Alternatively, you can choose to create a single language-specific text file with all captions for all objects.
Or you can choose to store the languages in memory so that you can pipe the result to another Windows PowerShell cmdlet such as Import-NAVApplicationObjectLanguage.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Export-NAVApplicationObjectLanguage -Source .\ORIGINAL\ -LanguageId "DEU","FRA" -Destination .\RESULT\
```

Description

-----------

This example exports the DEU and FRA languages from the Microsoft Dynamics NAV application objects that are in the ORIGINAL folder.
The result of the export is a separate text file for each object and for each language, such as TAB18-DEU.txt and TAB18-FRA.txt.

### EXAMPLE 2
```
PS C:\>Export-NAVApplicationObjectLanguage -Source .\ORIGINAL\ -LanguageId "DEU","FRA" -Destination .\RESULT\languages.txt
```

Description

-----------

This example exports the DEU and FRA languages from the Microsoft Dynamics NAV application objects that are in the ORIGINAL folder.
The result of the export is a single text file in the RESULT folder that lists all strings for all objects in one language first and then the other language.

### EXAMPLE 3
```
PS C:\>Export-NAVApplicationObjectLanguage -Source .\ORIGINAL\ -LanguageId "DEU","FRA" -Destination .\RESULT\languages.txt
          Get-Content .\RESULT\languages.txt |
          Sort-Object |
          Set-Content .\RESULT\languages-sorted.txt
```

Description

-----------

This example is similar to example 2 and exports the DEU and FRA languages to a single text file in the RESULT folder that lists all strings for all objects in one language first and then the other language.
The exported captions are read into memory, sorted by object ID so that the DEU and FRA captions for the same object are listed together.
This new result is saved to a new file.

### EXAMPLE 4
```
PS C:\>foreach ($lang in ('DEU', 'FRA'))
          {
          Export-NAVApplicationObjectLanguage -Source ORIGINAL\*.txt
          -LanguageId $lang -Destination .\RESULT\ALL-$lang.txt
          }
```

Description

-----------

When used in a script, this code snippet exports the DEU and FRA languages from the Microsoft Dynamics NAV application objects that are in the SOURCE folder.
The result of the export is two text files in the RESULT folder that each lists all strings for all objects in that language.
In this example, the resulting text files are ALL-DEU.txt and ALL-FRA.txt.

## PARAMETERS

### -Destination
Specifies the text file or folder where the result of the export must be put.
If you do not set this parameter, captions are stored in memory and can be piped to another Windows PowerShell cmdlet such as Import-NAVApplicationObjectLanguage.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
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

### -DevelopmentLanguageId
Specifies you want to generate captions in the base development language if captions are missing.
Missing captions are generated based on the object name in the language that is specified as the base development language.
The default value is ENU because the base development language in Microsoft Dynamics NAV is English (US).

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
Specifies the language or list of languages that you want to export, such as "DEU".
If you do not set this parameter, all available languages are exported.

If the parameter is omitted, the output contains a line for every text value in the object.
If you specify a list of language IDs, the output contains one line for each language that has been added for each object.
If a language is not present on a property that is translated into another language, the entry for the missing language is empty.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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
Specifies the text file or folder that contains Microsoft Dynamics NAV application objects.
The cmdlet does not modify these text files.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: PSPath

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

