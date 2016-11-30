---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Join-NAVApplicationObjectFile

## SYNOPSIS
Combines multiple application object files into one text file.

## SYNTAX

```
Join-NAVApplicationObjectFile [-Source] <String[]> [-Destination] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Join-NAVApplicationObjectFile to combine the application objects in the specified folder into a single text file.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
PS C:\>Join-NAVApplicationObjectFile -Source C:\Solution\TXT\COD*.txt -Destination C:\Solution\all-codeunits.txt
```

Description

-----------

This example merges a list of files with application objects, such as COD1.TXT and COD2.TXT, into a single, larger file, all-codeunits.txt.
When the merge completes, the status is shown with information about the file that was created.

## PARAMETERS

### -Destination
Specifies the name and location of the generated text file.

For example, to generate the MyObjects.txt file in the current folder, type .\MyObjects.txt.

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

### -Force
Forces the cmdlet to overwrite any existing files in the Result folder.

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
Specifies the folder that stores the text files with application objects that you want to merge into a single text files with all application objects.

For example, to use all text files in the SOURCE folder that is a subfolder to the current folder, type .\SOURCE\*.txt.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Result, PSPath

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

