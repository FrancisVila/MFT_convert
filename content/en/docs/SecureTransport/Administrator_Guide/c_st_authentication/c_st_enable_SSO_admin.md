{
    "title": "Enable Single Sign-On (SSO) for administrators",
    "linkTitle": "Enable Single Sign-On (SSO) for administrators",
    "weight": "150"
}The following steps are the general configuration steps to enable SSO functionality for administrators in SecureTransport.

1.  Navigate to **Authentication > Login Settings**.
2.  In *Administrator login options* pane, select **Required** for *SSO*.
3.  Click **Save**.

## Configure Single Sign-On (SSO) for administrators

Before configuring SSO for administrators, refer to <a href="../c_st_sso_configuration#Configur" class="MCXref xref">SecureTransport Single Sign-On (SSO) configuration prerequisites</a>.

In order to configure SSO functionality for administrators, you need to update the `sso-admin.xml` file and remember that SSO authenticated administrators are only mapped to existing <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> administrator accounts. For additional information, refer to <a href="../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts/t_st_add_administrator_account" class="MCXref xref">Add an administrator account</a>.

> **Note:**
>
> Do not rename the sso-admin.xml configuration file.

> **Note:**
>
> SecureTransport only supports SAML-based Identity providers for SSO for administrators.

> **Note:**
>
> The following configuration steps describe the setup of a single Identity provider. For multiple Identity Provider configuration, refer to Multiple Identity Provider configuration.

> **Note:**
>
> Before configuring SSO for Administrators using a SAML-based Identity Provider, make sure that you configured it properly.

Configure SSO for administrators using SAML-based Identity Providers:

1.  Download the SAML-based Identity Provider metadata file from your Identity Provider instance.  

    > **Note:**
    >
    > Do not modify the SAML-based Identity Provider metadata file.

2.  Open the `sso-admin.xml` file. The following changes are required:
    -   In the `SamlIdentityProvider` element, change the following attribute values:
        -   `metadataUrl` to be `./(name of the SAML-based Identity provider metadata file)`
        -   `entityId` - add the `<EntityDescriptor>` element `entityID` attribute value, from the SAML-based Identity Provider metadata file.
    -   `Mappings` element: Both `<FilterMapping>` and `<RenameMapping>` elements are not applicable for administrators.
    -   `Features` element: The recommended features are listed in <a href="../../r_st_sample_admin" class="MCXref xref">Sample SSO configuration file for administrators</a>.

3.  Save the `sso-admin.xml` file.

4.  Zip the `sso-admin.xml` file and the SAML-based Identity Provider metadata file from Step 1.  

    > **Note:**
    >
    > Do not put the configuration files in a sub-directory inside the ZIP file.

5.  Navigate to **Operations > Server Configuration**. Click on **Configuration Files**.

6.  Select the **Browse** button for SSO Configuration Files. Choose the ZIP file containing the `sso-admin.xml` file and the SAML-based Identity Provider metadata file.

7.  Click on the check box for **SSO Configuration Files**.

8.  Click **Upload**.

9.  Restart the admin service.

> **Note:**
>
> If, for some reasons after importing SSO configuration files and enabling SSO for administrators, you are still redirected to the default Administrator login page, perhaps there is some misconfiguration. To resolve this situation you can use SecureTransport as an Identity provider to login with the local stored credentials and troubleshoot. For more information, refer to SecureTransport as an Identity Provider.

> **Note:**
>
> In both Standard Clusters and Enterprise Clusters, after successfully importing the SSO configuration files, they will be automatically redistributed across all nodes in the cluster. Restart of admin service is required on all nodes.

> **Note:**
>
> In cluster environment SecureTransport will always redirect to the node that is configured in the Service Provider, even if the request came from a different node.

> **Note:**
>
> Due to the limitation of having only one Service Provider entity ID for the sso-admin.xml configuration file and the fact that configuration files are synced between the cluster nodes, all administrators will have the same service provider configuration. Since the IdP cannot differentiate which request is coming from which node, it will always return the user to the assertion consumer service configured on the IdP.
> This could be worked around by having a separate IdP for each cluster node and the user could select the node they want to login to by choosing the dedicated IdP. For more information about how to configure multiple Identity Provider in SecureTransport, refer to Multiple Identity Provider configuration.

## Single Sign-On (SSO) administrators configuration

For more information about how to setup the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> administrators to use SSO, refer to <a href="../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts" class="MCXref xref">Manage administrator accounts</a>.
