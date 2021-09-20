{
    "title": "Account templates",
    "linkTitle": "Account templates",
    "weight": "200"
}You can create an account template that can be used by LDAP, SSO, or other external user repositories. Use account templates to avoid duplicating users between your user repository and SecureTransport. Account templates let SecureTransport use the user names and passwords that exist in external user repositories such as LDAP, SSO, Active Directory, or a third party database. SecureTransport does not need to synchronize with any external source. By using the value set in the User Class field, the account templates map the user in real time to SecureTransport.

The template uses the user class as a type of dividing mechanism, allowing you to create different templates for different user functions based on the User Class. A user can be assigned a User Class based on the following items: User Type, User Name, User Group, and From address (the IP address or host name of the logged in user). Create a specific user class for each external repository that you are using.

Templates can also be assigned a business unit.

The following topics describe how to assign external users to account templates and how to manage account template. They also list the account template required values.

-   [Account templates and external users](c_st_account_templates_external_users) - Describes how to assign external users to account templates.
-   [Account template required values](c_st_account_template_required_values) - Lists the account template required values.
-   [Manage account templates](t_st_accounttemplates) - Provide how-to instructions for managing account templates.