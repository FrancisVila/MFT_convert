{
    "title": "Manage Route Package Templates",
    "linkTitle": "Manage Route Package Templates",
    "weight": "250"
}Use the *Route Package Templates* page to manage route package templates. Route package templates can be created, edited, and deleted from the *Route Package Templates* page. To display the *Route Package Templates* page, select **Routes &gt; Route Packages**.

If you have access to the *Route Package Templates* page, you can create, edit, and delete route package templates. Master administrators and limited administrators with the Manage Route Package Templates privilege have access to the *Route Package Templates* page by default.

The following topics provide how-to instructions for managing Route Package Templates:

-   [Add Route Package Template](#add)
-   [Edit Route Package Template](#edit)
-   [Enable Route](#enable)
-   [Disable Route](#disable)
-   [Reorder Routes](#reorder)
-   [Delete Route](#delete)
-   [Delete Route Package Template](#delete_template)

**Related topics:**

-   [Advanced Routing delegated administrator](t_st_create_delegated_administrator4.htm)
-   [Create user accounts](../t_st_create_user_accounts)
-   [Create Advanced Routing application](../t_st_create_advanced_routing_application)
-   [Manage Routes](../t_st_manage_routes)
-   [Subscribe to Advanced Routing application](../t_st_subscribe_advanced_routing_application)
-   [Assign Route Package Template](../t_st_assign_route_package_template)

## <span id="Add"></span>Add Route Package Template

Use the following procedure to add a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Click **New Route Package Template**.  
    The *New Route Package Template Entry* page is displayed.
3.  Enter a unique **Route Package Template Name**. You cannot enter spaces-only values in this field. For more information, see [Spaces in required fields](../../../accounts/useraccounts/t_st_create_user_account).
4.  (Optional) Use the **Left** and **Right** buttons to assign business units to the Route Package Template. The **Business Unit List** contains the names of business units you create. For details, [Business units](../../../c_st_advancedaccountadministration/c_st_businessunits).
5.  (Optional) Enter a **Description**.
6.  Determine the **Execution Rule**. Select either **All Matching Routes** (default) or **First Matching Route**.  
    When **All Matching Routes** is selected, all matching routes are executed. When **First Matching Route** is selected, only the first matching route is executed.
7.  Click **New Route**.  
    The *New Route Entry* page is displayed. For route entry configuration information, see [Manage Routes](../t_st_manage_routes).
8.  (Optional) Have **Additional attributes** with your route package templates: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](reordericon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See [Additional attributes](../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables).
9.  Determine email **Notifications**. As a prerequisite the SMTP settings must be configured by navigating to **Setup > Miscellaneous > SMTP Configuration** in the Administration Tool. For additional SMTP configuration information, see [SMTP configuration](../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration). Additionally, in order to add email notifications the administrator must have access to Mail Templates, otherwise this selection is disabled. Mail Templates access is configurable through the Administrative role settings.
    See [Manage administrator accounts](../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts).
    1.  Select **Notify following e-mails on route failure** to be notified on route failure and enter a notification email address, a list of mail addresses, or an expression.
    2.  Select the **Mail Template** from the menu to used for route failure notifications. See [Mail templates](../../../c_st_setup/t_st_mailtemplates).
    3.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, a list of mail addresses, or an expression
    4.  Select the **Mail Template** from the menu to used for route failure notifications.
    5.  Select **Notify following e-mails on route triggering** to be notified on route triggering and enter a notification email address, a list of mail addresses, or an expression.
    6.  Select the **Mail Template** from the menu to used for route triggering notifications.
10. Click **Save**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can <a href="../t_st_manage_routes" xrefformat="{paratext}">Manage Routes</a>, <a href="#enable" xrefformat="{paratext}">Enable Route</a>, <a href="#disable" xrefformat="{paratext}">Disable Route</a>, <a href="#reorder" xrefformat="{paratext}">Reorder Routes</a>, and <a href="#delete" xrefformat="{paratext}">Delete Route</a> as part of editing a Route Package Template.          </td>
      </tr>
</table>

## <span id="Edit"></span>Edit Route Package Template

Use the following procedure to edit a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Click on the name of the Route Package Template to edit in the *Route Package Templates List*.  
    The *Edit Route Package Template Entry* page is displayed.
3.  Edit the information displayed. To edit a route, click on the name of the Route and see [Manage Routes](../t_st_manage_routes).
4.  Click **Save** to apply the changes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You can <a href="../t_st_manage_routes" xrefformat="{paratext}">Manage Routes</a>, <a href="#enable" xrefformat="{paratext}">Enable Route</a>, <a href="#disable" xrefformat="{paratext}">Disable Route</a>, <a href="#reorder" xrefformat="{paratext}">Reorder Routes</a>, and <a href="#delete" xrefformat="{paratext}">Delete Route</a> as part of editing a Route Package Template.          </td>
      </tr>
</table>

## <span id="Enable"></span>Enable Route

Use the following procedure to enable a Route.

1.  Select the Route to enable from the *Routes* list.
2.  Click **Enable**.  
    The selected Route is enabled and a Enabled icon (![Enabled](reordericon.png)) is displayed next to the selected Route name.

## <span id="Disable"></span>Disable Route

Use the following procedure to disable a Route.

1.  Select the Route to disable from the *Routes* list.
2.  Click **Disable**.  
    The selected Route is disabled and a Disabled icon (![Disabled](reordericon.png) ) is displayed next to the selected Route name.

## <span id="Reorder"></span>Reorder Routes

Use the following procedure to reorder the Routes

1.  Click **Reorder**.  
    A Reorder tool (![Reorder](reordericon.png)) appears for each Route in the *Routes* list.
2.  Use the Reorder tool (![Reorder](reordericon.png)) to move the Routes in the *Routes* list into the desired order.
3.  Click **Save Order**.

## <span id="Delete"></span>Delete Route

Use the following procedure to delete a Route.

1.  Select the Route to delete from the *Routes* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Route.

## <span id="Delete_template"></span>Delete Route Package Template

Use the following procedure to delete a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Select the check box for the Route Package Template to delete from the *Route Package Templates List*.
3.  Click Delete.
4.  When prompted, confirm that you would like to delete the selected Route Package Template.
