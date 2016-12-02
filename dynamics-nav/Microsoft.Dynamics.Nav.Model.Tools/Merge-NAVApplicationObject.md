---
external help file: Microsoft.Dynamics.Nav.Model.Tools.dll-Help.xml
online version:
schema: 2.0.0
---

# Merge-NAVApplicationObject

## SYNOPSIS
Compares the changes that have been made to application objects between two versions of Microsoft Dynamics NAV, and applies the difference to a third set of application objects.
The result of the merge is a number of text files with the merged application objects.
Any conflicts that the cmdlet cannot merge are identified in conflict files.

## SYNTAX

```
Merge-NAVApplicationObject [-OriginalPath] <String[]> [-ModifiedPath] <String[]> [-TargetPath] <String[]>
 [-ResultPath] <String> [-PassThru] [-Legacy] [-DateTimeProperty <DateTimePropertyAction>]
 [-ModifiedProperty <ModifiedPropertyAction>] [-VersionListProperty <VersionListPropertyAction>]
 [-DocumentationConflict <DocumentationConflictAction>] [-Strict] [-Force] [-DisableCommentOut] [-WhatIf]
 [-Confirm]
```

## DESCRIPTION
Use the Merge-NAVApplicationObject cmdlet to calculate the changes that have been made to application objects between two versions of Microsoft Dynamics NAV, and to apply the difference to a third set of application objects.
You specify an original version and compare that to a latest version.
The difference is then applied to the target version.
The result of the merge is a number of text files with the merged application objects.
Any conflicts that the cmdlet cannot merge are identified in conflict files.

For example, you can use the cmdlet to apply changes from an update to your version of Microsoft Dynamics NAV.
The following list provides examples of the parameter values that you can specify when you merge versions of Microsoft Dynamics NAV:

OriginalPath - Objects from the Microsoft release of Microsoft Dynamics NAV.

ModifiedPath - Objects from your solution based on Microsoft Dynamics NAV, such as MySolution.

TargetPath - Objects from the updated version of Microsoft Dynamics NAV, such as Cumulative Update 1.

ResultPath - Text files with the result of the merge, such as MySolution upgraded to Microsoft Dynamics NAV 2017 Cumulative Update 1.

The Merge-NAVApplicationObject cmdlet compares OriginalPath to ModifiedPath, applies as many changes as possible to TargetPath, and the resulting text files are stored in the folder that is specified by the ResultPath parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Merge-NAVApplicationObject -OriginalPath C:\Microsoft\NAV2017\DE\RTM\*.TXT -TargetPath C:\Microsoft\NAV2017\DE\CU1\*.TXT -ModifiedPath C:\Solution\NAV2017\DE\RTM\*.TXT -ResultPath C:\Solution\NAV2017\DE\CU1\
          Processed 14 objects:
          Inserted   0 objects
          Deleted    0 objects
          Merged     3 objects
          Identical  9 objects
          Conflict   2 objects
          Failed     0 objects
          Processed 5 changes:
          Conflict   1 changes
          % Merged   80,00
```


This example compares the application objects from the German version of Microsoft Dynamics NAV 2017 to a customized solution that modified that version.
The result of the comparison is applied to the German version of Microsoft Dynamics NAV 2017 Cumulative Update 1.
The final result is stored in the folder that is specified in the -ResultPath parameter.
When the merge completes, the summary of the result is shown.

### EXAMPLE 2
```
PS C:\>Merge-NAVApplicationObject -OriginalPath C:\Solution\ORIGINAL\COD1-RTM.TXT -ModifiedPath C:\Solution\MODIFIED\My-COD1-RTM.txt -TargetPath C:\Solution\TARGET\COD1-CU1.TXT -ResultPath C:\Solution\RESULT\My-COD1-CU1.TXT - -PassThru
```

This example compares a text file with codeunit 1 from the original release of Microsoft Dynamics NAV to a modified version of codeunit 1.
The result of the comparison is applied to a version of codeunit 1 from Cumulative Update 1.
The final result is stored in the file that is specified in the -ResultPath parameter.
When the merge completes, the summary of the result is shown.

### EXAMPLE 3
```
PS C:\>Merge-NAVApplicationObject -OriginalPath C:\Solution\ORIGINAL\*.TXT -ModifiedPath C:\Solution\MODIFIED\*.txt -TargetPath C:\Solution\TARGET\*.TXT -ResultPath C:\Solution\RESULT\ | Sort-Object ObjectType, Id | Format-Table

ObjectType  Id  MergeResult  Original              Target                 Modified               Result                 Conflict               Error  
----------  --  -----------  --------              ------                 --------               ------                 --------               -----  
Codeunit    1   Conflict     C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  C:\Solution\CONFLI...  
Codeunit    6   Merged       C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  
Codeunit    7   Identical    C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  
Codeunit    8   Conflict     C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  C:\Solution\CONFLI...  
Codeunit    9   Merged       C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  
Page        6   Identical    C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  
Page        7   Identical    C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...  
Table       4   Identical    C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...
Table       14  Identical    C:\Solution\ORIGIN...  C:\Solution\TARGET...  C:\Solution\MODIFI...  C:\Solution\RESULT...
```

This example compares two sets of text files and applies the result of the comparison to a third version.
The final result is stored in the folder that is specified in the -ResultPath parameter.
When the merge completes, the summary of the result is shown as a table.

### EXAMPLE 4
```
PS C:\>$myVariable = Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\*.txt -TargetPath .\TARGET\*.txt
          -ModifiedPath .\MODIFIED\*.txt -ResultPath .\RESULT -Force

          $myVariable.Summary

          $myVariable |
          Where-Object MergeResult -eq 'Conflict' |
          Select Original, Target |
          Format-List
          Processed 14 objects:
          Inserted   0 objects
          Deleted    0 objects
          Merged     3 objects
          Identical  9 objects
          Conflict   2 objects
          Failed     0 objects
          Processed 5 changes:   Conflict   1 changes
          % Merged   80,00


          OriginalPath : C:\Solution\ORIGINAL\COD1.TXT
          TargetPath   : C:\Solution\TARGET\COD1.TXT

          OriginalPath : C:\Solution\ORIGINAL\COD8.TXT
          TargetPath   : C:\Solution\TARGET\COD8.TXT
```

This example compares two sets of text files and applies the result of the comparison to a third version.
The final result is stored in the folder that is specified in the -ResultPath parameter.
When the merge completes, the files with conflicting code are shown in a list.

### EXAMPLE 5
```
PS C:\>Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\*.txt -TargetPath .\TARGET\*.txt
          -ModifiedPath .\MODIFIED\*.txt -ResultPath .\RESULT -Force -PassThru |

          Where-Object MergeResult -eq 'Conflict' |
          foreach { NOTEPAD.EXE $_.Conflict }
```

This example compares two sets of text files and applies the result of the comparison to a third version.
The final result is stored in the folder that is specified in the -ResultPath parameter.
When the merge completes, the files with conflicting code are opened in Notepad.

### EXAMPLE 6
```
PS C:\>Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\pag9999.txt -ModifiedPath .\MODIFIED\pag9999.txt `
          -TargetPath .\TARGET\pag9999.txt -ResultPath .\RESULT\pag9999a.txt -Force -DocumentationConflict Strict

          Merge-NAVApplicationObject -OriginalPath .\ORIGINAL\pag9999.txt -ModifiedPath .\MODIFIED\pag9999.txt `
          -TargetPath .\TARGET\pag9999.txt -ResultPath .\RESULT\pag9999a.txt -Force -DocumentationConflict ModifiedFirst
          Processed 1 objects:
          Inserted   0 objects
          Deleted    0 objects
          Merged     0 objects
          Identical  0 objects
          Conflict   1 objects
          Failed     0 objects
          Processed 2 changes:
          Conflict   1 changes
          % Merged   50,00

          Processed 1 objects:
          Inserted   0 objects
          Deleted    0 objects
          Merged     1 objects
          Identical  0 objects
          Conflict   0 objects
          Failed     0 objects
          Processed 2 changes:
          Conflict   0 changes
          % Merged   100,00
```


This example compares the documentation triggers in two versions of a page object and applies the result of the comparison to a third version.
The final result is stored in the file that is specified in the -ResultPath parameter.
This is then repeated.
In the first command, the -DocumentationConflict parameter is set to Strict so that conflicting documentation is captured as conflicts.
In the second command, the conflicting entries are both inserted into the resulting file with the content from MODIFIED listed first.
When the merge completes, a summary of the merge is shown.

## PARAMETERS

### -DateTimeProperty
Specifies the value of the Date and Time properties for the merged application objects.
The following options are available:

Now

In the result of the application merge, the Date and Time properties are set to the current date and time.

Clear

In the result of the application merge, the Date and Time properties are empty.

FromTarget

In the result of the application merge, the Date and Time properties are set to the value from the target application objects.
This is the default value.

FromModified

In the result of the application merge, the Date and Time properties are set to the value from the modified application objects.

```yaml
Type: DateTimePropertyAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableCommentOut
Specifies if the cmdlet must not comment out merged code that cannot be imported into the development environment.

Merged code is passed through a simple parser, and any indication that it cannot be imported into the development environment results in commenting out the code.
Use this parameter to disable this functionality.
Code can be commented out if the merge results in unbalanced BEGIN and END statements, such as if both MODIFIED and TARGET contain an END statement.

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
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DocumentationConflict
Specifies how conflicting lines in documentation triggers are merged.
Set this parameter when you are merging objects with the same type of content in the documentation trigger, such as technical descriptions or a version list.
The following options are available:

Strict

Conflicting lines of documentation are reported as conflicts in the same way as all other conflicts.
Use this value when the objects contain technical descriptions in the documentation triggers.

ModifiedFirst

Conflicting lines of documentation are merged into the result file with the content from the modified object listed first.
Use this value when the objects contain version history in the documentation triggers.
This is the default value.

TargetFirst

Conflicting lines of documentation are merged into the result file with the content from the target object listed first.
Use this value when the objects contain version history in the documentation triggers.

```yaml
Type: DocumentationConflictAction
Parameter Sets: (All)
Aliases:
Accepted values: Strict, ModifiedFirst, TargetFirst

Required: False
Position: Named
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

### -ModifiedProperty
Specifies the value of the Modified property for the merged application objects.
The following options are available:

Yes

In the result of the application merge, the Modified property is set to Yes.

No

In the result of the application merge, the Modified property is set to No.

FromTarget

In the result of the application merge, the Modified property is set to the value from the target application objects.
This is the default value.

FromModified

In the result of the application merge, the Modified property is set to the value from the modified application objects.

```yaml
Type: ModifiedPropertyAction
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
Position: 2
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

### -ResultPath
Specifies the folder where the result of the merge between the two versions of application objects must be put.
The folder must already exist.

For example, to use the RESULT folder that is a subfolder to the current folder, type .\RESULT\.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Result

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Strict
Specifies if the cmdlet must report all conflicts, including non-functional conflicts such as the order in which variables or methods are listed in the text files.
If this parameter is not set, these conflicts are suppressed to reduce "noise".

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
Specifies the application objects that the difference between the original version and the modified version must be applied to.

For example, to use all txt files in the TARGET folder that is a subfolder to the current folder, type .\ TARGET\*.txt.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: Target

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionListProperty
Specifies if you want to update the Version List property for the application objects.
The default value is Clear.
The following options are available:

Clear

In the result of the application merge, the Version List property is empty.
This is the default value.

FromTarget

In the result of the application merge, the Version List property is set to the value from the target application objects.

FromModified

In the result of the application merge, the Version List property is set to the value from the modified application objects.

```yaml
Type: VersionListPropertyAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### A summary of all the merge operations or an object representing each merge operation individually.
When you use the PassThru parameter, the Merge-NAVApplicationObject cmdlet returns an object that represents each merge operation.
Otherwise, an object representing just a summary is returned.

## NOTES

## RELATED LINKS
[Compare-NAVApplicationObject](Compare-NAVApplicationObject.md)  

[Update-NAVApplicationObject](Update-NAVApplicationObject.md)  
