{
    "title": "SecureTransport as an Identity Provider",
    "linkTitle": "SecureTransport as an Identity Provider",
    "weight": "210"
}Using SecureTransport as an Identity Provider allows users to use SecureTransport as an Identity Provider. The users who authenticate using SecureTransport as an Identity Provider, will authenticate using the password stored internally in the SecureTransport, and will be treated as local accounts.

The following configuration options are added in the Server Configuration options:

-   For administrators:
    -   `LoginSettings.Admin.SSO.idpResolverKey`
    -   `LoginSettings.Admin.SSO.localIdpId`
-   For end-users:
    -   `LoginSettings.EndUser.SSO.idpResolverKey`
    -   `LoginSettings.EndUser.SSO.localIdpId`

The `idpResolverKey` corresponds to the Query Parameter name attribute and can be used in both a query parameter as well as a header. This is the key that will be used when requesting local or Identity Provider authentication. The default value is: `idp_id`.

The `localIdpId` corresponds to the value in the mapping that will force SecureTransport to not trigger the SSO flow and continue with local authentication. The default value is: `ST_IDP`.

The value of these options is configurable. For more information about how to edit the Server Configuration options, refer to [Update configuration files](../../operations_menu/c_st_serverconfiguration/t_st_serverconfigurationfiles).

Example for using SecureTransport as a Identity Provider:

`https:// <ST IP>/?idp_id=ST_IDP`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Options for using SecureTransport as an Identity Provider can be used either as query parameters or for using requests with header.         </td>
      </tr>
</table>
