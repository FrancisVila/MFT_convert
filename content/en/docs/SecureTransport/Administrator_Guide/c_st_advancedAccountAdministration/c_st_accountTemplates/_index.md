{
    "title": "Account templates",
    "linkTitle": "Account templates",
    "weight": "190"
}You can create an account template that can be used by LDAP, SSO, or other external user repositories. Use account templates to avoid duplicating users between your user repository and <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>. Account templates let <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> use the user names and passwords that exist in external user repositories such as LDAP, SSO, Active Directory, or a third party database. <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> does not need to synchronize with any external source. By using the value set in the User Class field, the account templates map the user in real time to <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>.

The template uses the user class as a type of dividing mechanism, allowing you to create different templates for different user functions based on the User Class. A user can be assigned a User Class based on the following items: User Type, User Name, User Group, and From address (the IP address or host name of the logged in user). Create a specific user class for each external repository that you are using.

Templates can also be assigned a business unit.

The following topics describe how to assign external users to account templates and how to manage account template. They also list the account template required values.

-   <a href="c_st_account_templates_external_users" class="MCXref xref">Account templates and external users</a> - Describes how to assign external users to account templates.
-   <a href="c_st_account_template_required_values" class="MCXref xref">Account template required values</a> - Lists the account template required values.
-   <a href="t_st_accounttemplates" class="MCXref xref">Manage account templates</a> - Provide how-to instructions for managing account templates.
