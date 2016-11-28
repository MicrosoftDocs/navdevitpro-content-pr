---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-NAVAddIn

## SYNOPSIS
Registers an add-in the system table 2000000069 Add-ins of the Microsoft Dynamics NAV database.

## SYNTAX

### AddInResource (Default)
```
New-NAVAddIn -AddInName <String> [-Version <String>] -PublicKeyToken <String> [-Category <AddInCategory>]
 [-Description <String>] [-Resource <Byte[]>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### AddInResourceFile
```
New-NAVAddIn -AddInName <String> [-Version <String>] -PublicKeyToken <String> [-Category <AddInCategory>]
 [-Description <String>] [-ResourceFile <String>] [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Add-ins must be registered in table 2000000069 Add-ins before they can be used in a Microsoft Dynamics NAV client or on the Microsoft Dynamics NAV Server instance.
The New-NAVAddin cmdlet creates an entry for the add-in in the table.
An add-in typically consists of one or more .NET Framework assemblies and support files.
These files must be installed either on the computer running the Microsoft Dynamics NAV Server or client.
Instead of manually installing the add-in files, you can use the -ResourceFile parameter of the cmdlet to set up the system to automatically deploy the add-in the first time that it is requested.
To do this, before you run the New-NAVAddin cmdlet, create a compressed (.zip type) file that contains the files (in the desired folder structure) that are associated with the add-in.
For an add-in to be deployed automatically, it must have the same name as the assembly that contains it.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
New-NAVAddIn -ServerInstance DynamicsNAV -Category dotnetcontroladdin -PublicKeyToken 31bf3856ad364e35 -ResourceFile 'c:\addins\MyNavAddin.zip'
```

Description

-----------

This example registers an add-in of the DotNet Control Add-in category in the system table 2000000069 Add-ins.
The example also uploads the add-in files that are contained in the MyNavAddin.zip file that is located in the folder path c:\addin.

## PARAMETERS

### -AddInName
Specifies the name of the add-in.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Category
Specifies the category of the add-in.
There are four categories that you can specify: DotNet Control Add-in, DotNet Interoperability, Javascript Control Add-in, and Language Resource.

```yaml
Type: AddInCategory
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description of the add-in for identification purposes.

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

### -PublicKeyToken
Specifies a public token key of the add-in.
The public key token is a 16-character key that is given to the add-in assembly when it is built and signed in Microsoft Visual Studio.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Resource
Specifies a resource file for the add-in.
the resource file can be used to stream the add-in to the Microsoft Dynamics NAV Server instance.

```yaml
Type: Byte[]
Parameter Sets: AddInResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceFile
Specifies the full path to a compressed file (.zip type) that contains the add-in assembly and associated files.
The full path includes the drive, folders and file name.
Use this parameter to set up the automatic deployment of the add-in files to Microsoft Dynamics NAV Server instances instead of manually deploying the files.

```yaml
Type: String
Parameter Sets: AddInResourceFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Version
Specifies a version number for the add-in.
The version number must have the format N.N.N.N, such as 8.0.0.0.
This version number must match the version number that is assigned to the assembly.

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
Prompts you for confirmation before executing the command.

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

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

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

### -Force
{{Fill Force Description}}

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

## INPUTS

## OUTPUTS

## NOTES
## RELATED LINKS

