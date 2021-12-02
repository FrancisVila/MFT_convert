{
    "title": "Multi-node commands and management",
    "linkTitle": "Commands and management",
    "weight": "190"
}This topic describes how to mange {{< TransferCFT/componentshortname  >}} nodes, and related actions such as:

-   [Initialize internal data files](#Initiali)
-   [Start and stop the cluster](#Start)
-   [Check the status](#Check)
-   [Manage hosts](#Manage)
-   [Manage nodes](#Manage2)
-   [Rebalance the cluster after a host failure](#Rebalanc)

<span id="Initiali"></span>

## Initialize internal data files

### cftinit

The cftinit command initializes internal data files. If no option is specified, then all internal data files are initialized, both common and specific.

Syntax

cftinit \[options\] &lt;filename>\[&lt;filename>\] \[…\]

Options

-   -c |-common: only common internal data files are initialized (PARM, PART, main COM)
-   -n |-node: only node-specific internal data files are initialized (CATALOG, secondary COM, LOG)

Usage

All internal data files are initialized using provided configuration files.

```
cftinit conf/cft-tcp.conf conf/cft-tcp-part.conf
```

Only common internal data files are initialized using provided configuration files.

```
cftinit –c conf/cft-tcp.conf conf/cft-tcp-part.conf
```

Specific internal data files for node 2 are initialized (cftcata02, cftcom02, cftlog02).

```
cftinit –n 2
```
<span id="Start"></span>

## Start and stop the cluster

> **Note:**
>
> The 'cft force-stop' command is not supported in multi-node installations.

### Start a node manager

#### copstart

The copstart command starts Copilot (the node manager and the other services).

Syntax

copstart

Usage

```
copstart
```

Start all node managers

For each host perform the command: `copstart`

<span id="Stop"></span>

### Stop a node manager

#### copstop

The copstop command stops Copilot (the node manager and the other services). When stopping a Copilot on a host, all nodes running on this host are stopped and re-started on the other hosts in the cluster.

Syntax

copstop

Usage

```
copstop
```

Stop all node managers

For each host, run the command: `copstop`

### Start a node or all nodes

#### cft start

The cft start command starts one or all nodes. If no node is specified, all nodes are started.

> **Note:**
>
> Node managers must be started first.

Syntax

cft start \[options\]

Options

The -n|-node &lt;node\_id> starts the node &lt;node\_id>.

Usage

All nodes are started by the node managers.

```
cft start
```

Node 0 is started by one of the node managers.

```
cft start –n 0
```

### Stop a node or all nodes

#### cft stop

The cft stop command stops one or all nodes. If no node is specified, all nodes are stopped.

Syntax

cft stop \[options\]

Options

The -n|-node &lt;node\_id> stops the node &lt;node\_id>.

Usage

Stops all nodes.

```
cft stop
```

Stops node 0.

```
cft stop –n 0
```
<span id="Restart"></span>

### Restart a node or all nodes

#### cft restart

The cft restart command re-stars one or all nodes. If no node is specified all nodes are re-started.

> **Note:**
>
> Node managers must be started first.

Syntax

cft restart \[options\]

Options

The` -n|-node <node_id>   `re-starts the node &lt;node\_id>.

The `-ln|-local_node` re-starts all nodes hosted locally that are running on the host from where the command is performed.

Usage

All nodes are re-started by the node managers.

```
cft restart
```

Node 0 is re-started by one of the node managers.

```
cft restart –n 0
```

All hosted locally nodes are re-started by the node managers.

```
cft restart –ln
```

### Stop the {{< TransferCFT/transfercftname  >}} cluster

1.  On the first host:
    -   To stop all nodes, run: `cft stop`
    -   To stop the node manager, run: `copstop`
2.  On each additional host, stop the node manager. Run: `copstop`

### Start the {{< TransferCFT/transfercftname  >}} cluster

1.  On each host, start the node manager. Run: `copstart`
2.  On the last host, start all nodes. Run: `cft start`

## Check the status

### Check the cluster status

<span id="Multi N Listnode"></span>

#### listnode

The CFTUTIL listnode displays the status of the {{< TransferCFT/componentshortname  >}} cluster, including information about node managers (Copilots) and nodes.

Example

Enter:

```
CFTUTIL listnode
```

In this example, the four nodes running on four different hosts are displayed.

![Example screen shot of 4 nodes running on different hosts, per the description in the text.](/Images/TransferCFT/examplelistnode.png "Example screen shot of 4  nodes running on different hosts, per the description in the text.")

### Check a node manager's status

#### copstatus

The `copstatus `command checks the Copilot status.

Syntax

copstatus -v

Usage

```
copstatus -v
```

### Check all nodes' status

#### cftping

The `cftping `command checks the status of one or all enabled nodes. By default, the cftping checks status of all nodes.

Return values:

-   0: all enabled nodes are stopped
-   1: all enabled nodes are running
-   2: not all enabled nodes are running

Syntax

cftping \[options\]

Options

-   `-n|-node <node_id>`: checks the status of the node &lt;node\_id>
-   `-v`: verbose mode
-   `-p`: shows PID (Process IDs) of all CFTMAIN processes
-   `-h`: shows the help

### Check the log and transfers' status

<span id="Multi N Listlog"></span>

#### listlog

Use the `CFTUTIL listlog` command to display the log content, which can be defined according to certain criteria, such as date or node.

Additionally, you can filter the log according to multiple criteria, or view a log that is merged for several nodes in cluster mode. See [LISTLOG](../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listlog).

```
CFTUTIL listlog LINES=-200
CFTUTIL listlog node=1
```
<span id="Multi N Display"></span>

#### display/listcat

Use the `CFTUTIL display` or CFTUTIL listcat to show catalog transfer records. In multi-node, these commands aggregate all catalog internal data files to show catalog transfer records as a unique catalog. See [DISPLAY](../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/display_command), [LISTCAT](../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command).

<span id="Manage"></span>

## Manage hosts

### Add a host to the cluster

#### cft add\_host

The cft add\_host command adds a new host entry in the configuration. You must specify the hostname and a host address that is accessible from the other hosts.

Syntax

cft add\_host –hostname &lt;hostname> –host &lt;host\_address>

Usage on UNIX/Windows

1.  For the new host, run the installation executable. In the Installation architecture screen, select **Cluster-additional host.**
2.  Complete the installation.
3.  On the shared disk where runtime directory is installed, execute the profile.
4.  Execute the command add\_host:  
    ```
    cft add\_host -hostname newhost -host newhost.company.int
    ```
5.  Check that new hostname displays when listing the hosts:  
    ```
    listuconf id= cft.multi\_node.hostnames.\*
    ```
6.  Start Copilot on &lt;hostname>.

Please refer to the OS-appropriate installation guide  for installation program details.

For specifics on adding a host on z/OS platforms, please see <a href="../../cft_intro_install/about_this_document_zos/c_multinode_zos/t_vipa_multinode_zos" class="MCXref xref">Customize the VIPA and execute commands</a>.

> **Note:**
>
> The cft add\_host command automatically sets the following UCONF parameters:

-   cft.multi\_node.hostnames
-   cft.multi\_node.hostnames.&lt;hostname>.host = &lt;host\_address>

### Remove a host

#### cft remove\_host

The cft remove\_host command removes a host entry from the configuration.

Syntax

cft remove\_host –hostname &lt;hostname>

Usage on UNIX/Windows

1.  On the host to be removed, execute the profile and then stop the node manager: `copstop`
2.  Check that all Transfer CFT nodes and node manager processes are stopped on the host to be removed.
3.  Execute the following command, where &lt;host to remove> is the name of host to remove as referenced in `cft.multi_node.hostnames`:  
    ```
    cft remove\_host -hostname <host to remove>
    ```
4.  Uninstall binaries from the &lt;host to remove>.

<span id="Manage2"></span>

## Manage nodes

### Add a new node

#### cft add\_node

The cft add\_node command adds a new node to the {{< TransferCFT/componentshortname  >}} cluster. The number of nodes is incremented (uconf: cft.multi\_node.nodes = N+1) . The internal data files associated with the new node are initialized and the node state is set to DISABLED (uconf:cft.multi\_node.nodes.&lt;node\_id>.nodestate). After adding the new node, you can enable it using the command: `cft enable_node -n x`

Syntax

cft add\_node

Usage

```
cft add\_node
```

### Enable a node

<span id="Multi N enable disable"></span>

#### cft enable\_node

The cft enable\_node command enables the specified node. The node state is set from DISABLED to ENABLED\_STOPPED (uconf:cft.multi\_node.nodes.&lt;node\_id>.nodestate).

Syntax

cft enable\_node -n -&lt;node\_id>

Usage

```
cft enable\_node -n -<node\_id>
```
<span id="Disable"></span>

### Disable a node

#### cft disable\_node

The cft disable\_node command disables the node identified by the highest node id in the {{< TransferCFT/componentshortname  >}} cluster and only that node.

-   The node un-registers its listening points from the connection dispatcher so that it no longer receives incoming requests.
-   Outgoing requests coming from APIs are no longer dispatched to this node.
-   Once the catalog related to the node is empty, the node state is set to DISABLED and the node stops.

Syntax

cft disable\_node -n -&lt;node\_id>

Usage

```
cft disable\_node -n -<node\_id>
```

### Remove a node

> **Note:**
>
> You can only remove the last node.

#### cft remove\_node

The cft remove\_node command removes the node identified by the highest node id in the {{< TransferCFT/componentshortname  >}} cluster, and only that node. To remove a node, the node state must be both DISABLED (uconf:cft.multi\_node.nodes.&lt;node\_id>.nodestate) and STOPPED (uconf:cft.multi\_node.nodes.&lt;node\_id>.state). See also, [Disable a node](#Disable).

The node number is decremented (uconf: cft.multi\_node.nodes = N-1), and any internal data files associated with the node are removed.

> **Note:**
>
> After removing a node, you must restart Transfer CFT.

Syntax

cft remove\_node –n &lt;the\_highest\_node\_id>

Usage

```
cft remove\_node –n 3
```
<span id="Rebalanc"></span>

## Rebalance the cluster after a host failure

On a host failure, the nodes running on that host are automatically handle by the node managers running on the other hosts.

Once the failed host (node manager) is running again, you can rebalance the cluster by restarting one or multiple nodes.

In this example there are two hosts (host A and host B), and two nodes (node\_0 and node\_1). Node\_0 is running on host A, and node\_1 is running on host B.

1.  Host A  experiences a failure.
2.  The host A node manager re-starts the node\_0 locally.
3.  Node\_0 and node\_1 run on host B.
4.  Host A and its node manager are manually re-started.
5.  From one of the hosts, host A or host B, execute the command:` cft restart –n 0`  
    See [Restart a node](#Restart) for details.
6.  The host A node manager restarts the node\_0 locally.
