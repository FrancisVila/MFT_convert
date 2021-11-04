{
    "title": "Account template required values",
    "linkTitle": "Account template required values",
    "weight": "220"
}Each template has several required values: **Account Template Name**, **User Class**, **UID**, **Group ID**, and **Change Home To**.

There are three ways to configure a template once you have specified the **User Class** and **Account Template Name**, and **Business Unit**:

-   **Hardcoded values** – The values of the **UID**, **Group ID**, **Change Home To**, and **Notes** fields are explicitly specified in the template. In this scenario every external user mapped to the template uses the same home folder and has the same UID and Group ID (GID).
-   **Expressions** – In this scenario the values of the **UID**, **Group ID**, **Change Home To**, and **Notes** fields are specified expressions in the supported expression language. Usually the values of the attributes are different for each external user.
-   **Mixed** – Some values are hardcoded and some are expressions or text that includes hardcoded values and expressions. For example you can specify the **Change Home To** as `/tmp/users/${stenv['loginname']}` which means that the home folder of every external user is determined by adding the path `/tmp/users/` and the login name.

Directory path names in an account template are case sensitive.

> **Note:**
>
> If you configure the home directory of an account template that is used for LDAP or SSO users to include the user name in the home directory, and LDAP or SSO user whose user name contains one or more of the characters &lt;, &gt;, #, and \\ or begins or ends with a space character cannot log in to SecureTransport. This is due to operating system limitation on file names. To allow such LDAP or SSO users to use an account template, use the UID or some other user-unique value to name the home directory.

**Related topics:**

-   <a href="../c_st_account_templates_external_users" class="MCXref xref">Account templates and external users</a>
-   <a href="../t_st_accounttemplates" class="MCXref xref">Manage account templates</a>