{
    "title": "Password Reset",
    "linkTitle": "Password Reset",
    "weight": "220"
}The <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Web Client users can reset their passwords if allowed by the administrator. If users have an email address configured in their <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> account, they can reset their passwords from the *Login* page. If not, they must contact the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>administrator to reset the password.

> **Note:**
>
> This functionality does not apply to LDAP or SSO users.

This functionality is controlled and configured by the following server configuration options, available on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> edge and backend servers in the Server configuration page in the Admin user interface:

#### PasswordReset.Enabled

Specifies if password reset is enabled. The default value for thе setting is true.

#### PasswordReset.Interval

Specifies the minimum interval (in minutes) between two password reset requests for the same email. The value must be a positive integer. The default value for the setting is 60.

#### PasswordReset.LinkExpirationInterval

Specifies the time (in minutes) until the reset password link expires. The value must be a positive integer. The default value for the setting is 60.

#### PasswordReset.RequireUsername

If set to true, users will be asked for a username and an email while requesting a password reset. Otherwise, only email is required. Possible values are true/false. The default value for the setting is false.

> **Note:**
>
> Set all the password reset configuration options on all SecureTransport edge and backend servers in your setup to have identical values to avoid unexpected behaviour in a streaming setup. (Valid note for all server configuration options: PasswordReset.Enabled, PasswordReset.Interval, PasswordReset.LinkExpirationInterval, PasswordReset.RequireUsername)

To reset a password, an end user must click on the **Forgot your password?** link on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Web Client login page and the following window will be displayed:

A valid and unique email address must be provided.

Client password reset will not work if emails assigned to user accounts in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> are not unique.

<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> sends an email with password reset instructions to the email address provided.

Once the user opens the link in the email, they are prompted to enter and confirm the new password in the displayed form.

If secret question service is enabled, the user must provide an answer to a secret question as part of the password reset process.

The user must fill in all the fields, save, and in case of success, log in with the new password.

#### Token

A token will be generated for authentication during the whole password reset process.

The token is encrypted with the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Secret and bears its creation-time stamp and the account's email.

A token is expired if time, indicated by the `PasswordReset.LinkExpirationInterval` configuration option, has passed or if a password reset has occurred after the creation of the token.

The link sent via email will have the following structure: `https://<st_ip>/passwordReset?token=<encryptedString>`.

If the secret question feature is enabled in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, the users must answer a secret question, which they have preciously set, before they can reset their password.

For more information on Secret Question Functionality, see <a href="t_st_secretquestion" class="MCXref xref">Configure a secret question</a>.