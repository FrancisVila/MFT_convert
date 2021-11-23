{
    "title": "Authentication",
    "linkTitle": "Authentication",
    "weight": "300"
}The following authentication methods are valid for connecting to a remote site for the different protocols.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadD-Column1-Header1">Authentication method         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>AS2         </td>
         <td>(no authentication)         </td>
      </tr>
      <tr>
         <td>FTP         </td>
         <td>User name + password<br />
User name + password + certificate<br />
User name + certificate         </td>
      </tr>
      <tr>
         <td>HTTP         </td>
         <td><p>User name + password<br />
User name + password + certificate<br />
User name + certificate<br />
Certificate</p>         </td>
      </tr>
      <tr>
         <td>SSO         </td>
         <td>User name + password (for more information see SSO Limitations)         </td>
      </tr>
      <tr>
         <td>PeSIT         </td>
         <td>(no authentication)<br />
User name + password<br />
User name + password + certificate<br />
User name + certificate         </td>
      </tr>
      <tr>
         <td>SSH         </td>
         <td>User name + password<br />
User name + password + SSH key<br />
User name + SSH key         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> If dual authentication is enabled, the key and password are required. If user classes are specified in Specific user classes, the key and password are required only for the specified classes.

You can configure the user name and password in the proxy configuration in a network zone node. See [Specify proxy settings in a network zone](../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify3).

**Related topics:**

-   [Transfer mode for server-initiated transfers](../c_st_transfer_mode_for_server-initiated_transfers)
-   [Transfer multiple files](../c_st_transfer_multiple_files)
-   [Configure retry parameters for server-initiated transfers](../c_st_configure_retry_parameters_for_server-initiated_transfers)
-   [Outgoing connections](../c_st_outgoing_connections)
-   [Server authentication](../c_st_server_authentication)
-   [Limitations](../c_st_limitations)
-   [Encryption and server-initiated transfers](../c_st_encryption_server-initiated_transfers)
