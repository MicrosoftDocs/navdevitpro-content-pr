---
external help file: Microsoft.Dynamics.Nav.Management.dll-Help.xml
online version: https://go.microsoft.com/fwlink/?linkid=521780
schema: 2.0.0
---

# New-NAVEncryptionKey

## SYNOPSIS
Create an encryption key and stores it in a file in a specified path on the computer or network.

## SYNTAX

```
New-NAVEncryptionKey [-KeyPath] <String> [-Password <SecureString>] [-Force] [-WhatIf] [-Confirm]
```

## DESCRIPTION
When using SQL Server authentication between the Microsoft Dynamics NAV Server instance and database in SQL Server, Microsoft Dynamics NAV encrypts passwords that are used by a Microsoft Dynamics NAV Server instance to access to Microsoft Dynamics NAV databases in SQL Server.
This includes, for example, the Microsoft Dynamics NAV Server service account credentials and the database credentials.
To encrypt and decrypt the passwords, an encryption key is used.
Microsoft Dynamics NAV uses a single encryption key per server instance.
In some cases, such as when upgrading or migrating a system from one set of hardware to another, you might need to copy of the encryption key to use it on another Microsoft Dynamics NAV Server instance.
By using the New-NAVEncryptionKey cmdlet, you can create an encryption key, and then use the Import-NAVEncryptionKey cmdlet to import the exported key to a Microsoft Dynamics NAV Server instance and database.
The New-NAVEncryptionKey cmdlet enables you to specify a destination file for the key and specify a password to protect the file.

## EXAMPLES

### EXAMPLE 1
```
Export-NAVEncryptionKey -ServerInstance DynamicsNAV -KeyPath "C:\Keys\nav.key" -Password (Get-Credential).Password
```

Description

-----------

The following example creates an encryption key in a password protected file.

## PARAMETERS

### -KeyPath
Specifies the full path of the key will be exported.
The full path includes the drive, folders, and file name.
The folder path must already exist.
The file will be created that has the given file name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Password
Specifies a password that protects the encryption key file.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String KeyPath

## NOTES
## RELATED LINKS
