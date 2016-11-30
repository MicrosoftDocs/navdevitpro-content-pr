---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: 
schema: 2.0.0
---

# Import-NAVEncryptionKey

## SYNOPSIS
Imports an encryption key from a file to a Microsoft Dynamics NAV Server instance and database in SQL Server.

## SYNTAX

```
Import-NAVEncryptionKey [[-ServerInstance] <String>] -ApplicationDatabaseServer <String>
 [-ApplicationDatabaseCredentials <PSCredential>] -ApplicationDatabaseName <String> [-KeyPath] <String>
 [-Password <SecureString>] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
When using SQL Server authentication between the Microsoft Dynamics NAV Server instance and database in SQL Server,Microsoft Dynamics NAV encrypts passwords that are used by a Microsoft Dynamics NAV Server instance to access to Microsoft Dynamics NAV databases in SQL Server.
This includes, for example, the Microsoft Dynamics NAV Server service account credentials and the database credentials.
To encrypt and decrypt the passwords, an encryption key is used.
Microsoft Dynamics NAV uses a single encryption key per server instance.
The encryption key must be installed on the computer where Microsoft Dynamics NAV Server is installed and in the Microsoft Dynamics NAV database.
In some cases, such as when upgrading or migrating a system from one set of hardware to another, you might need a copy of the encryption key that is used on one Microsoft Dynamics NAV Server instance to use on another Microsoft Dynamics NAV Server instance.
By first using the Export-NAVEncryptionKey cmdlet to export the encryption key from one Microsoft Dynamics NAV Server instance to a file, you can then use the Import-NAVEncryptionKey to import the encryption key from the file to another Microsoft Dynamics NAV Server instance.
The Import-NAVEncryptionKey cmdlet enables you to specify a destination file for the encryption key and also specify a password that is used to protect the file, if any.
You cannot import an encryption key on the Microsoft Dynamics NAV Server instance if an encryption key file already exists.
You must first delete the encryption key from the computer where Microsoft Dynamics NAV Server is installed.
By default, encryption keys are stored in the C:\ProgramData\Microsoft\Microsoft Dynamics NAV\80\Server\Keys folder.

## EXAMPLES

### EXAMPLE 1
```
Import-NAVEncryptionKey -ServerInstance DynamicsNAV -KeyPath "C:\Keys\nav.key" - ApplicationDatabaseServer MyNavSQLServer\MyNAV -ApplicationDatabaseName MyNavDB -Password (Get-Credential).Password
```

Description

-----------

This example imports an encryption key from a password protected file that has the file path C:\Keys\nav.key to the Microsoft Dynamics NAV Server instance that is called DynamicsNAV.
The encryption key is imported to the MyNavDB database on the MyNavSQLServer\MyNAV server instance in SQL Server.

## PARAMETERS

### -ApplicationDatabaseCredentials
Specifies the user name and password of the login account to use to access the application database in SQL Server by using SQL Server authentication

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationDatabaseName
Specifies the name of the Microsoft Dynamics NAV database in SQL Server to which you want to import the encryption key.
In a multitenant deployment, this is the application database, which contains a list of mounted tenants.

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

### -ApplicationDatabaseServer
Specifies the SQL Server name and instance, such as MyServer\MyInstance, that hosts the Microsoft Dynamics NAV database in which you want to import the encryption key.
In a multitenant deployment, this is the application database, which contains a list of mounted tenants.

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

### -KeyPath
The full path to the file that contains the encryption key.
The full path includes the drive, folders and file name.

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

### -Password
Specifies a password that protects the encryption key file that are importing.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerInstance
Specifies the name of a Dynamics NAV Server instance, for example, DynamicsNAV or myinstance.
You can specify either the full name of an instance, such as MicrosoftDynamicsNavServer$myinstance or the short name such as myinstance.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### None

## NOTES
## RELATED LINKS

