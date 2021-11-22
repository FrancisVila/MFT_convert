{
    "title": "Account templates and external users",
    "linkTitle": "Account templates and external users",
    "weight": "210"
}{{< SecureTransport/componentshortname  >}} assigns external users to the account template using the following steps:

1.  Determine the User Class based on the already known values for the UID, GID, User Type, and IP address.
2.  Compare the determined User Class with the defined User Class in all enabled external account templates. Since the User Class in the template can contain wildcards there might be more than one template that matches the User Class of the currently logged user. In this case, the templates are sorted alphabetically, and the first one is selected.
3.  If the User Class matches the User Class of a template, {{< SecureTransport/componentshortname >}} tries to determine the new UID, GID, and Home Folder values as defined in the template. The templates can contain expressions in the supported expression language to dynamically select the UID, GID, or Home Folder. The result is one of the following:
    -   If the system fails to determine even one of the required attributes (UID, GID, or Home Folder) from the template the user is *not* assigned to that template and the login fails.
    -   If the system manages to determine all of the required attributes, the currently logged external user is assigned to the selected template.
    -   If the User Class does not match any of the User Classes in the account template, the server treats the user as a regular external user.
4.  If the user is assigned to a template, the UID, GID, and Home Folder are determined from the template, and the values used to determine the User Class are ignored. If the home folder of the user is missing, it is automatically created with the correct permissions.
5.  After the external user is mapped to a template the user is automatically assigned a User Type of Virtual, the same as a regular user account.

**Related topics:**

-   <a href="../c_st_account_template_required_values" class="MCXref xref">Account template required values</a>
-   <a href="../t_st_accounttemplates" class="MCXref xref">Manage account templates</a>
