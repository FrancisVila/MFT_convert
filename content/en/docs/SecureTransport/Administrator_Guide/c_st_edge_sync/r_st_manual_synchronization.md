{
    "title": "Manual synchronization",
    "linkTitle": "Manual synchronization",
    "weight": "110"
}You can also propagate configuration information across a Standard Cluster (SC) by synchronizing the
secondary servers from the primary server manually.

A full synchronization can take some time to complete, so perform it when your
<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> system is not under heavy load.

Perform manual synchronization after you:

-   Upgrade <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge
-   Restart all the <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers
-   Restore a failed primary <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge server
-   Add or update administrators or administrative roles, either using the Administration
    Tool or by importing account configuration
-   Add or remove <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edge servers
-   Change the primary server
-   Restart the Administration Tool server on a secondary <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>
    Edge server, if you made changes using the Administration Tool on the primary server
    while it was down
