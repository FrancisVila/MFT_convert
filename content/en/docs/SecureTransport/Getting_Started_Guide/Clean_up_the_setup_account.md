{
    "title": "Clean up the setup account",
    "linkTitle": "Clean up the setup account",
    "weight": "120"
}The initial configuration of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> is now complete. As a final step, clean up the Setup account either by removing it or by changing the password. You can use the default administrator account for additional configuration tasks.

1.  Log out of the Administration Tool.
2.  Log in using the default user name, `admin` and default password `admin`.
3.  Select **Accounts > Administrators**.
4.  Take one of the following actions:
    -   Remove the Setup Administrator by clicking the check box next to it and then **Delete**.
    -   Change the password for the Setup Administrator by clicking the administrator entry and setting the desired password in the *Administrator Account Status* pane.

For the best security, change the default password of the `account`, `admin`, and `application` administrator accounts.

For more information on the ****Accounts &gt; Administrators** ** settings, refer to the <span class="redirect_st_ag" cshid="admin" data-version="5.3.5">*<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Administrator's Guide*</span>.

> **Note:**
>
> Once you have made the configuration changes using the Administration Tool, run stop\_all to stop all SecureTransport services, then run start\_all to restart them. For information on stopping and starting SecureTransport services, refer to the SecureTransport Administrator's Guide.
