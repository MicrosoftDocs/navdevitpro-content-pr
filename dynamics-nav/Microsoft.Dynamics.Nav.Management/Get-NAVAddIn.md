---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVAddIn

## SYNOPSIS
Returns information about add-ins that are registered in the table 2000000069 Add-ins of the Microsoft Dynamics NAV database.

## SYNTAX

```
Get-NAVAddIn [-AddInName <String>] [-Version <String>] [-PublicKeyToken <String>] [-Category <AddInCategory>]
 [-IncludeResource] [-ServerInstance] <String> [-Force]
```

## DESCRIPTION
The cmdlet displays the following information about the add-ins:

AddInName - The name of the add-in as it appears in the database table.

PublicTokenKey - A 16-character key that is given to the add-in assembly when it is built.

Version - The version number of the add-in.

Category - The category that add-in is assigned to. There are four different categories: Javascript Control Addin, DotNet Control Add-in, DotNet Interoperability, and Language Resource.

Resource (optional) - The resource binaries of the add-in. You use the parameters to filter the returned information on specific add-ins.

## EXAMPLES

### EXAMPLE 1
```
Get-NAVAddIn -ServerInstance DynamicsNAV -Category dotnetcontroladdin
```

This example returns a list of add-ins of the category DotNet Control Add-in that are registered in the database that is connected to the DynamicsNAV.

## PARAMETERS

### -AddInName
Specifies the name of an add-in that you want view information about.
The name must match the name as it appears in the database table.

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

### -Category
Specifies that category to filter the results on.

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

### -IncludeResource
Specifies to include the resource binaries with each add-in that is returned.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicKeyToken
Specifies a public token key to filter the results on.
The public key token is a 16-character key that is given to the assembly when it is built and signed in Microsoft Visual Studio.

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
Specifies the add-in version number to filter on.

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

### -Force
Forces the command to run without asking for user confirmation.

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
[New-NAVAddIn](New-NAVAddIn.md)

[Remove-NAVAddIn](Remove-NAVAddIn.md)

[Set-NAVAddIn](Set-NAVAddIn.md)
