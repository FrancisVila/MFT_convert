{
    "title": "Configure a secret question",
    "linkTitle": "Secret Question configuration",
    "weight": "240"
}Enabling and configuring the optional secret question feature provides a secure challenge and response mechanism for resetting passwords. It also eliminates the security risks of replacing passwords with temporary ones and sending passwords via email.

If the secret question feature is enabled and their system administrator requires them to do so, end users must select and answer a secret question during their initial login. If the secret question feature is enabled and they are not required to select a secret question, end users may optionally select and answer a secret question. For additional information, refer to the *ST Web Client User Guide*.

As a system administrator, you can:

-   <a href="#Enable" class="MCXref xref">Enable or disable the secret question feature</a>
-   <a href="#Set_minimum_length" class="MCXref xref">Set minimum length for the Secret question answer</a>
-   <a href="#Set" class="MCXref xref">Set maximum number of answer attempts</a>
-   <a href="#Configur" class="MCXref xref">Configure a list of secret questions</a>
-   <a href="#Require" class="MCXref xref">Require a user to select a new secret question</a>

If an end user forgets their password, they must:

1.  Submit a password reset request through their email using the ST Web Client forgotten password mechanism.
2.  Click the reset password link in the forgotten password email.
3.  Answer the secret question correctly.
4.  Provide and verify their new password.

For additional information on the end user password reset process, refer to the *ST Web Client User Guide*.

<span id="Enable"></span>

## Enable or disable the secret question feature

By default the secret question feature is disabled. To enable the secret question feature:

1.  Navigate to **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `Users.SecretQuestion.Enabled` configuration parameter.
3.  Click the **Edit** (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) icon in the *Edit* column.
4.  Change the `Users.SecretQuestion.Enabled` configuration parameter to **true**.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon in the *Edit* column.

To disable the secret question feature:

Repeat steps 1 through 5, but set the configuration parameter to **false**.

For more information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a>.

<span id="Set_minimum_length"></span>

## Set minimum length for the Secret question answer

To configure a minimum length for the Secret question answer:

1.  Navigate to **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `Users.SecretAnswer.MinLength` configuration parameter.
3.  Click the **Edit** (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) icon in the *Edit* column.
4.  Enter the desired minimum number of characters in the *Value* field. The default value is **0**.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon in the *Edit* column.

<span id="Set"></span>

## Set maximum number of answer attempts

To configure the maximum number of answer attempts:

1.  Navigate to **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `Users.SecretQuestion.MaxAttempts` configuration parameter.
3.  Click the **Edit** (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) icon in the *Edit* column.
4.  Enter the desired number of answer attempts in the *Value* field. The default value is **0**.
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon in the *Edit* column.

For more information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a>.

<span id="Configur"></span>

## Configure a list of secret questions

To configure a list of secret questions:

1.  Navigate to **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `Users.SecretQuestions` configuration parameter.
3.  Click the **Edit** (![Edit](/Images/SecureTransport/EditIcon_12x13.png)) icon in the *Edit* column.
4.  Update the `Users.SecretQuestions` list as desired. The secret questions must be separated by a hard return. The default secret questions are:
    -   **What make was your first car or bike?**
    -   **What is your father's middle name?**
    -   **What is your mother's maiden name?**
    -   **What is your school's mascot?**
    -   **What is the name of your favorite fictional character?**
    -   **What is your favorite teacher's name?**
    -   **Where did you go on your first date?**
    -   **What is your dog's name?**
    -   **What is your dream occupation?**
5.  Click the **Save** (![](/Images/SecureTransport/SaveIcon2.png)) icon in the *Edit* column.

For more information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a>.

<span id="Require"></span>

## Require a user to select a new secret question

To require a user to select and answer a new secret question, edit their user account and select **Require user to set new secret question on next login**. On the next login, the user must select and answer a new secret question before they can access the user interface. For additional information on editing user accounts, refer to <a href="../../useraccounts/t_st_edit_user_account_settings" class="MCXref xref">Edit user account settings</a>.
