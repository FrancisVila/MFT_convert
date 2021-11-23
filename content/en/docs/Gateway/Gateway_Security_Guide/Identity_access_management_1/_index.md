{
    "title": "Identity and access management",
    "linkTitle": "Identity and access management",
    "weight": "60"
}## The RBAC model

This product implements an RBAC model to manage identity and access control. This model is based on the concept that there are actually few roles within an organization, and instead of assigning access to each individual resource, the permission can be assigned to roles, and then those roles assigned to users. This process makes it much easier to manage permissions. It is not necessary to review the complete list of users each time a new resource is added, but only to review the list of roles. In the same way it is not necessary to review the complete list of resources each time a new user is added, but only to review the list of roles.

The following diagram illustrates an RBAC model.

![The RBAC model](/Images/Gateway/Identity_and_access_management_1.png)

The following describes how the RBAC model works:

-   A role is a list of permissions (or privileges).
-   A permission is the right to execute one or multiple actions on one resource.
-   When using a permission, it becomes an operation.
-   Roles can be grouped to create hierarchical roles.
-   Roles belong to an organization.
-   When assigning a role to a subject (or user), it is possible to create a User/Role constraint to limit the scope of the role for this subject.
-   To define these constraints, attributes can be associated with Resources.
-   When the subject starts using a role, a session is created. When creating the session, it is possible to limit the scope of the role for this particular session through a role activation constraint.

For example:

-   A resource is a file.
-   Actions on this resource are: Create, Read, Update, or Delete.
-   A permission (privilege) on this resource is Read File.
-   An attribute of this resource is Directory Name.
-   The User/Role constraint is `If directory name=XYZ`.
-   The role RRR is created including this permission.
-   The constraint is added when assigning this role to a subject (user).

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
