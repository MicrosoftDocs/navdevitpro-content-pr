---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# New-NAVDatabase

## SYNOPSIS
Creates a new Microsoft Dynamics NAV database from a backup file.

## SYNTAX

### MultipleDestinations (Default)
```
New-NAVDatabase [-DatabaseServer <DatabaseServer>] [-DatabaseInstance <DatabaseInstance>]
 -DatabaseName <DatabaseName> [-ServiceAccount <String>] [-Timeout <Int32>] [-FilePath] <String>
 [-DataFilesDestinationPath <String>] [-LogFilesDestinationPath <String>] [-Force] [-WhatIf] [-Confirm]
```

### SingleDestination
```
New-NAVDatabase [-DatabaseServer <DatabaseServer>] [-DatabaseInstance <DatabaseInstance>]
 -DatabaseName <DatabaseName> [-ServiceAccount <String>] [-Timeout <Int32>] [-FilePath] <String>
 [-DestinationPath <String>] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
Use the New-NAVDatabase cmdlet to restore a database from a backup file.
You can specify the location of transaction log files and data files, but they must be located on the same computer as SQL Server.
You can use this cmdlet to restore a database to a remote SQL Server instance.

## EXAMPLES

### EXAMPLE 1
```
New-NavDatabase C:\Backups\backup1.bak -DatabaseName NewDatabase -Verbose | fl

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Restoring database 'NewDatabase' from backup file: 'C:\Backups\backup1.bak'...
VERBOSE: Restore of database 'NewDatabase' from file 'C:\Backups\backup1.bak' has been completed successfully.

DatabaseName     : NewDatabase
DatabaseInstance : MSSQLSERVER
DatabaseServer   : server1.cronus.com
VERBOSE: NavCommand.EndProcessing
```

Description

-----------

This example restores a database and preserves the original file names and locations.

### EXAMPLE 2
```
New-NAVDatabase C:\Backups\backup.bak -DestinationPath c:\newdestination -DatabaseName NewDatabase -Verbose

VERBOSE: NavCommand.BeginProcessing
VERBOSE: NavCommand.ProcessRecord
VERBOSE: Restoring database 'NewDatabase' from backup file: 'C:\Backups\backup.bak'...
VERBOSE: Restore of database 'NewDatabase' from file 'C:\Backups\backup.bak' has been completed successfully.

DatabaseName                            DatabaseInstance                        DatabaseServer
------------                            ----------------                        --------------
NewDatabase                             MSSQLSERVER                             server1.cronus.com
VERBOSE: NavCommand.EndProcessing
```

Description

-----------

This example restores a database, moves transaction log files and data files to the new location 'C:\newdestination', and preserves the original file names.

## PARAMETERS

### -DatabaseInstance
Specifies the name of the SQL Server instance that the database is restored to.

```yaml
Type: DatabaseInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseName
Specifies the name that you want to use for the restored database.

```yaml
Type: DatabaseName
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DatabaseServer
Specifies the name of the computer that is running SQL Server.

```yaml
Type: DatabaseServer
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DataFilesDestinationPath
Specifies the destination path for the data files for the restored database.
The path can be a UNC path or a path on the local computer.
You can specify either a directory path or a file path.
If you specify a directory path, then the location for data files is changed but the original file names are preserved.
If you specify a file path, then both the location and the file name of the data file is changed.
You can specify a file path only if the database that you restore contains a single data file.
If you specify a file path and the database contains multiple data files, then the restore operation fails.
If you do not specify the following parameters, then the database files are restored to their original locations: DestinationPath, DataFilesDestinationPath, LogFilesDestinationPath
If you specify the local computer for the DatabaseServer parameter, then if the directory that you specify does not exist, it is created automatically.

```yaml
Type: String
Parameter Sets: MultipleDestinations
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DestinationPath
Specifies the destination path for both data files and transaction log files for the restored database.
The path can be a UNC path or a path on the local computer.
You must specify a directory path.
If you specify a file path, then the restore operation fails.
If you do not specify the following parameters, then the database files are restored to their original locations: DestinationPath, DataFilesDestinationPath, LogFilesDestinationPath.
If you specify the local computer for the DatabaseServer parameter, then if the directory that you specify does not exist, it is created automatically.

```yaml
Type: String
Parameter Sets: SingleDestination
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FilePath
Specifies the path to the database backup file.
The backup file must be located on the same computer as SQL Server.

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

### -LogFilesDestinationPath
Specifies the destination path for transaction log files of the restored database.
The path can be a UNC path or a path on the local computer.
You can specify either a directory path or a file path
If you specify a directory path, then the location for transaction log files is changed but the original file names are preserved.
If you specify a file path, then both the location and the file name of the transaction log file are changed.
You can specify a file path only if the database that you restore contains a single transaction log file.
If you specify a file path and the database contains multiple transaction log files, then the restore operation fails.
If you do not specify the following parameters, then the database files are restored to their original locations: DestinationPath, DataFilesDestinationPath, LogFilesDestinationPath.
If you specify the local computer for the DatabaseServer parameter, then if the directory that you specify does not exist, it is created automatically.

```yaml
Type: String
Parameter Sets: MultipleDestinations
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServiceAccount
Specifies the logon account that runs the Microsoft Dynamics NAV Server instance.
This account is given the appropriate permissions to the database when you run the cmdlet.
For more information, see "Provisioning the Microsoft Dynamics NAV Server Account" in the MSDN Library at http://go.microsoft.com/fwlink/?LinkID=281888.

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

### -Timeout
The time (in seconds) to wait before terminating an attempt to execute a command on SQL Server, such as reading content or restoring the database from a .bak file.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### MDF and LDF

## NOTES
## RELATED LINKS

