{
    "title": "Protocol level security",
    "linkTitle": "Protocol level security",
    "weight": "80"
}With Gateway, you can analyze the identity of Transfer partners during protocol connection to determine whether or not you want to authorize them to connect and exchange files. You have the option of using internal or external processes for this identity control.

Possible connection control methods that can be used in Gateway are:

-   CGate – internal processing; can be configured through user exit or directly in Gateway
-   SGate – internal processing configured only through user exit
-   Passport PM – external processing

## Internal processing: Using the CGate/SGate object

You can use the CGate/SGate object to link client access rights to connection authorization. You can define:

-   File visibility for groups or sub-groups of users
-   Access to portions of the VFD (Virtual File Directory) tree
-   File transfer rights for individual users
-   Filtering based on the port number and IP address of the caller

Note that, after passing the CGate/SGate control, the user can be authenticated a second time at remote site level (only available for physical remote sites)

CGate objects can be forced (selected) from user exit, using an external user access control database.

SGate objects are always forced (selected) from user exits.

## External processing: Using Passport PM

Connection control is made using partner information stored in Passport database.

## OFTP protocol

Additionally, the OFTP v2 protocol offers a protocol specific authentication using CMS signature/encryption

For more information refer to [Security features.](../ov_gw_security_features)

## HTTP protocol

HTTP server identification methods *CGI session id* and *CGI user password* are insecure by design and should not be used.

{{< Gateway/gatewayname  >}} offers several other identification methods, which should be used instead:

-   Web
-   Cookie session id
-   Cookie user password

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
