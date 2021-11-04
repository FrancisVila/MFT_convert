{
    "title": "Manage Routes",
    "linkTitle": "Manage Routes",
    "weight": "250"
}If you have access to the *Route Package Templates* page, you can create, edit, and delete Routes as part of managing Route Package Templates. You can also add, edit, enable, disable, reorder, and delete Route steps.

The following topics provide how-to instructions for managing Routes:

-   <a href="#New" class="MCXref xref">New Route</a>
-   <a href="#Edit" class="MCXref xref">Edit Route</a>
-   <a href="#Enable" class="MCXref xref">Enable Step</a>
-   <a href="#Disable" class="MCXref xref">Disable Step</a>
-   <a href="#Reorder" class="MCXref xref">Reorder Steps</a>
-   <a href="#Delete" class="MCXref xref">Delete Step</a>
-   <a href="#Delete_route" class="MCXref xref">Delete Route</a>

**Related topics:**

-   <a href="../t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>
-   <a href="../t_st_create_user_accounts" class="MCXref xref">Create user accounts</a>
-   <a href="../t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>
-   <a href="../t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>
-   <a href="../t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>
-   <a href="../t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>

<span id="New"></span>

## New Route

Use the following procedure to create a Route.

1.  From the *Route Package Template Entry* page, click **New Route**.  
    The *New Route Entry* page is displayed.
2.  Enter a unique **Route Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.
3.  (Optional) Enter a **Description**.
4.  Determine the **Condition**. Select either **Always** (default) or **Expression Language**.  
    When **Always** is selected, the trigger condition is always used. When **Expression Language** is selected, the trigger condition is based on the expression entered in the *Expression Language* field.  
    Expression Language should be used to define the route trigger condition.  
    Examples:  
    Files uploaded only through a specific protocol:  
    `${session.protocol eq 'http'}`  
    Files uploaded from specific partner over PeSIT:  
    `${pesit.pi.senderID.toLowerCase() eq 'partner'}`
5.  Select steps (**Transformation** or **Routing**) from the *Select Step* menu and click **Add Step**. Refer to the following tables for **Transformation** or **Routing** configuration information.
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Transformation         </th>
    <th class="HeadD-Column1-Header1">Configuration Reference         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>PGP Encryption         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_pgp_encryption" class="MCXref xref">PGP Encryption</a>         </td>
          </tr>
          <tr>
             <td>PGP Decryption         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_pgp_decryption" class="MCXref xref">PGP Decryption</a>         </td>
          </tr>
          <tr>
             <td>Compress         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_compress" class="MCXref xref">Compress</a>         </td>
          </tr>
          <tr>
             <td>Decompress         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_decompress" class="MCXref xref">Decompress</a>         </td>
          </tr>
          <tr>
             <td>Line Ending         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_line_ending" class="MCXref xref">Line Ending</a>         </td>
          </tr>
          <tr>
             <td>External Script         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_external_script" class="MCXref xref">External Script</a>         </td>
          </tr>
          <tr>
             <td>Encoding Conversion         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_charset_conversion" class="MCXref xref">Encoding Conversion</a>         </td>
          </tr>
          <tr>
             <td>Characters Replace         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_replace" class="MCXref xref">Characters Replace</a>         </td>
          </tr>
          <tr>
             <td>Line Padding         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_line_padding" class="MCXref xref">Line Padding</a>         </td>
          </tr>
          <tr>
             <td>Line Folding         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_file_folding" class="MCXref xref">Line Folding</a>         </td>
          </tr>
          <tr>
             <td>Line Truncating         </td>
             <td><a href="../../c_st_route_step_transformations/t_st_line_truncating" class="MCXref xref">Line Truncating</a>         </td>
          </tr>
       </tbody>
    </table>

    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Routing         </th>
    <th class="HeadD-Column1-Header1">Configuration Reference         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td>Publish To Account         </td>
             <td><a href="../../c_st_route_steps/t_st_publish_to_account" class="MCXref xref">Publish To Account</a>         </td>
          </tr>
          <tr>
             <td>Send To Partner         </td>
             <td><a href="../../c_st_route_steps/t_st_send_to_partner" class="MCXref xref">Send To Partner</a>         </td>
          </tr>
       </tbody>
    </table>
6.  Determine email **Notifications**. In order to add email notifications the administrator must have access to Mail Templates, otherwise this selection is disabled. Mail Templates access is configurable through the Administrative role settings.
    For additional administrative role configuration information, refer to <a href="../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts" class="MCXref xref">Manage administrator accounts</a>.
    1.  Select **Notify following e-mails on route failure**. You need to have configured SMTP settings on the **Administration Tool > Setup > Miscellaneous > SMTP Configuration** page (notify email, mail relay and SMTP port). The *Notify following e-mails on route failure* field supports EL and you can enter:
        -   An email address
        -   An expression, for example `ldap.attributes.Mail, ${account.name}, ${account.email}`.
        -   A list of email addresses (delimiters depend on the SMTP server)
    2.  For additional email configuration information, see <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>.
    3.  Select the **Mail Template** from the menu to used for route failure notifications. For email template configuration information, see <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.
    4.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, mail relay, or SMTP port in the field.
    5.  Select the **Mail Template** from the menu to used for route failure notifications.
    6.  Select **Notify following e-mails on route trigger** to be notified on route trigger and enter a notification email address, mail relay, or SMTP port in the field.
    7.  Select the **Mail Template** from the menu to used for route trigger notifications.
7.  Click **Save**.

> **Note:**
>
> You can Edit, Enable Step, Disable Step, Reorder Steps, and Delete Step as part of adding a Route.

<span id="Edit"></span>

## Edit Route

Use the following procedure to edit a Route.

1.  From the *Route Package Template Entry* page, click on the name of the Route to edit in the *Routes* list.  
    The *Edit Route Entry* page is displayed.
2.  Edit the information displayed. To edit a Route Step, click on the name of the Route Step and refer to <a href="../../c_st_route_step_transformations" class="MCXref xref">Transformations</a> to edit Transformations and to <a href="../../c_st_route_steps" class="MCXref xref">Route steps</a> to edit Route Steps.
3.  Click **Save** to apply the changes.

> **Note:**
>
> You can Edit, Enable Step, Disable Step, Reorder Steps, and Delete Step as part of adding a Route.

<span id="Enable"></span>

## Enable Step

Use the following procedure to enable a Route step.

1.  Select the Step to enable from the *Steps* list.
2.  Click **Enable**.  
    The selected Route Step is enabled and an Enabled icon (![Enabled](/Images/SecureTransport/enabledicon.png)) is displayed next to the selected Step name.

<span id="Disable"></span>

## Disable Step

Use the following procedure to disable a Route step.

1.  Select the Step to disable from the *Steps* list.
2.  Click **Disable**.  
    The selected Step is disabled and a Disabled icon (![Disabled](/Images/SecureTransport/disabledicon.png)) is displayed next to the selected Step name.

<span id="Reorder"></span>

## Reorder Steps

Use the following procedure to reorder Route steps.

1.  Click **Reorder**.  
    A Reorder tool (![Reorder](/Images/SecureTransport/reordericon.png)) appears for each Step in the *Steps* list.
2.  Use the Reorder tool (![Reorder](/Images/SecureTransport/reordericon.png)) to move the Steps in the *Steps* list into the desired order.
3.  Click **Save Order**.

<span id="Delete"></span>

## Delete Step

Use the following procedure to delete a Route step.

1.  Select the Step to delete from the *Steps* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Step.

<span id="Delete_route"></span>

## Delete Route

Use the following procedure to delete a Route.

1.  From the *Route Package Template Entry* page, select the check box for the Route to delete in the *Routes* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Route.
