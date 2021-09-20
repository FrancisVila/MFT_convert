{
    "title": "Enable Single Sign-On (SSO) for administrators",
    "linkTitle": "Enable Single Sign-On (SSO) for administrators",
    "weight": "160"
}The following steps are the general configuration steps to enable SSO functionality for administrators in SecureTransport.

1.  Navigate to **Authentication > Login Settings**.
2.  In *Administrator login options* pane, select **Required** for *SSO*.
3.  Click **Save**.

## Configure Single Sign-On (SSO) for administrators

Before configuring SSO for administrators, refer to [SecureTransport Single Sign-On (SSO) configuration prerequisites](../c_st_sso_configuration).

In order to configure SSO functionality for administrators, you need to update the `sso-admin.xml` file and remember that SSO authenticated administrators are only mapped to existing SecureTransport administrator accounts. For additional information, refer to [Add an administrator account](../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts/t_st_add_administrator_account).

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not rename the <code>sso-admin.xml</code> configuration file.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>SecureTransport</span> only supports SAML-based Identity providers for SSO for administrators.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The following configuration steps describe the setup of a single Identity provider. For multiple Identity Provider configuration, refer to <a href="../c_st_multi_idp" xrefformat="{paratext}">Multiple Identity Provider configuration</a>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Before configuring SSO for Administrators using a SAML-based Identity Provider, make sure that you configured it properly.         </td>
      </tr>
</table>

Configure SSO for administrators using SAML-based Identity Providers:

1.  Download the SAML-based Identity Provider metadata file from your Identity Provider instance.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not modify the SAML-based Identity Provider metadata file.         </td>
      </tr>
</table>

2.  Open the `sso-admin.xml` file. The following changes are required:
    -   In the `SamlIdentityProvider` element, change the following attribute values:
        -   `metadataUrl` to be `./(name of the SAML-based Identity provider metadata file)`
        -   `entityId` - add the `<EntityDescriptor>` element `entityID` attribute value, from the SAML-based Identity Provider metadata file.
    -   `Mappings` element: Both `<FilterMapping>` and `<RenameMapping>` elements are not applicable for administrators.
    -   `Features` element: The recommended features are listed in [Sample SSO configuration file for administrators](../../r_st_sample_admin).

3.  Save the `sso-admin.xml` file.

4.  Zip the `sso-admin.xml` file and the SAML-based Identity Provider metadata file from Step 1.  
    

    <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Do not put the configuration files in a sub-directory inside the ZIP file.         </td>
      </tr>
</table>

5.  Navigate to **Operations > Server Configuration**. Click on **Configuration Files**.

6.  Select the **Browse** button for SSO Configuration Files. Choose the ZIP file containing the `sso-admin.xml` file and the SAML-based Identity Provider metadata file.

7.  Click on the check box for **SSO Configuration Files**.

8.  Click **Upload**.

9.  Restart the admin service.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If, for some reasons after importing SSO configuration files and enabling SSO for administrators, you are still redirected to the default  Administrator login page, perhaps there is some misconfiguration. To resolve this situation you can use  SecureTransport as an Identity provider to login with the local stored credentials and troubleshoot. For more information, refer to <a href="../c_st_identity_provider" xrefformat="{paratext}">SecureTransport as an Identity Provider</a>.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In both Standard Clusters and Enterprise Clusters, after successfully importing the SSO configuration files, they will be automatically redistributed across all nodes in the cluster. Restart of admin service is required on all nodes.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In cluster environment <span>SecureTransport</span> will always redirect to the node that is configured in the Service Provider, even if the request came from a different node.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Due to the limitation of having only one Service Provider entity ID for the <code>sso-admin.xml</code> configuration file and the fact that configuration files are synced between the cluster nodes, all administrators will have the same service provider configuration. Since the IdP cannot differentiate which request is coming from which node, it will always return the user to the assertion consumer service configured on the IdP.
		This could be worked around by having a separate IdP for each cluster node and the user could select the node they want to login to by choosing the dedicated IdP. For more information about how to configure multiple Identity Provider in SecureTransport, refer to <a href="../c_st_multi_idp" xrefformat="{paratext}">Multiple Identity Provider configuration</a>.         </td>
      </tr>
</table>

## Single Sign-On (SSO) administrators configuration

For more information about how to setup the SecureTransport administrators to use SSO, refer to [Manage administrator accounts](../../c_st_advancedaccountadministration/c_st_manageadministratoraccounts).
