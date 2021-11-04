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

<span class="mc-variable suite_variables.GatewayName variable">Gateway</span> offers several other identification methods, which should be used instead:

-   Web
-   Cookie session id
-   Cookie user password

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
