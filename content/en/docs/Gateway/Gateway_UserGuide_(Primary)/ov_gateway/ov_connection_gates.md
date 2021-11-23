{
    "title": "Connection Gates",
    "linkTitle": "Connection Gates",
    "weight": "100"
}{{< Gateway/componentlongname  >}}: Overview

For security reasons, when a remote machine makes an attempt to connect to your local machine, you need to control whether or not to allow the connection. Gateway uses a combination of two different objects to filter connection attempts at the protocol level:

-   Connection Gate Groups (CGateGroups)
-   Connection Gates (CGates)

For a given connection attempt, Gateway scans the properties listed in CGateGroups and CGates to determine whether or not the remote partner is allowed to connect.

CGates and CGateGroups are only useful when Gateway is operating in *server mode*.

## CGateGroups

A CGateGroup can contain other CGateGroups or CGates. The CGates contained in a CGateGroup share the properties of that CGateGroup.

When you create a CGateGroup, you give the group a name and specify the protocol or protocols that connecting machines can use to connect to Gateway. You must also enter a value for the called SAP (either a specific value or the universal variable '`*`').

Additionally, you may require other filtering criteria at the group level, such as an HTTP hostname. You may choose to specify directory access rights for HTTP and/or FTP connections for the CGateGroup.

## CGates

Use CGates to:

-   Activate and deactivate individual protocol CGates
-   Associate IDs and passwords with protocol connection procedures - you can allow users to modify their own passwords
-   Link TLS security functions to the connection
-   Create remotely-accessible file directories and manage directory access rights for connected users (HTTP and/or FTP, SFTP)
-   Specify a home page (HTTP only)
-   Set upload limits (FTP / SFTP only)
-   Exclude connections from specified calling addresses (TCP/IP supported protocols only)

## SGates and SGateGroups

Gateway now supports the use of *Super CGates* (SGates) that offer a higher capacity than the standard CGates.

[Next topic](../ov_diffusion_lists)

Related topics

[About CGates and CGateGroups](../../managing_partners_start_here/cgates_start_here)

[About SGates](../../managing_partners_start_here/cgates_start_here/sgates_about)

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
