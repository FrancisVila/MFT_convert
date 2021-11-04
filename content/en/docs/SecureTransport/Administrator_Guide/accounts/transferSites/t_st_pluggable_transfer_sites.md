{
    "title": "Pluggable Transfer Sites",
    "linkTitle": "Pluggable transfer sites",
    "weight": "300"
}Pluggable Transfer Sites (connectors) are custom plug-ins that can be deployed on the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to allow sending and receiving files over various protocols.

Once deployed, the connector adds a new Transfer Site to the list of Transfer Sites available for the user accounts.

A collection of Transfer Site plug-ins for <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can be found in the [AMPLIFY Repository](https://repository.axway.com/).

Pluggable Transfer sites are deployed on all <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server nodes, into the following folder `${FILEDRIVE_HOME}/plugins/transferSites`.

For more information on Pluggable Transfer sites, refer to the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Developer’s Guide.

> **Note:**
>
> When using expressions to configure a Pluggable Transfer site there is a difference in the variable spaces, depending on the account type – e.g.

-   With standard User Accounts, the flow attributes of a file would be accessible with expression in the following format: `${ts['userVars.test']}`  
    **Note** The `${ts['userVars.test']}` expression is applicable only for evaluating Upload folder and a post-transmission action (PTA); and does not work with Download folder and pattern.  
-   With User Account Templates, the flow attributes of a file would be accessible with expression in the following format: `${stenv['DXAGENT_SUBSCRIPTION_ATTR_userVars_folder']}`
