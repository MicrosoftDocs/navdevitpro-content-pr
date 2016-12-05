---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Join-NAVApplicationObjectLanguageFile

## SYNOPSIS
Combines multiple text files with captions for Microsoft Dynamics NAV application objects into one text file.

## SYNTAX

```
Join-NAVApplicationObjectLanguageFile [-Source] <String[]> [[-Destination] <String>] [-Force] [-PassThru]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Join-NAVApplicationObjectLanguageFile cmdlet to combine multiple text files with captions for Microsoft Dynamics NAV application objects into one text file.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Join-NAVApplicationObjectLanguageFile -Source "*-ESP.TXT" -Destination .\RESULT\All-ESP.txt
```

Description

-----------

This example combines all the text files with Spanish translations into a single text file.
In this example, you have previously exported Spanish strings into separate text files for each application object.

## PARAMETERS

### -Destination
Specifies the text file or folder where you want the generated files to be put.
Optionally, do not set this parameter so that you can pipe the result to another Windows PowerShell cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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
Specifies the text file or folder that contains the text files that you want to combine.
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

