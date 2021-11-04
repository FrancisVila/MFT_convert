{
    "title": "User classes",
    "linkTitle": "User classes",
    "weight": "170"
}User classes define sets of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> users who share characteristics and privileges.

Use user classes to define the following access restrictions:

-   SSL encryption
-   Filesystem, upload and download
-   FTP command
-   Server
-   User limits

You might also define user classes to support the following <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> functions:

-   The *Server Usage Monitor* page reports usage information by user class.
-   On the *Setting* page, you define a FTP passive mode address rules for a user class.
-   On the *Command Logging* page, you enable logging for a user class.
-   On the *Transfer Logging* page, you enable logging for a user class.
-   When you create an LDAP domain, you can define a DN filter for a user class.
-   On the LDAP *Home Folders* page, you define the home folder prefix for a user class.
-   When you create an account template, you specify the user class <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> applies it to.
-   You define a user class named `EncryptClass` to enable repository encryption for users.

To determine the user class for a user, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> evaluates the criteria for each user class in the sequence and puts the user in the first class that matches.

User classes are defined by the following values:

-   **User type** – The user type can be *real*, *virtual*, or either
-   **User name** – The user’s login name
-   **User group** – The account group for the user
-   **From address** – The IP address or host name from which the user connects
-   **Custom expression** – An expression comprised of values of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user attributes and LDAP attributes as well as SSO attributes, constant values and patterns using arithmetic, comparison, string matching, logical, and conditional operations

You can use wildcard characters to define patterns in the **User name**, **User group**, and **From address** fields. Question mark (`?`) matches one character and asterisk (`*`) matches any string of characters.

Configure user classes on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server only.

The following topics describe and list the default user classes and custom expressions. The also provide how-to instructions for managing user classes.

-   <a href="c_st_default_user_classes" class="MCXref xref">Default user classes</a> - Describes and lists the default user classes.
-   <a href="c_st_custom_expressions" class="MCXref xref">Custom expressions</a> - Lists the user class custom expressions.
-   <a href="t_st_userclasses" class="MCXref xref">Manage user classes</a> - Provides how-to instructions for managing user classes.
