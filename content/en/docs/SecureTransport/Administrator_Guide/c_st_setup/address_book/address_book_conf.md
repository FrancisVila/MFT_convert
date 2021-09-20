{
    "title": "Address Book configuration settings",
    "linkTitle": "Address Book configuration settings",
    "weight": "340"
}The Address Book data source configurations are arranged hierarchically in three levels. The first level of configuration is the global level, the second level is business unit level, and the third level is the account level. Each level deeper is able to either inherit or override the settings of the upper level Address Book configurations.

Example:

A custom source “MSSQL DS” is enabled at the global level and then “MSSQL DS” is assigned to a business unit. For this business unit, the SecureTransport administrator is able to enable or disable the source, specify the group property, and set permissions if these settings can be overridden for underlying accounts by delegated administrators. All these settings are taken with higher precedence than the global settings.

The order of the Address Book data source hierarchy is:

-   Account level
    -   Business unit level
        -   Global level

## <span id="Address"></span>Address Book global configuration

The Address Book global configuration consists of enabling the Address Book feature and configuring the global level Address Book settings.

### Address Book server configuration settings

By default the Address Book feature is not enabled and Address Book sources global configuration page is hidden. Additionally, the business unit and account level address features are hidden by default. To enable the address book feature:

1.  Navigate to **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
2.  Search for the `AddressBook.Enabled` configuration parameter.
3.  Click the **Edit** (![Edit](SaveIcon_13x13.png)) icon in the *Edit* column.
4.  Change the `AddressBook.Enabled` configuration parameter to **true**.
5.  Click the **Save** (![](SaveIcon_13x13.png)) icon in the *Edit* column.

For more information on changing server configuration parameters, refer to [View and change server configuration parameters](../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).

All Address Book configuration settings are stored under the `AddressBook` namespace in the server configuration:

-   `AddressBook.Enabled` - Enable or disable Address Book functionality. When enabled, the Address Book user interfaces appear in the Administration Tool, allowing configuration on global, business unit, and account levels. New REST API endpoints also become available for configuring and querying the Address Book. When disabled the Address Book related UI is hidden, REST API endpoints return empty result set to the client, and all Address Book related configuration settings (described below) are not taken into consideration.
-   `AddressBook.AllowCollaboration` - Default setting for controlling Address Book collaboration with external recipients. This setting can be set from the Address Book global setting **Setup> Address Books> Allow collaboration with non-Address Book recipients** and can be overridden on the business unit and account levels. If Address Book functionality is disabled (`AddressBook.Enabled` is set to **false**) this setting does not affect user collaboration.
-   `AddressBook.Limit.AdHoc.Recipients` - The total number of recipients allowed for AdHoc packages and Shared Folders collaboration. If the recipient count exceeds this value, an error will be returned to the client. The default value is **100**.
-   `AddressBook.Limit.DefaultDisplayEntries` - Specifies the default limit of Address Book entries displayed to the user if no limit is specified in the request. The default value is **10**.
-   `AddressBook.Limit.MaxDisplayEntries` - Specifies the maximum number of Address Book entries returned by the server in a single response. The default value is **100**.
-   `AddressBook.Limit.MaxDisplayPages` - Specifies the maximum number of Address Book pages in a single request. The maximum number of entries returned by an Address Book source is the multiplication of this value and `AddressBook.Limit.MaxDisplayEntries`. The default value is **100**.
-   `AddressBook.Search.Min.Length` - Specifies the minimum search string length when performing wildcard search for Address Book entries. The default value is **3**.

### Address Book global sources list configuration

You can configure (enable and disable) Address Book data sources, define a parent group for each resource, and specify if allow collaboration is enabled for the whole system. You cannot add or remove Address Books from the Address Book Sources List on the *Address Book Sources* page because of the Address Book provider auto-discovery registration process. This process works the following way – in order to add a new address book source, the address book provider implementation package must be placed inside the `<FILEDRIVEHOME>/lib/jars` folder. On Transaction Manager startup, the provider is dynamically loaded and any new Address Book sources are registered into the SecureTransport system.

To view and configure the global Address Book sources list:

Navigate to **Setup &gt; Address Books**.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <em>Address Book Sources</em> page is only displayed if the Address Book feature is enabled (the value of the <code>AddressBook.Enabled</code> configuration option is set to <strong>true</strong>).         </td>
      </tr>
</table>

#### Enable an Address Book source

1.  Select the Address Book source to enable.
2.  Click **Enable**.

#### Disable an Address Book source

1.  Select the Address Book source to disable.
2.  Click **Disable**.

#### Edit the Local source

1.  Click the **Edit** icon (![Edit](SaveIcon_13x13.png)).
2.  Select the **Business Unit** source from the *Source Type* menu. Select either **All Business Units** or **User's own business unit**. If the local source type is **All Business Units**, the user can send emails to all SecureTransport accounts that have email addresses configured. If the local source type is **User's own business unit**, the user can send emails only to accounts in the same business unit.
3.  Edit the **Parent Display Group**.
4.  Click the **Save** icon (![Save](SaveIcon_13x13.png)).

#### Edit the LDAP source

1.  Click the **Edit** icon (![Edit](SaveIcon_13x13.png)).
2.  Select the **Domain** from the *Source Type* menu.
3.  Edit the **Parent Display Group**.
4.  Click the **Save** icon (![Save](SaveIcon_13x13.png)).

#### Edit a Custom source

1.  Click the **Edit** icon (![Edit](SaveIcon_13x13.png)).
2.  Edit the **Parent Display Group**.
3.  Click the **Save** icon (![Save](SaveIcon_13x13.png)).

#### Allow collaboration with non-Address Book recipients

1.  Select **Allow collaboration with non-Address Book recipients**.
    -   When **checked**, accounts that use the global Address Book policy will be allowed to send email packages and share folders with users that do not exist the defined Address Book.
    -   When **unchecked**, accounts that use the global Address Book policy will be allowed to send email packages and share folders only with users that exist in the defined Address Book.

      
    This global setting can be overridden on business unit and account configuration levels.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Users will be able to share folders when <strong>Allow collaboration with non-Address Book recipients</strong> is checked (enabled), only if the <code>SharedFolders.AllowCollaboration</code> server configuration parameter is set to <strong>true</strong>. For more information on changing server configuration parameters, refer to <a href="../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters">View and change server configuration parameters</a>.         </td>
      </tr>
</table>

## <span id="Address3"></span>Address Book business unit level configuration

At the business level, SecureTransport administrators can configure the following settings:

-   Address Book Sources - Address Book Policy that will apply for the current business unit.
    -   Default - When **Default** is selected, the business unit inherits either its parent's Address Book policy or the global Address Book policy if it is a top level business unit.
    -   Custom - When **Custom** is selected, a custom Address Book policy configuration will be set for this business unit only. A list of all registered Address Books is displayed and for each the administrator is able to:
        -   Enable or disable Address Book sources for the business unit.
        -   Specify the parent group for a given Address Book source.
        -   Specify the domain for LDAP Address Book sources.
        -   Specify **All Business Units** or **User's own business unit** for local and custom Address Book sources.
    -   Disabled - When **Disabled** is selected, the Address Book policy is set to disabled for this business unit.
-   Allow collaboration with non-Address Book recipients - Enable address book collaboration. If Address Book functionality is disabled, this setting does not affect user collaboration.
    -   When **checked**, accounts that use the Address Book policy defined on the business unit level will be allowed to send email packages and share folders with users that do not exist the defined Address Book.
    -   When **unchecked**, accounts that use the Address Book policy defined on the business unit level will be allowed to send email packages and share folders only with users that exist in the defined Address Book.

      
    This business unit setting overrides the global Address Book policy setting for collaboration. This setting can be overridden on the account level if **Allow modifying of the Collaboration setting** is checked.  
    
    Users will be able to share folders when **Allow collaboration with non-Address Book recipients** is checked (enabled), only if the `SharedFolders.AllowCollaboration` server configuration parameter is set to **true**. For more information on changing server configuration parameters, refer to [View and change server configuration parameters](../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).

<!-- -->

-   Allow modifying of the Collaboration setting - Allow Address Book Collaboration setting modification.
    -   When **checked**, accounts that use the Address Book policy defined in this business unit will be allowed to override the **Allow collaboration with non-Address Book recipients** setting specified here.
    -   When **unchecked**, accounts that use the Address Book policy defined in this business unit will be not allowed to override the **Allow collaboration with non-Address Book recipients** setting specified here.
-   Allow Address Book source settings modifying - Allow Address Book Policy modification.
    -   When **checked**, accounts that use the Address Book policy defined in this business unit will be allowed to override the Address Book Sources specified here.
    -   When **unchecked**, accounts that use the Address Book policy defined on business unit will be not allowed to override the Address Book Sources specified here.

## <span id="Address2"></span>Address Book account level configuration

At the account level, SecureTransport administrators can configure the following settings:

-   Address Book Sources - Address Book policy that will apply for the current account.
    -   Default - When **Default** is selected, the account inherits either its business unit Address Book policy or the global Address Book policy.
    -   Custom - When **Custom** is selected, a custom Address Book policy configuration will be set for this account only.
        -   Enable or disable Address Book sources for the account.
        -   Specify the parent group for a given Address Book source.
        -   Specify the domain for LDAP Address Book sources.
        -   Specify **All Business Units** or **User's own business unit** for local and custom Address Book sources.
    -   Disabled - When **Disabled** is selected, the Address Book policy is set to disabled for this account.
-   Allow collaboration with non-Address Book recipients - Enables Address Book collaboration with non-Address Book recipients. If Address Book functionality is disabled, this setting does not affect user collaboration.
    -   When **checked**, the account will be allowed to send email packages and share folders with users that do not exist in the defined Address Book.
    -   When **unchecked**, the account will be allowed to send email packages and share folders only with users that exist in the defined Address Book.

      
    This account setting overrides the business unit or global Address Book Policy setting for collaboration.  
    
    Users will be able to share folders when **Allow collaboration with non-Address Book recipients** is checked (enabled), only if the `SharedFolders.AllowCollaboration` server configuration parameter is set to **true**. For more information on changing server configuration parameters, refer to [View and change server configuration parameters](../../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationparameters).
