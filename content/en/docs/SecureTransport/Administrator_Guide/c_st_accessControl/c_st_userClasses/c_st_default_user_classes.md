{
    "title": "Default user classes",
    "linkTitle": "Default user classes",
    "weight": "200"
}SecureTransport provides the following default user classes:

-   **RealClass** – all users of type real, connecting from any host address (`*`)
-   **VirtClass** – all users of type virtual, connecting from any host address (`*`)

If not other user classes are defined, all users are in one of the default user classes. You can use these user classes to create access and security settings. For example, you can prevent virtual users from uploading documents to the server. To define more specific access and security settings more specific sets of users, create custom user classes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Classes that match Single Sign-On (SSO) accounts cannot be used with users with type Real.         </td>
      </tr>
</table>

**Related topics:**

-   [Custom expressions](../c_st_custom_expressions)
-   [Manage user classes](../t_st_userclasses)
