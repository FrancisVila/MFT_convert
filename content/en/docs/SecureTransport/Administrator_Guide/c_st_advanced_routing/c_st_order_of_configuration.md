{
    "title": "Order of configuration",
    "linkTitle": "Order of configuration",
    "weight": "180"
}This topic provides the configuration order for the {{< SecureTransport/advancedrouting  >}} feature. It also provides a brief overview of each configuration item.

Business units can be created prior to configuring the Route Package Template. For configuration information, refer to [Manage business units]()

Optionally, an {{< SecureTransport/advancedrouting  >}} administrator can be created. For configuration information, refer to [Advanced Routing delegated administrator](../c_st_configuration/t_st_create_delegated_administrator) and to [Advanced Routing delegated administrator](../c_st_configuration/t_st_create_delegated_administrator).

The {{< SecureTransport/advancedrouting  >}} feature should be configured in the following order:

1.  Create user account (or account template) or use an existing one. See .
2.  Create {{< SecureTransport/advancedrouting >}} application. See [Create Advanced Routing application](../c_st_configuration/t_st_create_advanced_routing_application).
3.  Create Route Package Template.
4.  Assign Route Package Template to the account from Step 1. See [Assign Route Package Template](../c_st_configuration/t_st_assign_route_package_template).
5.  Subscribe to the {{< SecureTransport/advancedrouting >}} application. See .

## Create {{< SecureTransport/advancedrouting  >}} administrator

In order to setup an administrator dedicated to managing the {{< SecureTransport/advancedrouting  >}} application and Route Package Templates it is necessary to create an {{< SecureTransport/advancedrouting  >}} administrator with file tracking, accounts, applications, mail templates, and routes privileges. For instructions on creating an {{< SecureTransport/advancedrouting  >}} administrator, refer to [Advanced Routing delegated administrator](../c_st_configuration/t_st_create_delegated_administrator).

## Create user accounts

In order to subscribe an account to an {{< SecureTransport/advancedrouting  >}} application instance, start off by creating a {{< SecureTransport/componentshortname  >}} user account or account template (or use an existing one). For information on creating user accounts, refer to [Create a user account](../../accounts/useraccounts/t_st_create_user_account). For information on creating account templates, refer to [Manage account templates](../../c_st_advancedaccountadministration/c_st_accounttemplates/t_st_accounttemplates)

## Create {{< SecureTransport/advancedrouting  >}} application

Navigate to the **Application** tab and click **Add New**. Specify the preferred **Application Name** for the {{< SecureTransport/advancedrouting  >}} application instance. Select *{{< SecureTransport/advancedrouting  >}}* from the **Application Type** combo box. For additional information on creating an {{< SecureTransport/advancedrouting  >}} application instance, refer to [Create Advanced Routing application](../c_st_configuration/t_st_create_advanced_routing_application).

## Create Route Package Template

Navigate to the **Routes** tab and click **New Route Package Template**. Specify the preferred **Route Package Template Name** for the Route Package Template, determine assigned business units, enter a route template description, determine execution routes, add transformation and routing steps, and determine notifications. For additional information

## Assign Route Package Template

You must subscribe the selected user to the {{< SecureTransport/advancedrouting  >}} application prior to assigning the user a Route Package Template. To assign the user a Route Package Template, navigate to **Accounts &gt; User Accounts**, select the desired user account, and then select the **Routes** tab for the selected account. From the *Routes* tab, select the desired Route Package Template from the **Route Package Template** list and then click **Assign Route**. The *Create Route Package* screen is displayed with a link to the selected Route Package Template under the **Created From** label. For more details on assigning a Route Package Template, refer to [Assign Route Package Template](../c_st_configuration/t_st_assign_route_package_template).

## Subscribe to {{< SecureTransport/advancedrouting  >}} application

To subscribe a user account to the {{< SecureTransport/advancedrouting  >}} application, navigate to **Accounts &gt; User Accounts**, select the desired user account, and then select the **Subscriptions** tab for the selected account. From the **Subscriptions** tab, select *{{< SecureTransport/advancedrouting  >}}* from the **Subscribe to** list and click **Subscribe**. For additional details on subscribing to the {{< SecureTransport/advancedrouting  >}} application, refer to [Subscribe to Advanced Routing application](../c_st_configuration/t_st_subscribe_advanced_routing_application). For details on managing subscriptions, refer to
[Manage subscriptions](../../accounts/c_st_subscriptions/t_st_subscriptions).
