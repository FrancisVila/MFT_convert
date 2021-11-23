{
    "title": "Predefined default roles",
    "linkTitle": "Predefined default roles",
    "weight": "90"
}## Predefined default roles

The following is a list of predefined roles in Gateway.

-   Admin
    -   Enables access to all the resources. Should be assigned to a system administrator which should have access to the system’s resources and architecture.
    -   Can create other user profiles in accordance with specific requirements.
    -   Should be employed using all security best practices to include but not limited to: strong passwords, not used for current application activity but only for product management, along with audit trails and proper ACL employment.
    -   Using the Admin *default* role should be restricted as much as possible. In many cases, administrative tasks can be delegated to user roles with specific access rights to individual {{< Gateway/gatewayname >}} resources.
-   Access all transfers
-   Anonymous
    -   This user can connect with no credentials and has access to all resources.
    -   It is meant to be an initial setup user and it should not be allowed to function after initial setup as it presents a great security risk in a production environment.
-   Customizable User
    -   General user which should be custom tailored to accommodate the need to perform certain actions by certain users. These can be clustered in common user profiles but for audit purposes a finer grained access control should be employed through an individual basis.

Through Gateway’s user profile management, a fine grained access control can be implemented and thus numerous types of users and user-profiles can be created and managed, given a variety of access privileges to the application’s resources.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
