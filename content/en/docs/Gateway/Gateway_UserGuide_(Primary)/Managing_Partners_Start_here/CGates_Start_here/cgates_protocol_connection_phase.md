{
    "title": "CGates: Protocol connection phase",
    "linkTitle": "CGates: Protocol connection phase",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Partners

[Connection identification](#Connection_identification)

[Default protocol connection mechanism via CGates](#Default_protocol_connection_mechanism_via_CGates)

[Setting protocol connection parameters](#Setting_protocol_connection_parameters)

[How Gateway selects a CGate](#How_Gateway_selects_a_CGate)

[Best matching process](#Best_matching_process)

[Checking CGate parameters](#Checking_CGate_parameters)

For more information on TLS security, refer to *Security guide &gt; [SSL and TLS protocols](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/ssl_and_tls_protocols_about.htm)*.

[Forcing CGates](#Forcing_CGates)

<span id="Connection_identification"></span>

## Connection identification

Gateway manages connection identification at the protocol connection level. Although the CGate and CGateGroup objects provide a default identification mechanism, you can customize the Protocol connection user exit [ExitRcProtoConn\_C](../../../customizing_gw_about/user_exits_about/user_exits_external#ExitRcProtoConn_C) to override this definition.

Protocol connection exit scheduling and its interaction with the default identification process depend on the **[Connection control method](../../../configuration_start_here/config_gateway_paras#connection_control_method)** parameter that you set in the configuration menu. The connection identification can also be set per protocol using the <span style="font-weight: bold;">[Set option per protocol...](../../../configuration_start_here/config_gateway_paras#Connection_Ctrl_Meth_Per_Protocol)</span> option. You can select any of the following methods:

-   <span style="font-weight: bold;">Monitor</span>: Applies no identification via CGate or exit – implements identification via static Site object
-   <span style="font-weight: bold;">CGate</span>: Applies default identification
-   <span style="font-weight: bold;">Exit</span>: Executes Protocol connection exit
-   <span style="font-weight: bold;">CGate & Exit</span>: Applies CGate identification and then executes exit
-   <span style="font-weight: bold;">Exit & CGate</span>: Executes exit and then applies CGate identification
-   <span style="font-weight: bold;">Exit & SGate</span>: Executes exit and then applies SGate identification
-   <span style="font-weight: bold;">Use global</span> (<span style="font-style: italic;">only for Set option per protocol</span>): Use the global connection control method (as opposed to a specific connection control method for this protocol)

Use the <span style="font-weight: bold;">Exit & CGate</span> option if you want to [force the use of a particular CGate](#Forcing_CGates).

<span id="Default_protocol_connection_mechanism_via_CGates"></span>

## Default protocol connection mechanism via CGates

The default connection identification process via CGate objects is as follows:

1.  Gateway first identifies a CGateGroup that corresponds to the connected user and then refines the search via the CGate objects within that group. Since CGates can contain wildcard characters (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>), this selection is based on a best-matching process. Gateway selects a CGate whose parameters most closely correspond to those taken from the network.
2.  After selecting a CGate, Gateway then checks the protocol-dependent parameters, security parameters and so on. If the checks fail, Gateway rejects the connection.
3.  Gateway then retrieves and merges the CGate hierarchy to build a set of the following output parameters:
    -   protocol-dependent parameters for use while the connection is active
    -   connected user rights on the VFD device
    -   an optional Template Site (if the client station is not declared as a Remote Site object)
4.  If the <span style="font-weight: bold;">Template Site</span> value is set in the CGateGroup object, Gateway uses the Template Site and the parameters received from the network to create a Dynamic Site. Otherwise, Gateway tries to find an existing Site definition that matches the parameters taken from the network. If Gateway fails to retrieve a Site, the connection is rejected.

<span id="Setting_protocol_connection_parameters"></span>

## Setting protocol connection parameters

To allow Gateway to select a CGate, you must first define the protocol connection parameters via the CGateGroup and CGate objects.

#### CGateGroup properties

Define the following properties in the top-level <span style="font-weight: bold;">CGateGroup</span>. You can only set these parameters once in a given hierarchy, and all CGates below this CGateGroup inherit these properties:

-   Protocol
-   HTTP host name (optional)
-   TCP/IP connection SAP
-   TCP/IP called address (optional)

To take a set of called addresses into account, use wildcard characters (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>) in the <span style="font-weight: bold;">TCP/IP called address</span> field.

#### CGate properties

Define the following properties in the <span style="font-weight: bold;">CGate</span> object:

-   <span style="font-style: italic;">Protocol identifiers</span>: Protocol identifiers can contain wildcard characters (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>) and are protocol-dependent. That is, the parameters that you complete for the CGate object depend on the protocol defined for the parent CGateGroup:  
    <table>
             
             
             
       
       <tbody>
          <tr>
             <td><p>FTP, SFTP &amp; HTTP</p>         </td>
             <td><ul>
    <li><span class="code">login_user</span>, <span class="code">login_password</span></li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>PEL, OFTP</p>         </td>
             <td><ul>
    <li><span class="code">client_ident</span>, <span class="code">client_password</span></li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>PeSIT HS D, PeSIT HS E</p>         </td>
             <td><ul>
    <li><span class="code">client_ident</span>, <span class="code">client_password</span>, <span class="code">server_ident</span> and the PeSIT pre-connection parameters (<span class="code">login_user</span>, <span class="code">login_password</span>)</li>
    </ul>         </td>
          </tr>
       </tbody>
    </table>
-   *Calling Address Control patterns*: used to specify authorized or forbidden TCP/IP calling addresses. You can define this property in both CGateGroup objects and in CGates. Since this is an additive parameter, Gateway takes both object definitions into account.

<span id="How_Gateway_selects_a_CGate"></span>

## How Gateway selects a CGate

To select a CGate, Gateway first identifies a CGateGroup whose protocol, called TCP/IP SAP and optionally called TCP/IP address, matches those of the incoming connection. Within that CGateGroup, Gateway then selects a CGate object whose protocol identifiers match the connection.

Gateway then checks that the parameters taken from the network correspond to the selected CGate. It checks the following parameters:

-   Protocol identifier password
-   TLS security parameters (TLS profile, TLS client and server authentication)
-   CGate state (must be enabled)
-   Calling address and SAP

<span id="Best_matching_process"></span>

## Best matching process

Since many fields may contain wildcard characters (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>), Gateway uses a <span style="font-style: italic;">best matching</span>process to identify the CGate that most closely corresponds to a given connection. Gateway applies this process to:

-   Protocol identifiers
-   Called address
-   Called SAP

### Protocol identifier matching

If CGate protocol identifiers contain wildcards, multiple CGate definitions may match the protocol parameters of a given connection. Gateway uses a <span style="font-style: italic;">best matching process</span> based on the number of shared characters in the login field to identify the CGate that most closely corresponds to the incoming connection.

The following table describes the protocol identifier matching process for each protocol:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Protocol</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FTP, SFTP and HTTP</p>         </td>
         <td><p>Gateway searches for the number of shared characters in the <span class="code">login_user</span> parameter taken from the network (sent by the client trying to connect) and the <span class="code">login_user</span> parameter for the current CGate object.</p>         </td>
      </tr>
      <tr>
         <td><p>PEL, OFTP</p>         </td>
         <td><p>Gateway searches for the number of shared characters in the <span class="code">client_ident</span> parameter taken from the network (sent by the client trying to connect) and <span class="code">client_ident</span> parameter taken from the current CGate object.</p>         </td>
      </tr>
      <tr>
         <td><p>PeSIT HS D, PeSIT HS E</p>         </td>
         <td><p>Gateway takes into account both the <span class="code">client_ident</span> (received PI 3) and the <span class="code">server_ident</span> (received PI 4) parameters:</p>
<ul>
<li>If two CGate definitions contain the same <span class="code">client_ident</span> value, Gateway selects the CGate whose <span class="code">server_ident</span> value best matches the corresponding parameter taken from the network.</li>
<li>If two CGate definitions contain different <span class="code">client_ident</span> values, Gateway selects the CGate whose <span class="code">client_ident</span> best matches the corresponding parameter taken from the network, regardless of the respective CGate <span class="code">server_ident</span> fields. In other words, the <span class="code">client_ident</span> parameter has priority.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

### Examples

### FTP / HTTP / SFTP / PEL / OFTP

If the client user login is "<span style="font-style: italic;">dupont"</span> and if the <span class="code">login\_user</span> or <span class="code">client\_ident</span> fields for the two CGates CG1 and CG2 are respectively "<span style="font-style: italic;">du\*"</span> and <span style="font-style: italic;">"dup?nt"</span>, then CG2 has a higher number of shared characters and is selected.

### PeSIT HS D / PeSIT HS E

#### Example 1

Given the following CGate definitions, where the <span class="code">client\_ident</span> values are different:

<span style="font-weight: bold;">CG1:</span> <span class="code">client\_ident</span> = "T\*" and <span class="code">server\_ident</span> = "G\*"

<span style="font-weight: bold;">CG2:</span> <span class="code">client\_ident</span> = "T?TI" and <span class="code">server\_ident</span> = "G\*"

If a client sends <span class="code">client\_ident</span> / PI 3 = "TITI" and <span class="code">server\_ident</span> / PI 4 = "GATEWAY", Gateway selects the CG2 CGate object.

#### Example 2

Given the following CGate definitions, where the <span style="font-style: italic;">client\_ident</span> values are the same:

<span style="font-weight: bold;">CG1:</span> <span class="code">client\_ident</span> = "T\*" and <span class="code">server\_ident</span> = "GATE\*"

<span style="font-weight: bold;">CG2:</span> <span class="code">client\_ident</span> = "T\*" and <span class="code">server\_ident</span> = "G\*"

If a client sends <span class="code">client\_ident</span> / PI 3 = "TITI" and <span class="code">server\_ident</span> / PI 4 = "GATEWAY", Gateway selects the CG1 CGate object.

#### Example 3

Given the following CGate definitions:

<span style="font-weight: bold;">CG1:</span><span class="code">client\_ident</span> = "T\*" and <span class="code">server\_ident</span> = "GATE\*"

<span style="font-weight: bold;">CG2:</span> <span class="code">client\_ident</span> = "T?TI" and <span class="code">server\_ident</span> = "G\*"

If a client sends <span class="code">client\_ident</span> / PI 3 = "TITI" and <span class="code">server\_ident</span> / PI 4 = "GATEWAY", Gateway selects the CG2 CGate object (<span class="code">client\_ident</span> takes priority over <span class="code">server\_ident</span>).

<span style="font-weight: bold;">Note:</span> Since the parameters listed above serve as selection keys, keep in mind that the fields taken from the network must contain a non-empty value.

### Called address matching

The Gateway host machine may be connected to more than one network and have several TCP/IP local addresses. It is therefore useful, although not mandatory, to link CGates to a specific network (IP address). To validate CGate selection and accept the connection, Gateway compares the <span class="code">called\_address</span> field (that can contain the wildcard characters <span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>), taken from the selected CGate parent groups with the <span class="code">called\_address</span> field taken from the network. If the CGateGroup field value is empty or if the two fields match, Gateway accepts the connection. Otherwise it rejects the connection.

<span style="font-weight: bold;">Note:</span> You set the <span style="font-weight: bold;">called address</span> field in a CGateGroup object and can only set this value once in a given hierarchy.

### Called SAP matching

The TCP/IP SAP called from the client side must match one of the listener connection ports associated with the current CGate hierarchy. The <span style="font-style: italic;">sap</span> field is part of the CGateGroup object and can only be set once in a given hierarchy. This field value follows the syntax given in <span style="font-style: italic;">Checking CGate Parameters</span>.

<span id="Checking_CGate_parameters"></span>

## Checking CGate parameters

After selecting a CGate that best matches the incoming connection, Gateway checks the following parameters:

-   Protocol identifier passwords
-   Calling address filter list
-   TLS security parameters

<span style="font-weight: bold;">Note:</span> Each failure during the checking operation generates a message in the Gateway LOG file.

<span id="Checking_protocol_identifiers"></span>

### Checking protocol identifiers

Gateway checks the following protocol identifier parameters:

-   <span style="font-weight: bold;">FTP, HTTP and SFTP:</span><span class="code">login\_password</span>
-   <span style="font-weight: bold;">PeSIT</span><span style="font-weight: bold;">:</span><span class="code">client\_password</span> (and pre-connection parameters <span class="code">login\_user</span> and <span class="code">login\_password</span>)
-   <span style="font-weight: bold;">PEL, OFTP</span><span style="font-weight: bold;">:</span><span class="code">client\_password</span>

<span style="font-weight: bold;">Note:</span> When the corresponding CGate fields are set to asterisk ( <span style="font-weight: bold;">\*</span> ), every value taken from the network is accepted and it is not mandatory to send these values from the client side.

<span id="Checking_calling_address_filter_list"></span>

### Checking calling address filter list

Each CGate and CGateGroup can contain an access control list. The access control list allows you to define the IP addresses from which a defined user is authorized to connect to Gateway. Each element of this list comprises two fields:

-   An IP address pattern (that can include the <span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span> wildcards)
-   An access flag (which can either be ALLOWED or DENIED)

During the connection process, Gateway checks the remote address provided by the client against the access control list of each member of the selected CGate hierarchy. Since the IP address pattern may contain wildcards, Gateway applies a best matching selection process (based on the number of shared characters) to each CGate or CGateGroup list. In addition, Gateway uses the best matching address pattern from the higher group of the hierarchy (from the CGateGroup nearest the root) to determine whether the connection is accepted or not.

<span style="font-weight: bold;">Note:</span> If a list is left empty, all the calling addresses are allowed by default.

### Examples

#### Case 1: Calling address filter list in the CGate object only

Calling address taken from the network: 172.17.160.40

Calling address filter list (CGate)

-   Pattern = authorization
-   172\* = Denied
-   172.1?.160.\* = Accepted

In this case, the connection is accepted.

#### Case 2: Calling address filter list in both the CGate and the parent CGateGroup

Calling address taken from the network: 172.17.160.40

Calling address filter list (CGate)

-   Pattern = authorization
-   172\* = Denied
-   172.1?.160.\* = Accepted

Calling address filter list (parent CGateGroup)

-   Pattern = authorization
-   172\* = Denied

The calling address filter list in the CGateGroup object takes priority, so in this case, the connection is denied.

<span id="Checking_security__TLS__parameters"></span>

### Checking security (TLS) parameters

When you use TLS or SSL to secure incoming connections, the TLS Handshake has already ended when the protocol connection occurs. Gateway may reject a client if the security level is lower than the expected level.

The Gateway network layer (also known as <span style="font-style: italic;">NET</span>) provides three security-related parameters that Gateway checks against those found in the selected CGate definition. The following TLS-related parameters are only part of the CGate object, and not the CGateGroup object:

-   <span class="code">tls\_client\_auth</span>: Flag that indicates whether authentication is required for the client trying to connect. (<span style="font-weight: bold;">TLS Client Authentication</span> check box)
-   <span class="code">tls\_sprof:</span> Security profile name used for the incoming call TLS Handshake negotiation. This field can contain wildcards (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>). (<span style="font-weight: bold;">TLS Security profile name</span> field)
-   <span class="code">tls\_sprof\_user\_param</span>: User parameter that you can complete in the security profile definition. This field can contain wildcards (<span class="code" style="font-weight: bold;">?</span> and <span class="code" style="font-weight: bold;">\*</span>). (<span style="font-weight: bold;">TLS Security user parameters</span> field)

See the [Security Guide](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm) for further information.

<span id="Forcing_CGates"></span>

## Forcing CGates

This feature allows you to force the selection of a specific CGate, rather than allowing Gateway to select the CGate to use for identification.

To implement this functionality, you must first go to the configuration menu and set the [Connection control method](../../../configuration_start_here/config_gateway_paras#connection_control_method) to <span style="font-weight: bold;">Exit & CGate</span>. If you set any other connection control method, the <span class="code">cgate\_forced</span> parameter is ignored. An external process, such as access to an LDAP directory, can then be scheduled for user identification. In such a case, it is useful to force the selection of a specific CGate object and define Gateway users externally via a set of parameters that includes:

-   Identification parameters (such as <span class="code">user\_login</span> and <span class="code">user\_password</span> for FTP clients)
-   Links with Gateway resources profiles (such as VFD rights in the CGate/CGateGroup objects) via a single field (the CGate name)

To force CGate selection, you must set the following parameters in the Protocol connection user exit [ExitRcProtoConn\_C](../../../customizing_gw_about/user_exits_about/user_exits_external#ExitRcProtoConn_C) output structure (<span class="code">Out\_ExitRcProtoConn\_t</span>):

-   <span class="code">cgate\_forced</span>: name of the CGate object to select (a string of up to 32 characters)
-   <span class="code">cgate\_forced\_p</span>: indicate whether or not to take the <span class="code">cgate\_forced</span> parameter into account at the CGate selection level (unsigned char, set to 0 or 1)

<span id="Protocol_connection_using_cgate_forced_field"></span>

### Protocol connection using cgate\_forced field

When you set the <span class="code">cgate\_forced\_p</span> field in the output structure<span class="code"> Out\_ExitRcProtoConn\_t</span> to <span style="font-weight: bold;">1</span>, Gateway:

-   Takes the <span class="code">cgate\_forced</span> parameter into account
-   Automatically searches for the specified CGate object

If Gateway finds the specified CGate object, then it:

-   Does not apply any additional selection or checking algorithm (refer to [Checking CGate parameters](#Checking_CGate_parameters))
-   Automatically selects this CGate object for the current connection
-   Merges the CGate hierarchy and supplies the resulting parameters to the file transfer layer (refer to [Passing parameters to File Transfer Layer](../cgates_transfer_phase#Passing_parameters_to_File_Transfer_Layer))
-   Applies the CGate output parameters [override mechanism](../cgates_transfer_phase#Overwritten_parameters) from the Protocol connection exit, regardless of whether the CGate object selection was forced

If Gateway cannot find the specified CGate object, then the connection fails. The name provided in the <span class="code">cgate\_forced</span> field does not correspond to any existing CGate object definition known to Gateway.

<span style="font-weight: bold;">Note:</span> When you use the CGate forcing mechanism, Gateway applies no selection and checking algorithms to the forced CGate object. This means you must take the following points into account:

-   The forced CGate object must exist on Gateway.
-   You must manually process the optional checks that Gateway normally performs on CGate parameters. Set up these checks in the Protocol connection exit.
-   If you create a Dynamic Site, the Template Site object (taken from the selected CGate hierarchy) must correspond to the current connection (protocol type, and so on). Otherwise, the connection will fail.

Related topics

[Overview: Connection Gates](../../../ov_gateway/ov_connection_gates)

[About CGates and CGateGroups](../)

[CGates: Transfer phase](../cgates_transfer_phase)

[Working with CGates and CGateGroups](../working_with_cgates_and_cgategroups_(gui))

[Working with CGates (command line)](../working_with_cgates_cli)

[Working with CGateGroups (command line)](../working_with_cgates_cli/working_with_cgategroups_cli)

[CGates and CGateGroups: Parameters List](../working_with_cgates_cli/cgates_parameter_list)

[External user exits](../../../customizing_gw_about/user_exits_about/user_exits_external)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
