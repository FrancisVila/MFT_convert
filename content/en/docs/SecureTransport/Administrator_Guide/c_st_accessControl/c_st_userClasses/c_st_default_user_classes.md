{
    "title": "Default user classes",
    "linkTitle": "Default user classes",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> provides the following default user classes:

-   **RealClass** – all users of type real, connecting from any host address (`*`)
-   **VirtClass** – all users of type virtual, connecting from any host address (`*`)

If not other user classes are defined, all users are in one of the default user classes. You can use these user classes to create access and security settings. For example, you can prevent virtual users from uploading documents to the server. To define more specific access and security settings more specific sets of users, create custom user classes.

> **Note:**
>
> Classes that match Single Sign-On (SSO) accounts cannot be used with users with type Real.

**Related topics:**

-   <a href="../c_st_custom_expressions" class="MCXref xref">Custom expressions</a>
-   <a href="../t_st_userclasses" class="MCXref xref">Manage user classes</a>
