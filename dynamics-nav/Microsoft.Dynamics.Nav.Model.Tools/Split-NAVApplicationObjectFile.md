---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version: 
schema: 2.0.0
---

# Split-NAVApplicationObjectFile

## SYNOPSIS
Splits a text file that contains two or more application objects into separate text files for each application object.

## SYNTAX

```
Split-NAVApplicationObjectFile [-Source] <String> [[-Destination] <String>] [-PassThru] [-PreserveFormatting]
 [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Split-NAVApplicationObjectFile cmdlet to split a text file that contains two or more application objects into separate text files for each application object.
For example, if you have exported tables 18 and 27 to a single text file such as MySolution.txt, you can use the cmdlet to create two new text files, TAB18.txt and TAB27.txt.

The Split-NAVApplicationObjectFile cmdlet can copy each application object to a new file, or it can recreate the object in the new file.
The default setting is to recreate the object, but you can change this by setting the PreserveFormatting parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Split-NAVApplicationObjectFile -Source C:\Solution\All.txt -Destination C:\Solution\TXT\
```

Description

-----------

This example creates separate text files for each application object in the All.txt file, such as TAB18.TXT and TAB27.TXT.

### EXAMPLE 2
```
PS C:\>Split-NAVApplicationObjectFile -Source C:\Solution\All.txt -Destination C:\Solution\TXT\ -PreserveFormatting
```

Description

-----------

This example creates separate text files for each application object in the All.txt file, such as TAB18.TXT and TAB27.TXT.
By setting the PreserveFormatting parameter, each object is an exact copy, including extra line breaks or potential syntax errors.
This makes it easier to compare files afterwards, for example.

## PARAMETERS

### -Destination
Specifies the folder where the resulting text files must be put.

For example, to use the TXT folder that is a subfolder to the current folder, type .\TXT\.

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
Forces the cmdlet to overwrite any existing files in the Destination folder.

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
Specifies if the cmdlet must return a FileInfo object for each text file that is created.
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

### -PreserveFormatting
Specifies if you want to keep the structure of the application objects as shown in the source text file.
This copies the textual descriptions of the objects line by line so that the description of the object is identical in the source file and destination file.

If you do not set this parameter, each application object is identified, translated from text to metadata, and then written to the destination text file.
As a result, the object in the generated text file can look different from the source file by listing properties in a different order, or by having removed empty lines, for example.

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
Specifies the file that contains multiple application objects that you want to split into separate text files for each application object.

For example, to specify the MySolution.txt files in the SOURCE folder that is a subfolder to the current folder, type .\SOURCE\MySolution.txt.

```yaml
Type: String
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

