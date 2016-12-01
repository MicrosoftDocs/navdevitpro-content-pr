---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Import-NAVServerLicense

## SYNOPSIS
Imports a license file into a Microsoft Dynamics NAV database.

## SYNTAX

### LicenseFileSet (Default)
```
Import-NAVServerLicense [-Tenant <TenantId>] [-LicenseFile] <String> [-Database <LicenseDatabase>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

### LicenseDataSet
```
Import-NAVServerLicense [-LicenseData] <Byte[]> [-Tenant <TenantId>] [-Database <LicenseDatabase>]
 [-ServerInstance] <String> [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Import-NAVServerLicense cmdlet to import a license file into a Microsoft Dynamics NAV database.

If the Microsoft Dynamics NAV Server account specified does not have access to the location where the license file is stored, an error results. Check the Event Log on the Microsoft Dynamics NAV Server computer to see what permissions are required.

After importing a new license, restart all Microsoft Dynamics NAV Server instances to activate the license for client users.

## EXAMPLES

### EXAMPLE 1
```
Import-NAVServerLicense DynamicsNAV -LicenseData ([Byte[]]$(Get-Content -Path "fin.flf" -Encoding Byte))
```

This example imports a license file that is named "fin.flf" from the current directory into the default database.

### EXAMPLE 2
```
Import-NAVServerLicense MyInstance -LicenseData ([Byte[]]$(Get-Content -Path "fin.flf" -Encoding Byte)) -Database NavDatabase
```

This example imports a license file that is named "fin.flf" from the current directory into the local Microsoft Dynamics NAV database that is used by the MyInstance Microsoft Dynamics NAV Server instance.

### EXAMPLE 3
```
Import-NAVServerLicense 'MicrosoftDynamicsNavServer$MyInstance' -LicenseData ([Byte[]]$(Get-Content -Path "fin.flf" -Encoding Byte)) -Database Master
```

This example imports a license file that is named "fin.flf" from the current directory into the master database.

### EXAMPLE 4
```
Import-NAVServerLicense 'MicrosoftDynamicsNavServer$MyInstance' -LicenseData ([Byte[]]$(Get-Content -Path "fin.flf" -Encoding Byte)) -Database Tenant -Tenant Tenant1
```

This example imports a license file that is named "fin.flf" from the current directory into the database that is used by the specified tenant, Tenant1.

## PARAMETERS

### -Database
Specifies the database into which to import the license file.
The possible values are described in the following list:

Default = 0  
Default; overrides the license file currently in use.  

Master = 1  
Forces the license file to be global.

NavDatabase = 2  
Forces the license file to be local and stored in the Microsoft Dynamics NAV database that is used by the specified Microsoft Dynamics NAV Server instance.

Tenant = 3  
Forces the license file to be local and stored in the Microsoft Dynamics NAV database that is used by the tenant that is specified in the Tenant parameter.

```yaml
Type: LicenseDatabase
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseData
Specifies the content retrieved from the certificate file by using the Get-Content cmdlet. For more information, see the examples.

```yaml
Type: Byte[]
Parameter Sets: LicenseDataSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseFile
The LicenseFile parameter specifies the path to the Microsoft Dynamics NAV license file.

```yaml
Type: String
Parameter Sets: LicenseFileSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance. You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

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

### -Tenant
Specifies the ID of the tenant in which you want to import the license, such as Tenant1. This parameter is required unless the specified service instance is not configured to run multiple tenants.

```yaml
Type: TenantId
Parameter Sets: (All)
Aliases: Id

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

### System.String
You can pipe a string that contains a Microsoft Dynamics NAV Server instance name to the cmdlet.

## OUTPUTS

## NOTES
## RELATED LINKS
[Get-NAVServerLicenseInformation](Get-NAVServerLicenseInformation.md)
