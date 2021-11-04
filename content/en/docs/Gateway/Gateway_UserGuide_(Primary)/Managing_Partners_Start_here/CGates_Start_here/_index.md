{
    "title": " ",
    "linkTitle": "Managing Connection Gate objects",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

# Managing Connection Gate objects

## About CGates and CGateGroups

[Introduction](#intro)

[Protocol connection](#Protocol_connection)

[CGate hierarchy](#cgate_hierarchy)

[SGates and SGateGroups](#sgates)

<span id="intro"></span>

### Introduction

This documentation refers to <span style="font-style: italic;">Connection Gates</span> as <span style="font-style: italic;">CGates</span>.

CGate and CGateGroup objects are identification filters used internally in server mode at the protocol connection level to control the connections of remote partners.

CGates determine whether a client has the right to connect to Gateway and exchange files with it or not. CGates are also used to assign connected user rights to the Virtual File Directory tree.

CGateGroups are used to group together a set of CGates with similar properties. For example, all CGates that use FTP protocol could belong to the same FTP CGateGroup.

Note that you cannot use the CGate identification mechanism when working with SMTP or POP3 protocols, since these protocols only function in client mode.

<span id="Protocol_connection"></span>

### Protocol connection

If the protocol connection is successful, the CGate supplies the following information to the file transfer process for use during the current session:

-   Virtual File Directory (VFD) rights for the connected user. You must assign user access rights via the CGate object for FTP, SFTP, HTTP and SHTTP transfers.
-   Protocol-dependent parameters:
    -   PHSE (server password to return to the client)
    -   FTP (home and root directories within the VFD)
    -   HTTP (<span style="font-style: italic;">home\_page</span>, <span style="font-style: italic;">list\_template</span>, home and root directories within the VFD)
-   User parameters 1 and 2 for selective file visibility from the connected client side

#### Connection to Gateway resources

The following figure illustrates how all connections to Gateway resources pass via the CGate object:

<img src="/Images/Gateway/CGate_Connection_756x596.png" class="maxWidth" />

<span id="cgate_hierarchy"></span>

### CGate hierarchy

CGates are organized hierarchically within CGateGroups. A CGateGroup can nest other CGateGroups. However, only one CGateGroup in a given hierarchy contains CGates.

CGateGroups are used to:

-   Group CGates (that correspond to one user or one user profile), depending on technical aspects such as:
    -   The protocol
    -   The Called SAP (the listening SAP on the Gateway host machine) and address (Gateway may serve as a bridge between separate networks)
-   Link users to a Template Site in order to use the Dynamic Site creation process, since a given hierarchy is always protocol-specific.
-   Define parameter values for a set of CGates (below the current CGateGroup in the hierarchy) without duplicating the information. Certain CGate parameters are added within a given hierarchy. Others are overridden by the hierarchy.

CGates are organized in a hierarchy in which each CGate belongs to a CGateGroup. The top-level object in the hierarchy is the <span style="font-style: italic;">root</span> CGateGroup. A CGateGroup can nest multiple sub-CGateGroups or CGates. However, a CGateGroup cannot contain CGateGroups <span style="font-style: italic;">and</span> CGates at the same level. The CGate hierarchy is the set of objects that comprises the CGate (at the bottom of the hierarchy) and all its associated parent CGateGroups right up to the root CGateGroup.

The purpose of this hierarchical organization is to group CGates with shared properties, such as protocol or TCP/IP address. In addition, this organization allows for parameter inheritance and avoids the duplication of information.

#### Example

The following diagram schematically illustrates an example of CGate organization:

<img src="/Images/Gateway/CGate_Hierarchy_756x510.png" class="maxWidth" />

The hierarchical organization for CGates and CGateGroups follows these rules:

-   A CGate always belongs to a single parent CGateGroup.
-   A CGateGroup can contain multiple CGates or multiple sub-CGateGroups. However, a CGateGroup cannot contain both sub-CGateGroups and CGates at the same level.
-   A CGateGroup that does not belong to a parent group is referred to as a <span style="font-style: italic;">root CGateGroup</span>.

<span id="sgates"></span>

### SGates and SGateGroups

Gateway now supports the use of [*Super CGates* (SGates)](sgates_about) that offer a higher capacity than the standard CGates.

Related topics

[Working with CGates and CGateGroups](working_with_cgates_and_cgategroups_(gui))

[Working with CGates (command line)](working_with_cgates_cli)

[Working with CGateGroups (command line)](working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](working_with_cgates_cli/cgates_parameter_list)

[Overview: Connection Gates](../../ov_gateway/ov_connection_gates)

[CGates: Protocol connection phase](cgates_protocol_connection_phase)

[CGates: Transfer phase](cgates_transfer_phase)

[About SGates](sgates_about)

[Working with SGates](sgates_working_with)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
