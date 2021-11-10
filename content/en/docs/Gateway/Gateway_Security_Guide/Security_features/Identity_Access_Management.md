{
    "title": "Identity and Access Management",
    "linkTitle": "Identity and Access Management",
    "weight": "150"
}## Identity and Access Management

Identity and Access Management can either be performed internally in the product or using PassPort AM.

### PassPort AM

The following PassPort AM features are available:

-   An RBAC (Role Base Access Control) is used.
-   The users and associated passwords can be stored in either a PassPort database, or retrieved from an LDAP directory or from Active Directory. Also, they can be retrieved from any other third-party product, but some code must be written to access these users.
-   An SSO option is available. PassPort includes a reverse proxy and a token manager to provide an SSO option only for Axway products.

See the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> documentation for a complete list of features in this product.

### When not using PassPort

The following features are available:

-   An RBAC (Role Base Access Control) is used. Roles are defined through “Profile” objects and stored in Gateway object database.
-   Each defined user have a profile assigned which controls actions that the user is allowed to execute on the different Gateway resources according to its role.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
