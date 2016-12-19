---
Module Name: Microsoft.Dynamics.Nav.Apps.Management
Module Guid: 1405f736-a2d8-455e-b296-f66594a2fc1e
Download Help Link:
Help Version: 1.0.0.0
Locale: en-US
---

# Microsoft.Dynamics.Nav.Apps.Management Module
## Description
The [!INCLUDE[nav_shell_md](../includes/nav_shell_md.md)] includes cmdlets for administering extension packages in the [!INCLUDE[navnow_md](../includes/navnow_md.md)]. These cmdlets are included in the Microsoft.Dynamics.Nav.Apps.Management module that is installed as part of the [!INCLUDE[nav_shell_md](../includes/nav_shell_md.md)] when you install the [!INCLUDE[nav_server_md](../includes/nav_server_md.md)].

>[!NOTE]
>Also included in the [!INCLUDE[nav_shell_md](../includes/nav_shell_md.md)] are cmdlets for administering the [!INCLUDE[navnow_md](../includes/navnow_md.md)] deployment, such as adding and configuring [!INCLUDE[nav_server_md](../includes/nav_server_md.md)] instances, databases, and users. For more information about these cmdlets, see [Microsoft.Dynamics.Nav.Management](../Microsoft.Dynamics.Nav.Management/Microsoft.Dynamics.Nav.Management.md).

## Microsoft.Dynamics.Nav.Apps.Management Cmdlets
### [Get-NAVAppInfo](Get-NAVAppInfo.md)
Gets information about an NAV App based on the specified package file or the specified Dynamics NAV Server instance.

### [Get-NAVAppTableModification](Get-NAVAppTableModification.md)
Gets information about the tabled added or modified by an Extension based on the specified Dynamics NAV Server instance.

### [Get-NAVAppTenant](Get-NAVAppTenant.md)
Gets the tenants where the specified NAV App is installed.

<!--### [Get-NAVTableSynchSetupForDataUpgrade](Get-NAVTableSynchSetupForDataUpgrade.md)
Gets information about the tables that will be modified, added, or removed during a tenant data upgrade on the specified Microsoft Dynamics NAV Server instance for the specified tenant.-->

### [Install-NAVApp](Install-NAVApp.md)
Installs a published NAV App for a tenant.

### [Publish-NAVApp](Publish-NAVApp.md)
Publishes an Extension to the app catalog of the specified Dynamics NAV Server instance.

### [Remove-NAVAppsForTenant](Remove-NAVAppsForTenant.md)
Removes all NAV Apps from the specified, unmounted tenant.

### [Repair-NAVApp](Repair-NAVApp.md)
Repairs a NAV App by recompiling it against the current base application.

### [Uninstall-NAVApp](Uninstall-NAVApp.md)
Uninstall a NAV App for a tenant.

### [Unpublish-NAVApp](Unpublish-NAVApp.md)
Unpublishes a NAV App from the app catalog of the specified Dynamics NAV Server instance.
