{
    "title": "Pluggable transfer sites",
    "linkTitle": "Pluggable transfer sites",
    "weight": "310"
}Pluggable Transfer Sites (connectors) are custom plug-ins that can be deployed on the SecureTransport Server to allow sending and receiving files over various protocols.

Once deployed, the connector adds a new Transfer Site to the list of Transfer Sites available for the user accounts.

A collection of Transfer Site plug-ins for SecureTransport can be found in the [AMPLIFY Repository](https://repository.axway.com/).

Pluggable Transfer sites are deployed on all SecureTransport Server nodes, into the following folder `${FILEDRIVE_HOME}/plugins/transferSites`.

For more information on Pluggable Transfer sites, refer to the SecureTransport Developer’s Guide.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">When using expressions to configure a Pluggable Transfer site there is a difference in the variable spaces, depending on the account type – e.g.         </td>
      </tr>
</table>

-   With standard User Accounts, the flow attributes of a file would be accessible with expression in the following format: `${ts['userVars.test']}`  
    **Note** The `${ts['userVars.test']}` expression is applicable only for evaluating Upload folder and a post-transmission action (PTA); and does not work with Download folder and pattern.  
-   With User Account Templates, the flow attributes of a file would be accessible with expression in the following format: `${stenv['DXAGENT_SUBSCRIPTION_ATTR_userVars_folder']}`
