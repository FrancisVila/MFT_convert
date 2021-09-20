{
    "title": "Control login name case sensitivity",
    "linkTitle": "Control login name case sensitivity",
    "weight": "220"
}You can avoid login errors caused by different treatment of the case sensitivity of user names for the different user types by setting server configuration parameters that control converting the case of login names and the case sensitivity of the names of a virtual users.

-   **`Users.LoginNames.normalizedCaseInsensitiveUsername`**– Controls the conversion of user names entered during login. Valid values are:  
    
    -   `lower` – The user name is converted by mapping all alphabetic character to lower case. This is the default.
    -   `upper` – The user name is converted by mapping all alphabetic character to upper case.
    -   `none` – The user name is not converted.
-   **`Users.LoginNames.virtualUserCaseSensitive`** – Controls whether the user name of a virtual user is case sensitive. Valid values are `true`, the default, or `false`.

The case sensitivity of login names is specified as follows, by user type:

-   **Real users** – User names are case-sensitive on UNIX-based systems and case-insensitive on Windows systems.
-   **Virtual users** – Case sensitivity depends on the parameter `Users.LoginNames.virtualUserCaseSensitive`. When the value of this parameter is `true`, login names must match configured user names exactly. When the value of this parameter is `false` and the value of `Users.LoginNames.normalizedCaseInsensitiveUsername` is `lower`, the login name is converted and there must be no upper case letters in the configured user name. When the value of this parameter is `false` and the value of `Users.LoginNames.normalizedCaseInsensitiveUsername` is `upper`, the login name is converted and there must be no lower case letters in the configured user name. When the value of this parameter is `false` and the value of `Users.LoginNames.normalizedCaseInsensitiveUsername` is `none`, login names must match configured user names exactly.
-   **LDAP users** – Case sensitivity depends on the **LDAP Common case** setting on the *LDAP Server* page. This setting specifies that an LDAP user name must be converted into upper or lower case before it is submitted for authentication. If the value of **LDAP Common case** is either `Upper` or `Lower`, the LDAP user name authentication is case insensitive. If the value of **LDAP Common case** is `None`, then case sensitivity is assumed. In other words, you must set **LDAP Common case** to either `Lower` or `Upper` to indicate that LDAP performs case insensitive match during login, even if it does not require normalization of the input string.
-   **SiteMinder** – Case sensitivity depends on the `Siteminder.UserAttributesMap.commonCaseAttr` parameter on the *Server Configuration* page. Valid values are `disabled`, which causes case sensitive authentication, and `enabled`, which causes case insensitive authentication with the user name converted according to the value of `Users.LoginNames.normalizedCaseInsensitiveUsername`.
