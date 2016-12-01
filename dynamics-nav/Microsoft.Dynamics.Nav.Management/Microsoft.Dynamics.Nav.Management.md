---
Module Name: Microsoft.Dynamics.Nav.Management
Module Guid: 00000000-0000-0000-0000-000000000000
Download Help Link:
Help Version: 1.0.0.0
Locale: en-US
---

# Microsoft.Dynamics.Nav.Management Module
## Description
The [!INCLUDE[nav_shell_md](../includes/nav_shell_md.md)] includes cmdlets for administering the Dynamics NAV deployment, such as adding and configuring [!INCLUDE[nav_server_md](../includes/nav_server_md.md)]  instances, databases, and users. These cmdlets are included in the Microsoft.Dynamics.Nav.Management module that is installed as part of the [!INCLUDE[nav_shell_md](../includes/nav_shell_md.md)] when you install the [!INCLUDE[nav_server_md](../includes/nav_server_md.md)].

>[!NOTE]
>Also included in the Dynamics NAV Administration Shell are cmdlets for administering extension packages. For more information about these cmdlets, see [Microsoft.Dynamics.Nav.Apps.Management](../Microsoft.Dynamics.Nav.Apps.Management/Microsoft.Dynamics.Nav.Apps.Management.md).


## Microsoft.Dynamics.Nav.Management Cmdlets
### [Copy-NAVCompany](Copy-NAVCompany.md)
Creates a new company and copies all data from an existing company in the same tenant database.

### [Dismount-NAVTenant](Dismount-NAVTenant.md)
Dismounts a tenant on the specified Dynamics NAV Server instance.

### [Export-NAVApplication](Export-NAVApplication.md)
Extracts the application tables in a Microsoft Dynamics NAV database to a separate database.

### [Export-NAVData](Export-NAVData.md)
Exports data from a Dynamics NAV database.

### [Export-NAVEncryptionKey](Export-NAVEncryptionKey.md)
Exports the encryption key to a file in a specified path on the computer or network.

### [Export-NAVServerLicenseInformation](Export-NAVServerLicenseInformation.md)
Exports license information from the Dynamics NAV database.

### [Get-NAVAddIn](Get-NAVAddIn.md)
Returns information about add-ins that are registered in the table 2000000069 Add-ins of the  Dynamics NAV database.

### [Get-NAVApplication](Get-NAVApplication.md)
{Gets information about the application database that is mounted against the specified Dynamics NAV Server instance.

### [Get-NAVCompany](Get-NAVCompany.md)
Gets a list of the Dynamics NAV companies in the specified tenant database.

### [Get-NAVDataFile](Get-NAVDataFile.md)
Gets information from a Dynamics NAV data file.

### [Get-NAVDataUpgrade](Get-NAVDataUpgrade.md)
Gets information about a data upgrade process that is currently running, or the last completed data upgrade process.

### [Get-NAVServerAppConfiguration](Get-NAVServerAppConfiguration.md)
Gets the settings in an application-specific configuration file of a Dynamics NAV Server instance.

### [Get-NAVServerConfiguration](Get-NAVServerConfiguration.md)
Gets configuration settings for the specified Dynamics NAV Server instance.

### [Get-NAVServerInstance](Get-NAVServerInstance.md)
Gets service details for the specified Dynamics NAV Server instance.

### [Get-NAVServerPermission](Get-NAVServerPermission.md)
Gets information about the permissions that are applied to Dynamics NAV objects for the specified Dynamics NAV Server instance.

### [Get-NAVServerPermissionSet](Get-NAVServerPermissionSet.md)
Gets a list of permission sets for the specified Dynamics NAV Server instance.

### [Get-NAVServerSession](Get-NAVServerSession.md)
Gets information about active sessions for a Microsoft Dynamics NAV Server instance.

### [Get-NAVServerUser](Get-NAVServerUser.md)
Gets information about all users created in the current Microsoft Dynamics NAV database.

### [Get-NAVServerUserPermissionSet](Get-NAVServerUserPermissionSet.md)
Gets permission set information for Dynamics NAV users.

### [Get-NAVTableConnection](Get-NAVTableConnection.md)
Gets a list of connections to external database tables from a Dynamics NAV application.

### [Get-NAVTenant](Get-NAVTenant.md)
Gets the tenants that are mounted against the specified Dynamics NAV Server instance.

### [Get-NAVWebServerInstance](Get-NAVWebServerInstance.md)
Gets the information about the Dynamics NAV Web Server instances that are registered on a computer.

### [Get-NAVWebService](Get-NAVWebService.md)
Gets a list of all web services that are created in the application on the specified Dynamics NAV Server instance.

### [Import-NAVConfigurationPackageFile](Import-NAVConfigurationPackageFile.md)
Imports a configuration package file into the Dynamics NAV application database.

### [Import-NAVData](Import-NAVData.md)
Imports data from a file that has been exported from a Dynamics NAV database.

### [Import-NAVEncryptionKey](Import-NAVEncryptionKey.md)
Imports an encryption key from a file to a Dynamics NAV Server instance and database in SQL Server.

### [Import-NAVMembershipEntitlement](Import-NAVMembershipEntitlement.md)
Imports the license entitlement data for a membership association.

### [Import-NAVServerLicense](Import-NAVServerLicense.md)
Imports a license file into a Microsoft Dynamics NAV database.

### [Invoke-NAVCodeunit](Invoke-NAVCodeunit.md)
Invokes the specified codeunit with the specified parameters.

### [Mount-NAVApplication](Mount-NAVApplication.md)
Mounts the Dynamics NAV application against the specified server instance.

### [Mount-NAVTenant](Mount-NAVTenant.md)
Mounts a tenant database against the specified Dynamics NAV Server instance.

### [New-NAVAddIn](New-NAVAddIn.md)
Registers an add-in the system table 2000000069 Add-ins of the Dynamics NAV database.

### [New-NAVCompany](New-NAVCompany.md)
Creates a new Dynamics NAV company in the specified database.

### [New-NAVDatabase](New-NAVDatabase.md)
Creates a new Dynamics NAV database from a backup file.

### [New-NAVEncryptionKey](New-NAVEncryptionKey.md)
Create an encryption key and stores it in a file in a specified path on the computer or network.

### [New-NAVServerAppConfiguration](New-NAVServerAppConfiguration.md)
Creates a new application-specific configuration file for the Dynamics NAV Server instance.

### [New-NAVServerConfiguration](New-NAVServerConfiguration.md)
Creates a new configuration with default values, or to replace the existing configuration for a Dynamics NAV Server instance.

### [New-NAVServerInstance](New-NAVServerInstance.md)
Creates a new Dynamics NAV Server instance.

### [New-NAVServerPermission](New-NAVServerPermission.md)
Adds a new permission to a permission set.

### [New-NAVServerPermissionSet](New-NAVServerPermissionSet.md)
Creates a new permission set.

### [New-NAVServerUser](New-NAVServerUser.md)
Creates a new Dynamics NAV user.

### [New-NAVServerUserPermissionSet](New-NAVServerUserPermissionSet.md)
Assigns a permission set to a Dynamics NAV user.

### [New-NAVTableConnection](New-NAVTableConnection.md)
Registers a connection to an external database table so the table can be used by the Dynamics NAV application.

### [New-NAVWebServerInstance](New-NAVWebServerInstance.md)
Creates a new Dynamics NAV Web Server instance and binds this instance to a Dynamics NAV Server instance.

### [New-NAVWebService](New-NAVWebService.md)
Creates a new Dynamics NAV web service.

### [Remove-NAVAddIn](Remove-NAVAddIn.md)
Removes an add-in that is registered in the system table 2000000069 Add-ins of the Dynamics NAV database.

### [Remove-NAVApplication](Remove-NAVApplication.md)
Removes the tables that define the application from a Dynamics NAV database.

### [Remove-NAVCompany](Remove-NAVCompany.md)
Removes a company from a Dynamics NAV database.

### [Remove-NAVConfigurationPackageFile](Remove-NAVConfigurationPackageFile.md)
Removes a configuration package file from the Dynamics NAV app database.

### [Remove-NAVServerInstance](Remove-NAVServerInstance.md)
Removes a Dynamics NAV Server instance.

### [Remove-NAVServerPermission](Remove-NAVServerPermission.md)
Removes a permission from a permission set.

### [Remove-NAVServerPermissionSet](Remove-NAVServerPermissionSet.md)
Removes a Dynamics NAV permission set.

### [Remove-NAVServerSession](Remove-NAVServerSession.md)
Closes the specified client connection to a Dynamics NAV Server instance.

### [Remove-NAVServerUser](Remove-NAVServerUser.md)
Deletes a Microsoft Dynamics NAV user.

### [Remove-NAVServerUserPermissionSet](Remove-NAVServerUserPermissionSet.md)
Removes a permission set from the list of permission sets that are assigned to a Dynamics NAV user.

### [Remove-NAVTableConnection](Remove-NAVTableConnection.md)
Removes a connection to an external database table from the Dynamics NAV application.

### [Remove-NAVWebServerInstance](Remove-NAVWebServerInstance.md)
Removes an existing Dynamics NAV Web Server instance.

### [Remove-NAVWebService](Remove-NAVWebService.md)
Removes the specified web services from the application that is mounted against the specified  Dynamics NAV Server instance.

### [Rename-NAVCompany](Rename-NAVCompany.md)
Renames a company in a Dynamics NAV database.

### [Resume-NAVDataUpgrade](Resume-NAVDataUpgrade.md)
Resumes a suspended data upgrade process.

### [Set-NAVAddIn](Set-NAVAddIn.md)
Specifies the description, category, resource or resourcefile of an add-in that is registered in the system table 2000000069 Add-ins of the Dynamics NAV database.

### [Set-NAVServerAppConfiguration](Set-NAVServerAppConfiguration.md)
Specifies a setting in an application-specific configuration file for a Dynamics NAV Server instance.

### [Set-NAVServerConfiguration](Set-NAVServerConfiguration.md)
Specifies settings for a Dynamics NAV Server instance.

### [Set-NAVServerInstance](Set-NAVServerInstance.md)
Specifies the service state of a Dynamics NAV Server instance.

### [Set-NAVServerPermission](Set-NAVServerPermission.md)
Specifies the values for an existing permission set.

### [Set-NAVServerPermissionSet](Set-NAVServerPermissionSet.md)
Specifies a new name for a Dynamics NAV permission set.

### [Set-NAVServerUser](Set-NAVServerUser.md)
Specifies configuration settings of an existing Dynamics NAV user.

### [Set-NAVWebServerInstanceConfiguration](Set-NAVWebServerInstanceConfiguration.md)
Specifies configuration values for a named web server instance.

### [Start-NAVDataUpgrade](Start-NAVDataUpgrade.md)
Starts the process for upgrading the data in the tenant database.

### [Stop-NAVDataUpgrade](Stop-NAVDataUpgrade.md)
Stops the data upgrade process that is currently running or suspended.

### [Sync-NAVTenant](Sync-NAVTenant.md)
Synchronizes a tenant database schema with an application database.

### [Update-NAVScheduledTaskList](Update-NAVScheduledTaskList.md)
Updates the application-wide list of scheduled tasks with the information from the tenant database.
