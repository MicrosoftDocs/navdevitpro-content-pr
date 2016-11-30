---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Import-NAVData

## SYNOPSIS
Imports data from a file that has been exported from a Microsoft Dynamics NAV database.

## SYNTAX

### UseDatabase_SomeCompanies (Default)
```
Import-NAVData [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseServer <String>] [-ApplicationDatabaseName <String>]
 [-ApplicationDatabaseCredentials <PSCredential>] [-FilePath] <String> [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-CompanyName <String[]>] [-CommitPerTable] [-Force] [-WhatIf]
 [-Confirm]
```

### UseNST_AllCompanies
```
Import-NAVData [-ServerInstance] <String> [[-Tenant] <TenantId>] [-FilePath] <String> [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-AllCompanies] [-CommitPerTable] [-Force] [-WhatIf] [-Confirm]
```

### UseNST_SomeCompanies
```
Import-NAVData [-ServerInstance] <String> [[-Tenant] <TenantId>] [-FilePath] <String> [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-CompanyName <String[]>] [-CommitPerTable] [-Force] [-WhatIf]
 [-Confirm]
```

### UseDatabase_AllCompanies
```
Import-NAVData [-DatabaseServer <String>] [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseServer <String>] [-ApplicationDatabaseName <String>]
 [-ApplicationDatabaseCredentials <PSCredential>] [-FilePath] <String> [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-AllCompanies] [-CommitPerTable] [-Force] [-WhatIf] [-Confirm]
```

### UseDatabase_NoCompanies
```
Import-NAVData [-DatabaseName <String>] [-DatabaseCredentials <PSCredential>]
 [-ApplicationDatabaseServer <String>] [-ApplicationDatabaseName <String>]
 [-ApplicationDatabaseCredentials <PSCredential>] [-FilePath] <String> [-IncludeApplication]
 [-IncludeApplicationData] [-IncludeGlobalData] [-CommitPerTable] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the Import-NAVData cmdlet to import data into a Microsoft Dynamics NAV database from a file.
You can choose to import all data in the file, and you can choose to import only company-specific data, global data, application data, or application objects.
You can use the Import-NAVData cmdlet in a classic single-tenant deployment of Microsoft Dynamics NAV, and you can use it in multitenant deployments.
You can only import an application into an empty database.
If you import application data but not the application, you cannot access the database from Microsoft Dynamics NAV.
Similarly, if you import global data into a database that does not contain a company, you cannot open Microsoft Dynamics NAV.
Also, we recommend that you do not import an application into a database that users are accessing.
A new application often defines a new database schema that changes the structure of the business data.
The cmdlet takes different parameter sets depending on how you connect to the database that you want to import data into.
You can access the database through the Microsoft Dynamics NAV Server instance, or you can access the database directly.
You can use the Import-NAVData cmdlet to transfer data between installations.
We recommend that you use SQL Server management tools to back up and restore databases.
To export data to a file, use the Export-NAVData cmdlet.

## EXAMPLES

### EXAMPLE 1
```
Import-NAVData -ServerInstance DynamicsNAV -CompanyName "CRONUS International Ltd.", "My Company" -IncludeGlobalData -FilePath C:\file\CompaniesAndGlobalData.navdata
```

Description

-----------

This example imports the two named companies into the database that is mounted against the specified Microsoft Dynamics NAV Server instance in a single-tenant deployment of Microsoft Dynamics NAV.

### EXAMPLE 2
```
Import-NAVData -DatabaseServer 'MyServer' -DatabaseName 'Tenant 1 Database' -ApplicationDatabaseServer 'MyServer' -ApplicationDatabase 'NAV App' -CompanyName "CRONUS International Ltd." -FilePath C:\file\Company.navdata
```

Description

-----------

This example imports a named company into the specified tenant database that uses the specified application database in a multitenant deployment of Microsoft Dynamics NAV.

### EXAMPLE 3
```
Import-NAVData -DatabaseServer 'MyServer' -DatabaseName 'Tenant 1 Database' DatabaseCredentials (Get-Credential)-ApplicationDatabaseServer 'MyServer' -ApplicationDatabase 'NAV App' -CompanyName "CRONUS International Ltd." ApplicationDatabaseCredentials (Get-Credential) -FilePath C:\file\Company.navdata
```

Description

-----------

This example imports the named into the specified tenant database that uses the specified application database in a multitenant deployment of Microsoft Dynamics NAV.
The example configures SQL Server Authentication on the nav_server instance for accessing the tenant and application databases.

## PARAMETERS

### -AllCompanies
Specifies if you want to import all companies from the specified file.

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
Specifies the user name and password of an SQL Server Authentication login account that provides access to the Microsoft Dynamics NAV application database in SQL Server.
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
Specifies the name of the Microsoft Dynamics NAV database that contains the application tables in the multitenant deployment.
Even if you are not importing application data to the application database, you must specify this parameter in a multitenant deployment.

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
Specifies the name of the computer on which the SQL Server instance for the Microsoft Dynamics NAV database that contains the application tables is installed in the multitenant deployment.
Even if you are not importing application data to the application database, you must specify this parameter in a multitenant deployment.

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

### -CommitPerTable
Specifies the data changes are committed per table.

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
Specifies the name of the Microsoft Dynamics NAV database, such as 'Demo Database NAV (8-0)', into which you want to import the data from the file.
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
Parameter Sets: UseDatabase_SomeCompanies, UseDatabase_AllCompanies
Aliases: TenantDatabaseServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the name and location of the file that you want to import data from.
The file must be a .navdata file that has been exported from Microsoft Dynamics NAV.
If you use parameter sets that include -ServerInstance, the user account for the Microsoft Dynamics NAV Server instance must have read access to the location that is specified by the -FilePath parameter.
If you use parameter sets that include -DatabaseServer, you must have read access to the location that is specified by the -FilePath parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: FileName

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeApplication
Specifies that you want to include application objects in the import.
If you do not set the parameter, application objects are not included in the import.
You can only import an application into an empty database.
You can only set this parameter when you access the Microsoft Dynamics NAV database directly through the DatabaseServer and DatabaseName parameters.

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
Specifies that you want to include application data in the import.
If you do not set the parameter, application data is not included in the import.
Application data is tables that describe the application as opposed to being business data.

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
Specifies that you want to include global, non-company specific data in the import.
If you do not set the parameter, global data is not included in the import.

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
This parameter is required unless the specified service instance is not configured to run multiple tenants.

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

