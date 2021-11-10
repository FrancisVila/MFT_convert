{
    "title": "AIX specific procedures",
    "linkTitle": "AIX specific procedures",
    "weight": "20"
}This chapter provides information specific to AIX platforms.

## Basics

<table>
   <tbody>
      <tr>
         <td><p><strong>Options available with AIX systems</strong></p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for AIX supports COMMUNICATION SERVER 5 SNA LU 6.2 Services through the CPIC programming interface.</p>         </td>
      </tr>
   </tbody>
</table>

## TCP/IP network interface configuration

To work with TCP/IP, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires the following information:

-   The **local port numbers** where <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> listens in order to receive incoming connections.  
    You must assign a different port number to each configured file transfer protocol. Make sure that these port numbers are not currently in use, and that no application on the system will try to use them during operation. It is recommended that you select port numbers in the range **5000** to **65000**. Configure the port numbers in the configuration menu and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.
-   Either a **host name** or **IP address** to use as authoritative host for incoming connections.  
    Use one of the following:
    -   The host name of the local machine
    -   The looped address (localhost or 127.0.0.1)
    -   An empty address

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Site objects group all parameters that apply to outgoing connections. For each remote machine and each configured file transfer protocol, you must create a Site object where you supply the TCP/IP address and port number that the remote machine expects for that protocol. To create <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Sites, use either the Windows GUI or the peladm line command.

### Example

The following example creates a Site using the command <span class="code">peladm create\_site</span> for a Site in PHSE protocol at dotted IP address <span class="bold_in_para">193.56.234.50</span> and port number <span class="bold_in_para">22001</span>:


    peladm create_site  -pr PHSE  -a SITE1  -pi SITE1
                            
                        -da 193.56.234.50/22001

You can specify either the host name (when using DNS facilities), or the IP dotted address (such as 193.56.234.50) as the IP destination address fields for Sites to which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> connects over TCP/IP.

## LU 6.2 network interface configuration

### Basics

<table>
   <tbody>
      <tr>
         <td><p>Hardware and software prerequisites</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> can communicate over LU 6.2 conversations using either SNA SERVER version 3 or COMMUNICATION SERVER version 5 SNA sub-systems.</p>         </td>
      </tr>
      <tr>
         <td><p>Configuring <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for CS5</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires AIX operating system version 5.1 or higher to support COMMUNICATION SERVER 5.</p>         </td>
      </tr>
   </tbody>
</table>

### Configuring SNA connectivity

A complete description of SNA connectivity configuration is beyond the scope of this document. Configurations can vary greatly depending on the topology of the SNA network. You can use the X-motif user interface <span class="bold_in_para">xsnaadmin</span> to configure SNA connectivity on your system.

To configure SNA connectivity, you define the following SNA configuration items:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">SNA configuration item         </th>
<th class="HeadD-Column1-Header1">Definition (xsnaadmin menu items)         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>local node</p>
<p>(characteristics)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>Node parameters</p>         </td>
      </tr>
      <tr>
         <td><p>port</p>
<p>(for each hardware interface)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>New Port</p>         </td>
      </tr>
      <tr>
         <td><p>link station</p>
<p>(for each adjacent host)</p>         </td>
         <td><p>Services</p>
<p>Connectivity</p>
<p>Link Station</p>         </td>
      </tr>
   </tbody>
</table>

These configuration parameters are stored in the <span class="code">/etc/sna/sna\_domn.cfg</span> file.

For a description of SNA connectivity parameters, refer to the related AIX Communication Server 5 documentation.

The following examples of a sample<span class="code"> sna\_domn.cfg</span> file illustrate some of the parameters involved in the SNA connectivity configuration data.

#### Example of local node configuration

>     [define_node]
>     cp_alias = PXRS10
>     description = ""
>     fqcp_name = SOPRA.PXRS10
>     node_type = NETWORK_NODE
>     mode_to_cos_map_supp = NO
>     mds_supported = YES
>     node_id = <0710000f>
>     max_locates = 1500
>     dir_cache_size = 255
>     max_dir_entries = 0
>     locate_timeout = 0
>     reg_with_nn = YES
>     reg_with_cds = YES
>     mds_send_alert_q_size = 100
>     cos_cache_size = 24
>     tree_cache_size = 40
>     tree_cache_use_limit = 40
>     max_tdm_nodes = 0
>     max_tdm_tgs = 0
>     max_isr_sessions = 1000
>     isr_sessions_upper_threshold = 900
>     isr_sessions_lower_threshold = 800
>     isr_max_ru_size = 16384
>     isr_rcv_pac_window = 8
>     store_endpt_rscvs = NO
>     store_isr_rscvs = NO
>     store_dlur_rscvs = NO
>     dlur_support = YES
>     pu_conc_support = YES
>     nn_rar = 128
>     max_ls_exception_events = 0
>     ms_support = NORMAL
>     queue_nmvts = YES
>     ptf_flags = NONE

#### Example of link station definition

>     [define_qllc_ls]
>     ls_name = LYRS04
>     description = ""
>     port_name = QLLCP0
>     adj_cp_name = SOPRA.RS04
>     adj_cp_type = NETWORK_NODE
>     dspu_services = NONE
>     dspu_name = <0000000000000000>
>     dlus_name = <0000000000000000000000000000000000>
>     bkup_dlus_name = <0000000000000000000000000000000000>
>     local_node_id = <00000000>
>     adj_node_id = <00000000>
>     vc_type = SVC
>     address = 9690002
>     pvc_id = 1
>     max_send_btu_size = 265
>     ls_attributes = SNA
>     cp_cp_sess_support = YES
>     default_nn_server = YES
>     hpr_supported = NO
>     auto_act_supp = NO
>     tg_number = 0
>     limited_resource = NO
>     solicit_sscp_sessions = NO
>     pu_name = <0000000000000000>
>     disable_remote_act = NO
>     link_deact_timer = 30
>     use_default_tg_chars = YES
>     effect_cap = 9600
>     connect_cost = 0
>     byte_cost = 0
>     security = SEC_PUBLIC_SWITCHED_NETWORK
>     prop_delay = PROP_DELAY_PKT_SWITCHED_NET
>     user_def_parm_1 = 128
>     user_def_parm_2 = 128
>     user_def_parm_3 = 128
>     target_pacing_count = 7
>     ls_role = USE_PORT_DEFAULTS
>     max_ifrm_rcvd = 0
>     dlus_retry_timeout = 0
>     dlus_retry_limit = 0
>     need_vrfy_fixup = NO
>     initially_active = NO
>     react_timer = 30
>     react_timer_retry = 65535
>     req_rev_charge = NO
>     loc_wsize = 0
>     rem_wsize = 0
>     retry_limit = 2
>     retry_timeout = 8
>     loc_packet = DEFAULT
>     rem_packet = DEFAULT
>     idle_timeout = 48
>      
>     cud = <c3>
>     rx_thruput_class = DEFAULT
>     tx_thruput_class = DEFAULT
>     cugo = NO
>     cug = NO
>     cug_index = 0
>     nuid = <>

### Configuring APPC/CPIC resources

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses the CPIC programming Interface to communicate over SNA networks. In CS5, this API is based on the APPC interface. The following APPC resources enable <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to operate with SNA:

-   Local LU
-   Partner LU (on remote node)
-   Mode
-   Remote Node (if needed)
-   Transaction programs
-   CPIC side information

You must define:

-   At least one resource of each type (with the possible exception of Remote Node), to allow <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to operate as both initiator and responder
-   CPIC-side information to allow <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to initiate connections to a remote machine
-   A transaction program for PeSIT E protocol to allow the SNA sub-system to start the appropriate <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> program on incoming conversations

Use the following menu entries from <span class="bold_in_para">xsnaadmin</span> to configure these items:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Resource         </th>
<th class="HeadD-Column1-Header1">xsnaadmin menu items         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local LU</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Independent Local LU</p>         </td>
      </tr>
      <tr>
         <td><p>Remote Node</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Remote Node</p>         </td>
      </tr>
      <tr>
         <td><p>Partner LU</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>New Partner LU</p>
<p>Partner LU on Remote Node</p>         </td>
      </tr>
      <tr>
         <td><p>Modes</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>Modes</p>         </td>
      </tr>
      <tr>
         <td><p>Transaction Programs</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>Transaction Programs</p>         </td>
      </tr>
      <tr>
         <td><p>CPIC Side Info</p>         </td>
         <td><p>Services</p>
<p>APPC</p>
<p>CPIC</p>         </td>
      </tr>
   </tbody>
</table>

Local LU, partner LUs and mode definitions are stored in <span class="code">/etc/sna/sna\_node.cfg</span>.

Transaction Program definitions are stored in <span class="code">/etc/sna/sna\_tps</span>.

CPIC Side Info profiles are stored in <span class="code">/etc/sna/sna\_domn.cfg</span>.

#### Defining local LU

<span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> can use a single local LU for both outgoing and incoming conversations. However, this type of configuration is not recommended.

For example, you can define sets of local LUs for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> as follows:

-   <span class="bold_in_para">LPHE</span>:local LU for both incoming and outgoing conversations

or

-   <span class="bold_in_para">LPHEI</span>: local LU for incoming conversations only
-   <span class="bold_in_para">LPHEO</span>: local LU for outgoing conversations only

#### Example of local LU definition

This is is an extract from <span class="code">/etc/sna/sna\_node.cfg</span>:

>     [define_local_lu]
>     lu_alias = PHSEI
>     list_name = ""
>     description = ""
>     lu_name = PHSEI
>     lu_session_limit = 0
>     pu_name = <0000000000000000>
>     nau_address = 0
>     default_pool = NO
>     syncpt_support = NO
>     lu_attributes = NONE
>     sscp_id = 0
>     disable = NO
>     sys_name = ""
>     timeout = 60
>     back_level = NO

#### Defining partner LU

You must define a partner LU for each <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> Remote Site. To enable <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to connect to that Site, you must also create a CPIC side info profile that points to that partner LU. For more information on CPIC side info profile creation, see <a href="#CPIC_side_info_AIX" class="MCXref xref">Defining CPIC side info</a>. When you create a partner LU name, you supply the fully qualified partner LU name.

#### Example of partner LU definition

This is an extract from <span class="code">/etc/sna/sna\_node.cfg</span>:

>     [define_partner_lu]
>     plu_alias = RS04
>     description = ""
>     fqplu_name = SOPRA.RS04
>     plu_un_name = RS04
>     parallel_sess_supp = YES
>     appcip_routing_preference = NATIVE
>     max_mc_ll_send_size = 0
>     conv_security_ver = NO

#### Defining mode

You must define all modes used for LU 6.2 conversations on all nodes intended to communicate over LU 6.2 (local and remote nodes, as seen from the local machine). A simple LU 6.2 configuration for a monitor that uses the same mode for all LU 6.2 conversations is possible, but not required. When a single set of mode parameters is not suitable for all LU 6.2 conversations, you can create several modes.

#### Example of mode definition

This is an extract from <span class="code">/etc/sna/sna\_node.cfg</span>:

>     [define_mode]
>     mode_name = PHSEMODE
>     description = ""
>     max_neg_sess_lim = 32767
>     plu_mode_session_limit = 2
>     min_conwin_src = 1
>     min_conloser_src = 0
>     auto_act = 0
>     receive_pacing_win = 4
>     max_receive_pacing_win = 0
>     default_ru_size = YES
>     max_ru_size_upp = 1024
>     max_ru_size_low = 0
>     cos_name = #CONNECT

<span id="CPIC_side_info_AIX"></span>

#### Defining CPIC side info

You must create a CPIC side info profile for each Remote Site to which <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> may initiate LU 6.2 conversations. Apart from the CPIC side info profile, you must also create the corresponding Site object. You can create these objects in any order, but the CPIC side info profile that addresses a given Remote Site must exist when <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> attempts to connect to this Site.

The CPIC side info profile contains all information that a CPIC application requires to initiate an LU 6.2 conversation. <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses the CPIC side info profile name as an object that fully addresses and qualifies the remote application.

For this reason, you supply the following information in each CPIC side info profile dedicated to <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>:

-   Local LU alias
-   Partner LU name
-   Mode name
-   TP (transaction program) name

#### Example of CPIC side info definition

This is an extract from <span class="code">/etc/sna/sna\_domn.cfg</span>:

>     [define_cpic_side_info]
>     sym_dest_name = PHECPICI
>     description = ""
>     lu_alias = PHSEI
>     partner_lu_name = PHSER
>     mode_name = PHSEMODE
>     tp_name_type = APPLICATION_TP
>     tp_name = PHECPICR
>     conversation_security_type = NONE
>     security_user_id = ""
>     security_password = ""

#### Defining TP (Transaction Program)

For each incoming conversation intended for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>, the SNA sub-system is expected to start an appropriate <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> application program. You first create a Transaction Program profile for the PeSIT E protocol.

You define Transaction Program profiles as follows:

1.  The USERID and GROUP fields must match the user-id and group-id used to install and start <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>.
2.  Set the TYPE field to NON-QUEUED.
3.  Complete the PATH field with the absolute path of the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> application program that corresponds to the targeted file transfer protocol.
4.  The ENVIRONMENT field must set APPCTPN to the corresponding TP name.  
    If for example, the TP name is PHECPICR, this field must contain APPCTPN=PHECPICR.

#### Example of Transaction Program definition

This is an extract from <span class="code">/etc/sna/sna\_tps</span>:

>     [PHECPICR]
>     LUALIAS = ""
>     DESCRIPTION = ""
>     USERID = portpel
>     GROUP = Gateway
>     TIMEOUT = 0
>     TYPE = NON-QUEUED
>     STYLE = EXTENDED
>     PATH = /portage_Gateway/users/portpel/T6342/bin/PHECPICR
>     ENV = APPCTPN=PHECPICR

### Summary of SNA installation for <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>

#### Configuring and checking SNA system resources

The SNA configuration procedure using the <span class="bold_in_para">xsnaadmin</span> interface is as follows:

1.  Configure SNA connectivity on the local machine:
    -   The node
    -   One port for each hardware interface used for SNA
    -   One link station per remote machine
2.  Check that you can activate all links. If not, check the SNA log and trace files.  
    The cause may be incorrect configuration on a remote machine.
3.  Configure the local LUs, partner LUs and possibly remote NODEs that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> will use.
4.  Use the appropriate <span class="bold_in_para">xsnaadmin</span> command to establish LU-LU sessions manually.  
    Fix any problems on the local and remote machines that may prevent LU-LU sessions from being established.
5.  Create all other configuration objects that <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> requires (that is, Modes, CPIC Side Information Profile, and Transaction Programs).

#### Configuring and checking <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> resources for SNA

1.  Configure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to enable the SNA option for the PeSIT E protocol.
2.  Stop and then restart <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> using the appropriate commands.
3.  Create a Remote Site for each remote system that expects to accept SNA conversations initiated by the local <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.  
    This Remote Site contains the corresponding CPIC side info profile name as the destination address field. Create the Remote Site using either the Windows GUI or the <span class="bold_in_para">peladm</span> command.
4.  To check each Remote Site configured for SNA/LU 6.2, submit a Transfer Request addressed to that Site.

If a problem occurs that prevents the file transfer from processing normally, enable the trace mode for that Site and set up the trace and log facility in the SNA sub-system. This will produce outputs that may help track the problem.

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
