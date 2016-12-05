---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version:
schema: 2.0.0
---

# Export-NAVData

## SYNOPSIS
Exports data from a Microsoft Dynamics NAV database.

## SYNTAX

### UseDatabase_SomeCompanies (Default)
```
Export-NAVData [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseServer <String>] [-ApplicationDatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseName <String>] -FilePath <String> [-Description <String>] [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-CompanyName <String[]>] [-Force]
```

### UseNST_AllCompanies
```
Export-NAVData [-ServerInstance] <String> [[-Tenant] <TenantId>] -FilePath <String> [-Description <String>]
 [-IncludeApplication] [-IncludeApplicationData] [-IncludeGlobalData] [-AllCompanies] [-Force]
```

### UseNST_SomeCompanies
```
Export-NAVData [-ServerInstance] <String> [[-Tenant] <TenantId>] -FilePath <String> [-Description <String>]
 [-IncludeApplication] [-IncludeApplicationData] [-IncludeGlobalData] [-CompanyName <String[]>] [-Force]
```

### UseDatabase_AllCompanies
```
Export-NAVData [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseServer <String>] [-ApplicationDatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseName <String>] -FilePath <String> [-Description <String>] [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-AllCompanies] [-Force]
```

### UseDatabase_NoCompanies
```
Export-NAVData [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseCredentials <PSCredential>] [-ApplicationDatabaseName <String>] -FilePath <String>
 [-Description <String>] [-IncludeApplication] [-IncludeApplicationData] [-IncludeGlobalData] [-Force]
```

## DESCRIPTION
Use the Export-NAVData cmdlet to export data from a Microsoft Dynamics NAV database.
You can export company-specific data, and you can choose to include global data, application data, and application objects.
When you export data from a Microsoft Dynamics NAV database, the data is stored in a file with the extension .navdata.
This file cannot be modified in external tools.
The data that you export is not deleted from the original database.
The cmdlet takes different parameter sets depending on how you connect to the database that you want to export data from.
You can access the database through the Microsoft Dynamics NAV Server instance, or you can access the database directly.
You can use the Export-NAVData cmdlet to transfer data between installations.
We recommend that you use SQL Server management tools to back up and restore databases.
To import data from a file, use the Import-NAVData cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Export-NAVData -DatabaseServer 'MyServer' -DatabaseName 'Demo Database NAV' -AllCompanies -FilePath C:\file\Companies.navdata
```

This example exports all companies from the specified database that is mounted against the specified Microsoft Dynamics NAV Server instance in a single-tenant deployment of Microsoft Dynamics NAV.

### EXAMPLE 2
```
Export-NAVData -ServerInstance DynamicsNAV -Tenant "Tenant1" -CompanyName "Company A, Company B" -FilePath C:\file\Companies.navdata -DatabaseCredentials (Get-Credential)
```

This example exports the two specified companies from the specified tenant database in a multitenant deployment of Microsoft Dynamics NAV.
The Microsoft Dynamics NAV Server instance is configured for SQL authentication with the database.

## PARAMETERS

### -AllCompanies
Specifies if you want to export all companies in the database to the specified file.

```yaml
Type: SwitchParameter
Parameter Sets: UseNST_AllCompanies, UseDatabase_AllCompanies
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseCredentials
Specifies the user name and password of an SQL Server Authentication login account that provides access to the application database in SQL Server.
You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter.
The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies, UseDatabase_NoCompanies
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseName
Specifies the name of the Microsoft Dynamics NAV database that contains the application tables in a multitenant deployment.
You must also set the ApplicationDatabaseServer parameter.
Even if you are not exporting data from the application database, you must specify this parameter.

```yaml
Type: String
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies, UseDatabase_NoCompanies
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database that contains the application tables is installed in a multitenant deployment.
Even if you are not exporting data from the application database, you must specify this parameter.

```yaml
Type: String
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CompanyName
Specifies the name of the company or the companies that you want to import.
If the company does not exist in the file, the operation fails.

```yaml
Type: String[]
Parameter Sets: UseDatabase_SomeCompanies, UseNST_SomeCompanies
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseCredentials
Specifies the user name and password for an SQL Server Authentication login account that provides access to the database or tenant database (in a multitenant deployment) in SQL Server.
You use this parameter to access the database by using SQL Server Authentication.
If you want to use Windows Authentication, then you can omit this parameter.
The login account must be a member of the db_owner role on the database.

```yaml
Type: PSCredential
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies, UseDatabase_NoCompanies
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseName
The name of the Microsoft Dynamics NAV database that contains the data that you want to export, such as 'Demo Database NAV'.
In a multitenant deployment, this is the name of the tenant database, and you must also specify the tenant ID in the Tenant parameter.

```yaml
Type: String
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies, UseDatabase_NoCompanies
Aliases: TenantDatabaseName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database is installed.

```yaml
Type: String
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies, UseDatabase_NoCompanies
Aliases: TenantDatabaseServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the data that you want to export, such as 'My Application Database'.

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

### -FilePath
Specifies the name and location of the file that you want to export data to.
The data is exported to a file with the extension .navdata.
If you use parameter sets that include -ServerInstance, the user account for the Microsoft Dynamics NAV Server instance must have write access to the location that is specified by the -FilePath parameter.
If you use parameter sets that include -DatabaseServer, you must have write access to the location that is specified by the -FilePath parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FileName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeApplication
Specifies that you want to include application objects in the export.
If you do not set the parameter, application objects are not included in the export.

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

### -IncludeApplicationData
Specifies that you want to include application data in the export.
If you do not set the parameter, application data is not included in the export.

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

### -IncludeGlobalData
Specifies that you want to include global data in the export.
If you do not set the parameter, global data is not included in the export.

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

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: UseNST_AllCompanies, UseNST_SomeCompanies
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies the ID of the tenant that the company is imported into, such as Tenant1.
This parameter is required in multitenant deployments of Microsoft Dynamics NAV.

```yaml
Type: TenantId
Parameter Sets: UseNST_AllCompanies, UseNST_SomeCompanies
Aliases: Id

Required: False
Position: 2
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
[Import-NAVData](Import-NAVData.md)
