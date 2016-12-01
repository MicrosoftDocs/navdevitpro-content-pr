---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Get-NAVCompany

## SYNOPSIS
Gets a list of the Microsoft Dynamics NAV companies in the specified tenant database.

## SYNTAX

### NavServerSet (Default)
```
Get-NAVCompany [-ServerInstance] <String> [[-Tenant] <TenantId>] [-Force]
```

### FileSet
```
Get-NAVCompany -FilePath <String> [-Force]
```

## DESCRIPTION
Use the Get-NAVCompany cmdlet to extract a list of companies in the specified database.
In the Microsoft Dynamics NAV 2016 Administration Shell, you can create, rename, and remove companies by using the New-NAVCompany, Rename-NAVCompany, and Remove-NAVCompany cmdlets.
The following information is returned for each company:
Company name, Evaluation Company

## EXAMPLES

### EXAMPLE 1
```
Get-NAVCompany -ServerInstance DynamicsNAV -Tenant CRONUS
```

This example shows a list of companies in the tenant database that has the tenant ID CRONUS and which is mounted against the DynamicsNAV server instance.

### EXAMPLE 2
```
Get-NAVCompany -FilePath c:\file\my-exported.navdata
```

This example shows a list of companies that are contained in the my-exported.navdata file that is located in the c:\file folder.

## PARAMETERS

### -FilePath
Specifies the path and name of the exported file that you want to get the company information from.

```yaml
Type: String
Parameter Sets: FileSet
Aliases: FileName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: NavServerSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that the company is stored in, such as Tenant1.
This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: NavServerSet
Aliases: Id

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### System.string
You can pipe the value of the ServerInstance parameter as a string to this cmdlet.

## OUTPUTS

### System.Data.DataRow
Returns the company information as a data row for each company.

## NOTES
## RELATED LINKS
[Copy-NAVCompany](Copy-NAVCompany.md)  

[New-NAVCompany](New-NAVCompany.md)  

[Remove-NAVCompany](Remove-NAVCompany.md)
