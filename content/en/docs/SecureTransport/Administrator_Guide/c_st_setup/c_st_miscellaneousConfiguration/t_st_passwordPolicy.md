{
    "title": "Password policy",
    "linkTitle": "Password policy",
    "weight": "300"
}Use this to define a set of requirements that users need to comply with when they change their passwords. You can set the minimum number of characters as well as require the minimum number of letters, numbers, and special characters.

**Related topics:**

-   [Miscellaneous options](../t_st_miscellaneousoptions)
-   [SMTP configuration](../t_st_smtpconfiguration)
-   [FTP and HTTP server suspend options](../t_st_ftphttpservershutdownoptions)

## Specify password policy

1.  Select **Setup > Miscellaneous** and view the *Password Policy* pane.
2.  Specify the desired values in the fields of the *Password Policy* pane.
    -   **Password must contain at least \[*n*\] characters total** – the minimum number of characters that the password must contain. Set *n* = 0 for no minimum number of characters.

    -   **Password must contain at least \[*n*\] alpha characters** – the minimum number of letters that must be in the password. Set *n* = 0 for no minimum number of letters in the password.

    -   **Password must contain at least \[*n*\] numeric characters** – the minimum number of numeric characters that must be in the password. Set *n* = 0 for no minimum number of numbers in the password.

    -   **Password must contain at least \[*n*\] special characters** – the minimum number of special characters (anything other than letters or numeric characters) that must be in the password. Set *n* = 0 for no minimum number of special characters in the password.

    -   **Enforce password history \[*n*\] passwords remembered** – the number of the last *n* stored passwords which are restricted for reuse; should be less or equal to 50. Set *n* = 10 to have the last 10 passwords stored and restricted for reuse upon a password change attempt. Set *n* = 0 to bypass this restriction.  

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> stores the last 50 passwords of an user regardless of the value set in the Enforce password history field.         </td>      </tr></table>

    -   **Minimum password age \[*n*\] days** – the minimum number of days until next allowed password change. This restriction applies when a user changes their password and ends after expiration of the configured *Minimum password age* period. Enter a positive integer value to define the number of days when a user will not be allowed to change their password. Set *n* = 0 to apply no *Minimum password age* restriction.  

        <table cellpadding="0" cellspacing="0">   <col/>   <col/>   <col/>      <tr>         <td valign="top">         </td>         <td valign="top"><span><b>Note</b></span>         </td>         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The configured <i>Minimum password age</i> restriction does not apply when a <span>SecureTransport</span> administrator changes the password of another user or administrator account. Also, the policy does not apply when a user's or administrator's password expires or if they are forced to change their passwords. However, this restriction does apply when a <span>SecureTransport</span> administrator changes their own password.         </td>      </tr></table>
3.  Click **Apply.**
4.  Restart the HTTP server on both the SecureTransport Server and the SecureTransport Edge.

If you are using a streaming setup and you change the password policy while a user is logged into SecureTransport, the old password policy is displayed in the Browser Client when a user tries to change the password.

If you are using an Enterprise Cluster and you change the password policy, a TM restart is required on all nodes of the cluster to apply the changes.

 
