{
    "title": "Manage Routes",
    "linkTitle": "Manage Routes",
    "weight": "260"
}If you have access to the *Route Package Templates* page, you can create, edit, and delete Routes as part of managing Route Package Templates. You can also add, edit, enable, disable, reorder, and delete Route steps.

The following topics provide how-to instructions for managing Routes:

-   [New Route](#new)
-   [Edit Route](#edit)
-   [Enable Step](#enable)
-   [Disable Step](#disable)
-   [Reorder Steps](#reorder)
-   [Delete Step](#delete)
-   [Delete Route](#delete_route)

**Related topics:**

-   [Advanced Routing delegated administrator](t_st_create_delegated_administrator4.htm)
-   [Create user accounts](../t_st_create_user_accounts)
-   [Create Advanced Routing application](../t_st_create_advanced_routing_application)
-   [Manage Route Package Templates](../t_st_manage_route_package_templates)
-   [Subscribe to Advanced Routing application](../t_st_subscribe_advanced_routing_application)
-   [Assign Route Package Template](../t_st_assign_route_package_template)

## <span id="New"></span>New Route

Use the following procedure to create a Route.

1.  From the *Route Package Template Entry* page, click **New Route**.  
    The *New Route Entry* page is displayed.

2.  Enter a unique **Route Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../../accounts/useraccounts/t_st_create_user_account).

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

    <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Transformation</th>         <th>Configuration Reference</th>      </tr>   </thead>   <tbody>      <tr>         <td>PGP Encryption         </td>         <td><a href="../../c_st_route_step_transformations/t_st_pgp_encryption">PGP Encryption</a>         </td>      </tr>      <tr>         <td>PGP Decryption         </td>         <td><a href="../../c_st_route_step_transformations/t_st_pgp_decryption">PGP Decryption</a>         </td>      </tr>      <tr>         <td>Compress         </td>         <td><a href="../../c_st_route_step_transformations/t_st_compress">Compress</a>         </td>      </tr>      <tr>         <td>Decompress         </td>         <td><a href="../../c_st_route_step_transformations/t_st_decompress">Decompress</a>         </td>      </tr>      <tr>         <td>Line Ending         </td>         <td><a href="../../c_st_route_step_transformations/t_st_line_ending">Line Ending</a>         </td>      </tr>      <tr>         <td>External Script         </td>         <td><a href="../../c_st_route_step_transformations/t_st_external_script">External Script</a>         </td>      </tr>      <tr>         <td>Encoding Conversion         </td>         <td><a href="../../c_st_route_step_transformations/t_st_charset_conversion">Encoding Conversion</a>         </td>      </tr>      <tr>         <td>Characters Replace         </td>         <td><a href="../../c_st_route_step_transformations/t_st_replace">Characters Replace</a>         </td>      </tr>      <tr>         <td>Line Padding         </td>         <td><a href="../../c_st_route_step_transformations/t_st_line_padding">Line Padding</a>         </td>      </tr>      <tr>         <td>Line Folding         </td>         <td><a href="../../c_st_route_step_transformations/t_st_file_folding">Line Folding</a>         </td>      </tr>      <tr>         <td>Line Truncating         </td>         <td><a href="../../c_st_route_step_transformations/t_st_line_truncating">Line Truncating</a>         </td>      </tr>   </tbody></table>

    <table cellspacing="0">   <col/>   <col/>   <thead>      <tr>         <th>Routing</th>         <th>Configuration Reference</th>      </tr>   </thead>   <tbody>      <tr>         <td>Publish To Account         </td>         <td><a href="../../c_st_route_steps/t_st_publish_to_account">Publish To Account</a>         </td>      </tr>      <tr>         <td>Send To Partner         </td>         <td><a href="../../c_st_route_steps/t_st_send_to_partner">Send To Partner</a>         </td>      </tr>   </tbody></table>

6.  Determine email **Notifications**. In order to add email notifications the administrator must have access to Mail Templates, otherwise this selection is disabled. Mail Templates access is configurable through the Administrative role settings.
    For additional administrative role configuration information, refer to [Manage administrator accounts](../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts).
    1.  Select **Notify following e-mails on route failure**. You need to have configured SMTP settings on the **Administration Tool > Setup > Miscellaneous > SMTP Configuration** page (notify email, mail relay and SMTP port). The *Notify following e-mails on route failure* field supports EL and you can enter:
        -   An email address
        -   An expression, for example `ldap.attributes.Mail, ${account.name}, ${account.email}`.
        -   A list of email addresses (delimiters depend on the SMTP server)
    2.  For additional email configuration information, see [SMTP configuration](../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration).
    3.  Select the **Mail Template** from the menu to used for route failure notifications. For email template configuration information, see [Mail templates](../../../c_st_setup/t_st_mailtemplates).
    4.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, mail relay, or SMTP port in the field.
    5.  Select the **Mail Template** from the menu to used for route failure notifications.
    6.  Select **Notify following e-mails on route trigger** to be notified on route trigger and enter a notification email address, mail relay, or SMTP port in the field.
    7.  Select the **Mail Template** from the menu to used for route trigger notifications.

7.  Click **Save**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can Edit, <a href="#enable">Enable Step</a>, <a href="#disable">Disable Step</a>, <a href="#reorder">Reorder Steps</a>, and <a href="#delete">Delete Step</a> as part of adding a Route.            </td>
      </tr>
</table>

## <span id="Edit"></span>Edit Route

Use the following procedure to edit a Route.

1.  From the *Route Package Template Entry* page, click on the name of the Route to edit in the *Routes* list.  
    The *Edit Route Entry* page is displayed.
2.  Edit the information displayed. To edit a Route Step, click on the name of the Route Step and refer to [Transformations](../../c_st_route_step_transformations) to edit Transformations and to [Route steps](../../c_st_route_steps) to edit Route Steps.
3.  Click **Save** to apply the changes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can Edit, <a href="#enable">Enable Step</a>, <a href="#disable">Disable Step</a>, <a href="#reorder">Reorder Steps</a>, and <a href="#delete">Delete Step</a> as part of adding a Route.            </td>
      </tr>
</table>

## <span id="Enable"></span>Enable Step

Use the following procedure to enable a Route step.

1.  Select the Step to enable from the *Steps* list.
2.  Click **Enable**.  
    The selected Route Step is enabled and an Enabled icon (![Enabled](reordericon.png)) is displayed next to the selected Step name.

## <span id="Disable"></span>Disable Step

Use the following procedure to disable a Route step.

1.  Select the Step to disable from the *Steps* list.
2.  Click **Disable**.  
    The selected Step is disabled and a Disabled icon (![Disabled](reordericon.png)) is displayed next to the selected Step name.

## <span id="Reorder"></span>Reorder Steps

Use the following procedure to reorder Route steps.

1.  Click **Reorder**.  
    A Reorder tool (![Reorder](reordericon.png)) appears for each Step in the *Steps* list.
2.  Use the Reorder tool (![Reorder](reordericon.png)) to move the Steps in the *Steps* list into the desired order.
3.  Click **Save Order**.

## <span id="Delete"></span>Delete Step

Use the following procedure to delete a Route step.

1.  Select the Step to delete from the *Steps* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Step.

## <span id="Delete_route"></span>Delete Route

Use the following procedure to delete a Route.

1.  From the *Route Package Template Entry* page, select the check box for the Route to delete in the *Routes* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Route.
