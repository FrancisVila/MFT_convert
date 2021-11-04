{
    "title": " Manage Route Package Templates",
    "linkTitle": "Manage Route Package Templates",
    "weight": "240"
}Use the *Route Package Templates* page to manage route package templates. Route package templates can be created, edited, and deleted from the *Route Package Templates* page. To display the *Route Package Templates* page, select **Routes &gt; Route Packages**.

If you have access to the *Route Package Templates* page, you can create, edit, and delete route package templates. Master administrators and limited administrators with the Manage Route Package Templates privilege have access to the *Route Package Templates* page by default.

The following topics provide how-to instructions for managing Route Package Templates:

-   <a href="#Add" class="MCXref xref">Add Route Package Template</a>
-   <a href="#Edit" class="MCXref xref">Edit Route Package Template</a>
-   <a href="#Enable" class="MCXref xref">Enable Route</a>
-   <a href="#Disable" class="MCXref xref">Disable Route</a>
-   <a href="#Reorder" class="MCXref xref">Reorder Routes</a>
-   <a href="#Delete" class="MCXref xref">Delete Route</a>
-   <a href="#Delete_template" class="MCXref xref">Delete Route Package Template</a>

**Related topics:**

-   <a href="../t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>
-   <a href="../t_st_create_user_accounts" class="MCXref xref">Create user accounts</a>
-   <a href="../t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>
-   <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>
-   <a href="../t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>
-   <a href="../t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>

<span id="Add"></span>

## Add Route Package Template

Use the following procedure to add a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Click **New Route Package Template**.  
    The *New Route Package Template Entry* page is displayed.
3.  Enter a unique **Route Package Template Name**. You cannot enter spaces-only values in this field. For more information, see <a href="../../../accounts/useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.
4.  (Optional) Use the **Left** and **Right** buttons to assign business units to the Route Package Template. The **Business Unit List** contains the names of business units you create. For details, <a href="../../../c_st_advancedaccountadministration/c_st_businessunits" class="MCXref xref">Business units</a>.
5.  (Optional) Enter a **Description**.
6.  Determine the **Execution Rule**. Select either **All Matching Routes** (default) or **First Matching Route**.  
    When **All Matching Routes** is selected, all matching routes are executed. When **First Matching Route** is selected, only the first matching route is executed.
7.  Click **New Route**.  
    The *New Route Entry* page is displayed. For route entry configuration information, see <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>.
8.  (Optional) Have **Additional attributes** with your route package templates: you can use the group of fields to add (or remove) custom attributes as *attribute:value* pairs. To add a new attribute: click **Add Attribute**, input entries for the attribute and value pair and click the Save (![](/Images/SecureTransport/SaveIcon.png)) icon to store your input. To remove an attribute: select the corresponding checkbox and click **Delete**. You can also edit either entry (for attribute or value) of an existing attribute. See <a href="../../../c_st_setup/t_st_mailtemplates/c_st_mail_template_commands_variables#Addition" class="MCXref xref">Additional attributes</a>.
9.  Determine email **Notifications**. As a prerequisite the SMTP settings must be configured by navigating to **Setup > Miscellaneous > SMTP Configuration** in the Administration Tool. For additional SMTP configuration information, see <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>. Additionally, in order to add email notifications the administrator must have access to Mail Templates, otherwise this selection is disabled. Mail Templates access is configurable through the Administrative role settings.
    See <a href="../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts" class="MCXref xref">Manage administrator accounts</a>.
    1.  Select **Notify following e-mails on route failure** to be notified on route failure and enter a notification email address, a list of mail addresses, or an expression.
    2.  Select the **Mail Template** from the menu to used for route failure notifications. See <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.
    3.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, a list of mail addresses, or an expression
    4.  Select the **Mail Template** from the menu to used for route failure notifications.
    5.  Select **Notify following e-mails on route triggering** to be notified on route triggering and enter a notification email address, a list of mail addresses, or an expression.
    6.  Select the **Mail Template** from the menu to used for route triggering notifications.
10. Click **Save**.

> **Note:**
>
> You can Manage Routes, Enable Route, Disable Route, Reorder Routes, and Delete Route as part of editing a Route Package Template.

<span id="Edit"></span>

## Edit Route Package Template

Use the following procedure to edit a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Click on the name of the Route Package Template to edit in the *Route Package Templates List*.  
    The *Edit Route Package Template Entry* page is displayed.
3.  Edit the information displayed. To edit a route, click on the name of the Route and see <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>.
4.  Click **Save** to apply the changes.

> **Note:**
>
> You can Manage Routes, Enable Route, Disable Route, Reorder Routes, and Delete Route as part of editing a Route Package Template.

<span id="Enable"></span>

## Enable Route

Use the following procedure to enable a Route.

1.  Select the Route to enable from the *Routes* list.
2.  Click **Enable**.  
    The selected Route is enabled and a Enabled icon (![Enabled](/Images/SecureTransport/enabledicon.png)) is displayed next to the selected Route name.

<span id="Disable"></span>

## Disable Route

Use the following procedure to disable a Route.

1.  Select the Route to disable from the *Routes* list.
2.  Click **Disable**.  
    The selected Route is disabled and a Disabled icon (![Disabled](/Images/SecureTransport/disabledicon.png) ) is displayed next to the selected Route name.

<span id="Reorder"></span>

## Reorder Routes

Use the following procedure to reorder the Routes

1.  Click **Reorder**.  
    A Reorder tool (![Reorder](/Images/SecureTransport/reordericon.png)) appears for each Route in the *Routes* list.
2.  Use the Reorder tool (![Reorder](/Images/SecureTransport/reordericon.png)) to move the Routes in the *Routes* list into the desired order.
3.  Click **Save Order**.

<span id="Delete"></span>

## Delete Route

Use the following procedure to delete a Route.

1.  Select the Route to delete from the *Routes* list.
2.  Click **Delete**.
3.  When prompted, confirm that you would like to delete the selected Route.

<span id="Delete_template"></span>

## Delete Route Package Template

Use the following procedure to delete a Route Package Template.

1.  Select **Routes >Route Packages**.  
    The *Route Package Template* page is displayed.
2.  Select the check box for the Route Package Template to delete from the *Route Package Templates List*.
3.  Click Delete.
4.  When prompted, confirm that you would like to delete the selected Route Package Template.
