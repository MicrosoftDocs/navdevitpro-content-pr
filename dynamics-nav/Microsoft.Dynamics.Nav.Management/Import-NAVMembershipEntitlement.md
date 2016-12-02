---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Import-NAVMembershipEntitlement

## SYNOPSIS
Imports the license entitlement data for a membership association.

## SYNTAX

```
Import-NAVMembershipEntitlement [-Path] <String> [[-Type] <String>] -Id <String> -Name <String>
 -EntitlementSetId <String> -EntitlementSetName <String> [-Evaluation] [-ServerInstance] <String> [-Force]
 [-WhatIf] [-Confirm]
```

## DESCRIPTION
Import license entitlement data for a membership association.

## EXAMPLES

### EXAMPLE 1
```
Import-NAVAzureADEntitlement -Path C:\License\ADPlanEntitlement.csv -Type 'Azure AD Plan' -Id '0000-0001' -Name 'My Service Plan' -EntitlementSetId 'MyPlanEntitlement' -EntitlementSetName 'Entitlements for My Service Plan' -ServerInstance 'DynamicsNAV'
```

This example imports an Azure AD entitlement of the type 'Azure AD Plan' to the entitlement set 'Entitlements for My Service Plan'.

## PARAMETERS

### -EntitlementSetId
Specifies the ID of the entitlement set in which to load the entitlements.

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

### -EntitlementSetName
Specifies the name of the entitlement set in which to load the entitlements.

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

### -Id
Specifies the ID of the membership.

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

### -Name
Specifies the name of the membership.

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

### -Path
Specifies the folder path and file name to the entitlement package file.
These files typically have a .csv extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.
Include the name in single-quotes.

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

### -Type
Specifies the membership type., such as  'Azure AD Plan' or 'Azure AD Role'.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
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

### -Evaluation
Specifies the entitlement to be for evaluation purposes, which means it has limited use and is not a paid entitlement. 

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
