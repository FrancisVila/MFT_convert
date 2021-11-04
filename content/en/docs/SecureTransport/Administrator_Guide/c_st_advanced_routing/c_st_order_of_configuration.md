{
    "title": "Order of configuration",
    "linkTitle": "Order of configuration",
    "weight": "180"
}This topic provides the configuration order for the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> feature. It also provides a brief overview of each configuration item.

Business units can be created prior to configuring the Route Package Template. For configuration information, refer to <a href="#" class="MCXref xref">Manage business units</a>

Optionally, an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> administrator can be created. For configuration information, refer to <a href="../c_st_configuration/t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a> and to <a href="../c_st_configuration/t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>.

The <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> feature should be configured in the following order:

1.  Create user account (or account template) or use an existing one. See .
2.  Create <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application. See <a href="../c_st_configuration/t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>.
3.  Create Route Package Template.
4.  Assign Route Package Template to the account from Step 1. See <a href="../c_st_configuration/t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>.
5.  Subscribe to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application. See .

## Create <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> administrator

In order to setup an administrator dedicated to managing the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application and Route Package Templates it is necessary to create an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> administrator with file tracking, accounts, applications, mail templates, and routes privileges. For instructions on creating an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> administrator, refer to <a href="../c_st_configuration/t_st_create_delegated_administrator" class="MCXref xref">Advanced Routing delegated administrator</a>.

## Create user accounts

In order to subscribe an account to an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance, start off by creating a <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> user account or account template (or use an existing one). For information on creating user accounts, refer to <a href="../../accounts/useraccounts/t_st_create_user_account" class="MCXref xref">Create a user account</a>. For information on creating account templates, refer to <a href="../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates" class="MCXref xref">Manage account templates</a>

## Create <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application

Navigate to the **Application** tab and click **Add New**. Specify the preferred **Application Name** for the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance. Select *<span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span>* from the **Application Type** combo box. For additional information on creating an <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application instance, refer to <a href="../c_st_configuration/t_st_create_advanced_routing_application" class="MCXref xref">Create Advanced Routing application</a>.

## Create Route Package Template

Navigate to the **Routes** tab and click **New Route Package Template**. Specify the preferred **Route Package Template Name** for the Route Package Template, determine assigned business units, enter a route template description, determine execution routes, add transformation and routing steps, and determine notifications. For additional information

## Assign Route Package Template

You must subscribe the selected user to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application prior to assigning the user a Route Package Template. To assign the user a Route Package Template, navigate to **Accounts &gt; User Accounts**, select the desired user account, and then select the **Routes** tab for the selected account. From the *Routes* tab, select the desired Route Package Template from the **Route Package Template** list and then click **Assign Route**. The *Create Route Package* screen is displayed with a link to the selected Route Package Template under the **Created From** label. For more details on assigning a Route Package Template, refer to <a href="../c_st_configuration/t_st_assign_route_package_template" class="MCXref xref">Assign Route Package Template</a>.

## Subscribe to <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application

To subscribe a user account to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application, navigate to **Accounts &gt; User Accounts**, select the desired user account, and then select the **Subscriptions** tab for the selected account. From the **Subscriptions** tab, select *<span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span>* from the **Subscribe to** list and click **Subscribe**. For additional details on subscribing to the <span class="mc-variable my_project_variables.Advanced_Routing variable">Advanced Routing</span> application, refer to <a href="../c_st_configuration/t_st_subscribe_advanced_routing_application" class="MCXref xref">Subscribe to Advanced Routing application</a>. For details on managing subscriptions, refer to
<a href="../../accounts/c_st_subscriptions/t_st_subscriptions" class="MCXref xref">Manage subscriptions</a>.
