{
    "title": "Transfer CFT  server and HACMP",
    "linkTitle": "Transfer CFT server and HACMP",
    "weight": "260"
}## <span id="HACMP_monitoring_commands"></span>HACMP monitoring commands

### Clstat

clstat
: clstat \[-c cluster ID\] \[ -r seconds\] \[-i\]

Clstat indicates if the cluster is started, stopped, or in an unstable
state. It also indicates if the nodes are in the process of joining or
quitting the cluster, or if they are in reconfiguration. Operational details
of each node are also displayed.

Example of ASCII operation

clstat
- HACMP for AIX Cluster Status Monitor

---------------------------------------------

Cluster:
axway (666) Thu Jan 15 18:00:37 NFT 2004

State:
DOWN Nodes: 2

SubState:
UNSTABLE

Node:
hacmp1 State: DOWN

Interface:
hacmp1-enboot (0) Address: 172.17.2.8

State:
DOWN

Node:
hacmp2 State: DOWN

Interface:
hacmp2-enboot (0) Address: 172.17.2.18

State:
DOWN

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*
f/forward, b/back, r/refresh, q/quit\*\*\*\*\*\*\*\*\*\*\*

### Clfindres

-   clfindres:
    clfindres \[-s\] \[resgroup1\] \[resgroup2\] ...

clfindres displays the resource groups of the cluster.

Example of ASCII display

----------------------------------------------------------------

GroupName
Type State Location

---------
------ --------

CFT-rg:
cascading UP hacmp1

---------------------------------------------------------------

### <span id="Starting_up_the_service"></span>Starting the service

Start-up service commands include:

-   /usr/sbin/cluster/etc/rc.cluster

This script is called by inittab if "Start
at system restart" has been selected in the smitty "Start Cluster
Services" screen.  
rc.cluster executes verifications, starts the clinfo demon, then emits
the command: /usr/sbin/cluster/utilities/clstart.

-   /usr/sbin/cluster/utilities/clstart

Start HACMP with the options specified in the smitty
"Start Cluster Services" screen.

### <span id="Stopping_the_service"></span>Stopping the service

The stop service command is:

/usr/sbin/cluster/utilities/clstop

Stop HACMP services with the options specified in the smitty "Stop
Cluster Services" screen.
