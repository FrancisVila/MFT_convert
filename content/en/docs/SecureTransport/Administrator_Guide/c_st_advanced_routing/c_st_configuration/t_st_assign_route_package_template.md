{
    "title": "Assign Route Package Template",
    "linkTitle": "Assign Route Package Template",
    "weight": "260"
}To assign a Route Package Template to a user account or account template, you must create at least one Route Package Template prior to assigning a route to a user account or account template. For configuration details on managing and creating Route Package Templates, refer to <a href="../t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.

2.  Click the name of the account that you want to assign a route.  
    The *User Account Settings* page is displayed with details for the selected account.

3.  Click the **Routes** tab for the selected account.

4.  Select the desired Route Package Template from the **Route Package Template** list.

5.  Click **Assign Route**.  
    The *Create Route Package* page is displayed. You can navigate to the *Edit Route Package Template* page for the selected Route Package Template by clicking the **Created From** link.

6.  In the **Route Name** field, type the desired name of the route. The route name can contain 254 characters or less.  

    > **Note:**
    >
    > You cannot use the following characters in the route name: \* &lt; > ? " / \\ | :

7.  (Optional) Enter a **Description**.

8.  In the *Inherited Settings* pane:
    1.  Select the check box for a Template Route and click **Disable** to disable an enabled inherited route.

    2.  Select the check box for a Template Route and click **Enable** to enable a disabled inherited route.

    3.  **Note:**
        >
        > The inherited Execution Rule cannot be changed.

        > **Note:**
        >
        > If an inherited route is disabled in the Route Package Template, it cannot be enabled from the Inherited Settings pane. Also, inherited routes cannot be reordered or deleted from the Inherited Settings pane.

9.  In the *Specific Settings* pane:
    1.  Determine the **Execution Rule**. Select either **All Matching Routes** (default) or **First Matching Route**.
    2.  When **All Matching Routes** is selected, all matching Routes are executed. When **First Matching Route** is selected, only the first matching Route is executed.
    3.  Click **New Route**.
    4.  The *New Route Entry* page is displayed. For Route configuration information, refer to <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>.
    5.  You can also edit, enable, disable, reorder, and delete Routes in the *Specific Settings* pane. For information on enabling, disabling, reordering, or deleting Routes, refer to <a href="../t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>.

10. In the *Notifications* pane:  
    As a prerequisite the SMTP settings must be configured by navigating to **Setup > Miscellaneous > SMTP Configuration** in the Administration Tool. For additional SMTP configuration information, refer to refer to <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>. Additionally, in order to add email notifications the administrator must have access to Mail Templates, otherwise this selection is disabled. Mail Templates access is configurable through the Administrative role settings.
    For additional administrative role configuration information, refer to refer to <a href="../../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts" class="MCXref xref">Manage administrator accounts</a>.
    1.  Select **Notify following e-mails on route failure** to be notified on route failure and enter a notification email address, list of addresses, or expression in the field. For additional email configuration information, refer to <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>.
    2.  Select the **Mail Template** from the menu to used for route failure notifications. For email template configuration information, refer to <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.
    3.  Select **Notify following e-mails on route success** to be notified on route success and enter a notification email address, list of addresses, or expression in the field. For additional email configuration information, refer to <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>.
    4.  Select the **Mail Template** from the menu to used for route success notifications. For email template configuration information, refer to <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.
    5.  Select **Notify following e-mails on route trigger** to be notified on route trigger and enter a notification email address, mail relay, or SMTP port in the field. For additional email configuration information, refer to <a href="../../../c_st_setup/c_st_miscellaneousconfiguration/t_st_smtpconfiguration" class="MCXref xref">SMTP configuration</a>.
    6.  Select the **Mail Template** from the menu to used for route triggering notifications. For email template configuration information, refer to <a href="../../../c_st_setup/t_st_mailtemplates" class="MCXref xref">Mail templates</a>.

11. Click **Save**.

**Related topics:**

-   <a href="../t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>
-   <a href="../t_st_create_user_accounts" class="MCXref xref">Create user accounts</a>
-   <a href="../t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>
-   <a href="../t_st_manage_route_package_templates" class="MCXref xref">Manage Route Package Templates</a>
-   <a href="../t_st_manage_routes" class="MCXref xref">Manage Routes</a>
-   <a href="../t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>
