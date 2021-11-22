{
    "title": "Enable Single Sign-On (SSO) for end-users",
    "linkTitle": "Enable Single Sign-On (SSO) for end-users",
    "weight": "160"
}The following steps are the general configuration steps to enable SSO functionality for end-users in {{< SecureTransport/componentshortname  >}}.

1.  Navigate to **Authentication > Login Settings**.
2.  In *End-users login options* pane, select **Required** for *SSO*.
3.  Click **Save**.

> **Note:**
>
> When SSO for end-users is enabled, the following configuration options will be updated automatically:

1.  `Http.FdxAuthReply` with value **PREAUTH**.
2.  `Http.AllowedAuthenticationParameters` with value **SAMLResponse;RelayState**.
3.  `AllowedAuthenticationParametersMaxSize` with value **32768**.

## Configure Single Sign-On (SSO) for end-users

The following configuration steps describe the setup of the single Identity provider. For multiple Identity Provider configuration, refer to <a href="../c_st_multi_idp#Multiple" class="MCXref xref">Multiple Identity Provider configuration</a>.

Before configuring SSO for end-users, ensure that all <a href="../c_st_sso_configuration#Configur" class="MCXref xref">SecureTransport Single Sign-On (SSO) configuration prerequisites</a> are met and the Identity provider is configured properly. For a full list of supported Identity providers, refer to <a href="../../overview/r_st_axway_and_third-party_software_support#Single" class="MCXref xref">Single Sign-On (SSO)</a>.

In order to configure SSO functionality for end-users, you need to update the `sso-enduser.xml` file and remember that SSO authenticated users are only mapped to existing {{< SecureTransport/componentshortname  >}} [user accounts](../../accounts/useraccounts/t_st_create_user_account) or [account templates](../../c_st_advancedaccountadministration/c_st_accounttemplates) with [user classes](../../c_st_accesscontrol/c_st_userclasses).

> **Note:**
>
> Do not rename the sso-enduser.xml configuration file.

To configure SSO for End-users using SAML-based Identity provider:

1.  Download the SAML-based Identity provider metadata file from your Identity Provider instance.  

    > **Note:**
    >
    > Do not modify the SAML-based Identity Provider metadata file.

2.  Open the `sso-enduser.xml` file. The following changes are required:
    -   In the `<SamlIdentityProvider>` element, change the following attribute values:
        -   `metadataUrl` to be `./(name of the SAML-based Identity provider metadata file)`
        -   `entityId` - add the `<EntityDescriptor>` element `entityID` attribute value, from the SAML-based Identity Provider metadata file.
    -   `<Mappings>` element:
        -   `FilterMapping` - For information on filter mapping, refer to the <a href="../../r_st_sso_filter_mapping" class="MCXref xref">SSO filter mapping</a>.
        -   `RenameMapping` – For mapping custom attributes from an Identity Provider, refer to <a href="../c_st_sso_configuration#Accessin" class="MCXref xref">Accessing Single Sign-On (SSO) attributes</a>.
    -   `<Features>` element: The recommended features are listed in <a href="../../r_st_sample_end-users" class="MCXref xref">Sample SSO configuration file for end-users</a>.

3.  Save the `sso-enduser.xml` file.

4.  Zip the `sso-enduser.xml `and the SAML-based Identity Provider metadata file from Step 1.  

    > **Note:**
    >
    > Do not put the configuration files in a sub-directory inside the ZIP file.

5.  Navigate to **Operations > Server Configuration**. Click on **Configuration Files**.

6.  Select the **Browse** button for SSO Configuration Files. Choose the ZIP file containing the `sso-enduser.xml` file and the SAML-based Identity Provider metadata file.

7.  Click on the check box for **SSO Configuration Files**.

8.  Click **Upload**.

9.  Restart the Transaction Manager service and the HTTP service.

Configure SSO for end-users using Kerberos:

1.  Configure Kerberos as an Identity provider. For the configuration with Kerberos as an Identity Provider, refer to <a href="../c_st_active_directory" class="MCXref xref">Configure Kerberos as an Identity Provider in SecureTransport</a>.

2.  Open the `sso-enduser.xml` file. The following changes are required:

3.  In `KerberosdentityProvider` element change the following attribute values:
    -   `configurationUrl` to be the absolute path to the Kerberos `.conf` file.

    -   **Note:**
        >
        > The Kerberos .conf file and .keytab file should be added to the SSO configuration ZIP file.

    -   `entityId` - add the `entityID` attribute value

    -   `<Mappings>` element:
        -   `FilterMapping` – For information on filter mapping, refer to the <a href="../../r_st_sso_filter_mapping" class="MCXref xref">SSO filter mapping</a>.
        -   `RenameMapping` – For mapping custom attributes from an Identity Provider, refer to <a href="../c_st_sso_configuration#Accessin" class="MCXref xref">Accessing Single Sign-On (SSO) attributes</a>.

    -   `<Features>` element: The recommended features are listed in <a href="../../r_st_sample_end-users" class="MCXref xref">Sample SSO configuration file for end-users</a>.

4.  Save the `sso-enduser.xml` file.

5.  Zip the `sso-enduser.xml` and all additional files (the Kerberos configuration file and the `.keytab` file).  

    > **Note:**
    >
    > Do not put the configuration files in a sub-directory inside the ZIP file.

6.  Navigate to **Operations > Server Configuration**. Click on **Configuration Files**.

7.  Select the **Browse** button for SSO Configuration Files. Choose the ZIP file containing the `sso-enduser.xml` and the Identity provider metadata file.

8.  Click on the check box for **SSO Configuration Files**.

9.  Click **Upload**.

10. Restart the Transaction Manager service and the HTTP service.

> **Note:**
>
> If, for some reasons after importing SSO configuration files and enable SSO for end-users you still redirect to default SecureTransport end-users login page, perhaps there is some misconfiguration. To resolve this situation you can use SecureTransport as an Identity provider to login with the local stored credentials and troubleshoot. For more information, refer to SecureTransport as an Identity Provider.

> **Note:**
>
> In both Standard Cluster and Enterprise Cluster, after successfully importing the SSO Configuration files, they will be automatically redistributed across all nodes in the cluster. Restart operation is required of Transaction Manager service on all nodes.

> **Note:**
>
> SSO for end-users can be configured using only sso-enduser.xml file only for backend instance.

> **Note:**
>
> Due to the limitation of having only one Service Provider entity ID for the sso-enduser.xml configuration file and the fact that configuration files are synced between the cluster nodes, all end-users will have the same service provider configuration. Since the IdP cannot differentiate which request is coming from which node, it will always return the user to the assertion consumer service configured on the IdP.
> This could be worked around by having a separate IdP for each cluster node and the user could select the node they want to login to by choosing the dedicated IdP. For more information about how to configure multiple Identity Provider in SecureTransport, refer to Multiple Identity Provider configuration.

## Single Sign-On (SSO) account configuration

For more information about how to configure {{< SecureTransport/componentshortname  >}} accounts with SSO, refer to <a href="../../accounts" class="MCXref xref">Manage Accounts</a> and <a href="../../c_st_advancedaccountadministration" class="MCXref xref">Advanced account administration</a>.
