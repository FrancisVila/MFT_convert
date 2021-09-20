{
    "title": "Manual synchronization",
    "linkTitle": "Manual synchronization",
    "weight": "120"
}You can also propagate configuration information across a Standard Cluster (SC) by synchronizing the
secondary servers from the primary server manually.

A full synchronization can take some time to complete, so perform it when your
SecureTransport system is not under heavy load.

Perform manual synchronization after you:

-   Upgrade SecureTransport Edge
-   Restart all the SecureTransport Edge servers
-   Restore a failed primary SecureTransport Edge server
-   Add or update administrators or administrative roles, either using the Administration
    Tool or by importing account configuration
-   Add or remove SecureTransport Edge servers
-   Change the primary server
-   Restart the Administration Tool server on a secondary SecureTransport
    Edge server, if you made changes using the Administration Tool on the primary server
    while it was down
