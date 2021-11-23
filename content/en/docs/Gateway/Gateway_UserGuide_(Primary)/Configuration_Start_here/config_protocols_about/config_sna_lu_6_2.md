{
    "title": "Configuring SNA LU 6.2 (on Windows)",
    "linkTitle": "SNA LU 6.2",
    "weight": "240"
}{{< Gateway/componentlongname  >}}: Configuration

For Windows server platforms only.

One of the network interfaces supported by Gateway is SNA LU 6.2. Gateway accesses SNA LU 6.2 via the CPI-C interface.

[Restrictions](#Restrictions)

[Defining SNA Resources](#Defining_SNA_Resources)

[Configuring Gateway for SNA LU 6.2](#Configuring_Gateway)

[Configuring Remote Sites for SNA LU 6.2](#Configuring_Remote_Sites)

[CPI-C symbolic destination](#CPI-C_Symbolic_Destination)

[CPI-C Transaction](#CPI-C_Transaction)

[Troubleshooting](#Troubleshooting)

[Error messages](#Error_messages)

<span id="Restrictions"></span>

## Restrictions

The current version implements only *basic conversation* functions, and does not support the following functions:

-   Commit/rollback
-   PIP (Program Initialization Parameters)
-   Conversational security
-   Control verbs

If required, you must define the LU-LU security and conversational services via the SNA configuration program.

<span id="Defining_SNA_Resources"></span>

## Defining SNA Resources

Before setting up Gateway for SNA LU 6.2, ensure that Microsoft SNA server is installed and SNA resources are correctly configured. In particular, the following SNA resources must be defined:

-   Node
-   Link Service
-   Connection
-   Remote LU
-   Local LU
-   Mode
-   [CPI-C Transaction](#CPI-C_Transaction)
-   [CPI-C symbolic destination](#CPI-C_Symbolic_Destination)

For more information on SNA Server configuration, refer to the following documentation:

-   Microsoft SNA Server Installation Guide
-   Microsoft SNA Server Administration Guide
-   Microsoft SNA Server Managing Microsoft SNA Server
-   Microsoft SNA Server Reference

<span id="Configuring_Gateway"></span>

## Configuring Gateway for SNA LU 6.2

1.  In the Gateway configuration menu, select **Connectivity > Legacy protocols**.
2.  Select the required protocol:

> -   PeSIT E
> -   PeSIT D
> -   PEL

1.  Select <span style="font-weight: bold;">SNA</span>.
2.  Use the following parameters to set up the SNA interface for use with the selected protocol. The SNA parameters listed here are only those that Gateway references directly. Parameters required for the normal operation of an SNA Server are configured separately during the installation of the SNA Server.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Parameter</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>Incoming sessions</p>         </td>
         <td><p>Specify the maximum number of concurrent incoming SNA LU 6.2 sessions for the protocol being configured.</p>
<p>This value must be greater than or equal to the number of SNA LU 6.2 sessions configured in your SNA base.</p>         </td>
      </tr>
      <tr>
         <td><p>Outgoing sessions</p>         </td>
         <td><p>Specify the maximum number of concurrent outgoing SNA LU 6.2 sessions for the protocol being configured.</p>
<p>This value must be equal to or greater than the number of SNA LU 6.2 sessions configured in your SNA base.</p>         </td>
      </tr>
      <tr>
         <td><p>Local LU name</p>         </td>
         <td><p>Specify the local LU to associate with the file transfer protocol being configured.</p>
<p>This LU name must also exist in your SNA base.</p>         </td>
      </tr>
      <tr>
         <td><p>Transaction program</p>         </td>
         <td><p>Specify the CPI-C transaction name for the file transfer protocol being configured.</p>
<p>Suggested default values:</p>
<ul>
<li>PELCPICR for PEL</li>
<li>PHSECPICR for PeSIT HS E</li>
<li>PHSDCPICR for PeSIT HS D</li>
</ul>
<p>Refer to <a href="#CPI-C_Transaction">CPI-C Transaction</a>.</p>         </td>
      </tr>
   </tbody>
</table>

1.  Click <span style="font-weight: bold;">Activate</span> to enable the SNA interface for use with this protocol.

<span id="Configuring_Remote_Sites"></span>

## Configuring Remote Sites for SNA LU 6.2

Refer to [Site objects: Address configuration for Remote Sites](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/site_objects_address_config#SNA_LU62).

<span id="CPI-C_Symbolic_Destination"></span>

## CPI-C symbolic destination

Among the [SNA resources](#Defining_SNA_Resources) mentioned above, only <span style="font-style: italic;">CPI-C symbolic destination</span> is directly referenced by Gateway. Specify the CPI-C symbolic destination name in the <span style="font-weight: bold;">Destination</span> field in the Gateway Remote Site definition. It identifies the SNA resources to use to connect to the Site.

Below is a sample definition of a CPI-C symbolic destination for Microsoft SNA server:

-   <span style="font-weight: bold;">Name:</span> PELIMVS
-   <span style="font-weight: bold;">Comment:</span> MVS
-   <span style="font-weight: bold;">Partner TP Name:</span> PELCPICR
-   <span style="font-weight: bold;">Partner LU Name:</span> PELLU62A
-   <span style="font-weight: bold;">Conversation Security:</span> None
-   <span style="font-weight: bold;">Mode Name:</span> LPELLU62

The <span style="font-weight: bold;">Partner LU name</span> corresponds to an LU defined on the remote platform (for example, the ACB parameter in VTAM APPL macro on IBM MVS).

The <span style="font-weight: bold;">Partner TP name</span> designates the remote transaction to invoke. It must be known on the remote platform.

The<span style="font-weight: bold;"> Mode Name</span> determines the session parameters to use. The same name must also be defined on the remote platform.

The <span style="font-weight: bold;">Local LU</span> used for the transaction is that defined during Gateway configuration.

<span id="CPI-C_Transaction"></span>

## CPI-C Transaction

For a transfer in Initiator mode, the remote platform determines which TPN to use.

For a transfer in Responder mode, the TPN used must be one of the following:

-   PELCPICR: for PEL
-   PHDCPICR: for PeSIT HS D
-   PHECPICR: for PeSIT HS E

These TPNs are automatically defined in the Windows registry during Gateway configuration. They are "autostarted non\_queued". Before starting an LU 6.2 transfer, ensure that <span class="code">tpstart.exe</span> (a Microsoft SNA Server utility program) is started.

For more information on <span class="code">tpstart.exe</span>, refer to the <span style="font-style: italic;">Microsoft SNA Server CPI-C Programmer's Guide</span>.

### Sample entries installed by the Gateway configuration procedure

#### PELCPICR

\\HKEY\_LOCAL\_MACHINE\\system\\CurrentControlSet\\Services\\SnaBase\\Parameters\\

TPs\\<span style="font-weight: bold;">PELCPICR</span>\\Parameters\\

SNAServiceType:REG\_DWORD:0x06

PathName:REG\_SZ:c:\\winnt35\\system32\\cmd.exe

Parameters:REG\_SZ:/C d:\\xfb\\bin\\PELCPICR.cmd d:\\pelint

AcceptNames:REG\_SZ:PELCPICR

TimeOut:REG\_DWORD:0xffffffff

ConversationSecurity:REG\_SZ:NO

!--kadov\_tag{{}}-->AlreadyVerified:REG\_SZ:YES

#### PHDCPICR

\\HKEY\_LOCAL\_MACHINE\\system\\CurrentControlSet\\Services\\SnaBase\\Parameters\\

TPs\\<span style="font-weight: bold;">PHDCPICR</span>\\Parameters\\

SNAServiceType:REG\_DWORD:0x06

PathName:REG\_SZ:c:\\winnt35\\system32\\cmd.exe

Parameters:REG\_SZ:/C d:\\xfb\\bin\\PHDCPICR.cmd d:\\pelint

AcceptNames:REG\_SZ:PHDCPICR

TimeOut:REG\_DWORD:0xffffffff

ConversationSecurity:REG\_SZ:NO

AlreadyVerified:REG\_SZ:YES

#### PHECPICR

\\HKEY\_LOCAL\_MACHINE\\system\\CurrentControlSet\\Services\\SnaBase\\Parameters\\

TPs\\<span style="font-weight: bold;">PHECPICR</span>\\Parameters\\

SNAServiceType:REG\_DWORD:0x06

PathName:REG\_SZ:c:\\winnt35\\system32\\cmd.exe

Parameters:REG\_SZ:/C d:\\xfb\\bin\\PHECPICR.cmd d:\\pelint

AcceptNames:REG\_SZ:PHECPICR

TimeOut:REG\_DWORD:0xffffffff/p>

ConversationSecurity:REG\_SZ:NO

AlreadyVerified:REG\_SZ:YES

<span id="Troubleshooting"></span>

## Troubleshooting

The following checklist may be helpful when SNA connection problems occur:

-   Is MS SNA running? If not, start it now.
-   Is <span class="code">tpstart.exe</span> running? If not, start it now.
-   Is the physical link to the remote platform active? If not, start it now. If link activation fails, consult MS SNA documentation and check the corresponding parameters.
-   Can you activate an LU-LU session with the remote platform? If LU-LU activation fails, consult MS SNA documentation and check the corresponding parameters.
-   If you can activate the LU-LU session but conversation allocation fails, check that the symbolic destination used is defined in SNA. The partner LU, logmode and transaction program as defined in the symbolic destination must also be defined on the remote platform.
-   If conversation allocation is accepted but a timeout occurs, check that the remote Gateway is started.
-   If problems persist, further information is also available in Windows Event Log and MS SNA event log or audit files.

<span id="Error_messages"></span>

## Error messages

When a CPI-C function call fails, an error message is written in the Gateway LOG file as shown below:

<span style="font-weight: bold;">function=cmxxxx, rc=nnn, errcod=mmm</span>

where:

-   <span style="font-weight: bold;">cmxxxx</span> is the CPI-C function concerned
-   <span style="font-weight: bold;">nnn</span> is the return code of that function
-   <span style="font-weight: bold;">mmm</span> is the diagnostic specific to the SNA implementation on your platform

The following list is taken from CMC.H, and describes the <span style="font-weight: bold;">nnn</span> return codes in question.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>nnn</p>         </td>
         <td><p>Description</p>         </td>
      </tr>
      <tr>
         <td><p>0</p>         </td>
         <td><p>CM_OK</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>CM_ALLOCATE_FAILURE_NO_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>CM_ALLOCATE_FAILURE_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>CM_CONVERSATION_TYPE_MISMATCH</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>CM_PIP_NOT_SPECIFIED_CORRECTLY</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>CM_SECURITY_NOT_VALID</p>         </td>
      </tr>
      <tr>
         <td><p>7</p>         </td>
         <td><p>CM_SYNC_LVL_NOT_SUPPORTED_LU</p>         </td>
      </tr>
      <tr>
         <td><p>8</p>         </td>
         <td><p>CM_SYNC_LVL_NOT_SUPPORTED_PGM</p>         </td>
      </tr>
      <tr>
         <td><p>9</p>         </td>
         <td><p>CM_TPN_NOT_RECOGNIZED</p>         </td>
      </tr>
      <tr>
         <td><p>10</p>         </td>
         <td><p>CM_TP_NOT_AVAILABLE_NO_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>CM_TP_NOT_AVAILABLE_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>17</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND</p>         </td>
      </tr>
      <tr>
         <td><p>18</p>         </td>
         <td><p>CM_DEALLOCATED_NORMAL</p>         </td>
      </tr>
      <tr>
         <td><p>19</p>         </td>
         <td><p>CM_PARAMETER_ERROR</p>         </td>
      </tr>
      <tr>
         <td><p>20</p>         </td>
         <td><p>CM_PRODUCT_SPECIFIC_ERROR</p>         </td>
      </tr>
      <tr>
         <td><p>21</p>         </td>
         <td><p>CM_PROGRAM_ERROR_NO_TRUNC</p>         </td>
      </tr>
      <tr>
         <td><p>22</p>         </td>
         <td><p>CM_PROGRAM_ERROR_PURGING</p>         </td>
      </tr>
      <tr>
         <td><p>23</p>         </td>
         <td><p>CM_PROGRAM_ERROR_TRUNC</p>         </td>
      </tr>
      <tr>
         <td><p>24</p>         </td>
         <td><p>CM_PROGRAM_PARAMETER_CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>25</p>         </td>
         <td><p>CM_PROGRAM_STATE_CHECK</p>         </td>
      </tr>
      <tr>
         <td><p>26</p>         </td>
         <td><p>CM_RESOURCE_FAILURE_NO_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>27</p>         </td>
         <td><p>CM_RESOURCE_FAILURE_RETRY</p>         </td>
      </tr>
      <tr>
         <td><p>28</p>         </td>
         <td><p>CM_UNSUCCESSFUL</p>         </td>
      </tr>
      <tr>
         <td><p>30</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND_SVC</p>         </td>
      </tr>
      <tr>
         <td><p>31</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND_TIMER</p>         </td>
      </tr>
      <tr>
         <td><p>32</p>         </td>
         <td><p>CM_SVC_ERROR_NO_TRUNC</p>         </td>
      </tr>
      <tr>
         <td><p>33</p>         </td>
         <td><p>CM_SVC_ERROR_PURGING</p>         </td>
      </tr>
      <tr>
         <td><p>34</p>         </td>
         <td><p>CM_SVC_ERROR_TRUNC</p>         </td>
      </tr>
      <tr>
         <td><p>100</p>         </td>
         <td><p>CM_TAKE_BACKOUT</p>         </td>
      </tr>
      <tr>
         <td><p>130</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND_BO</p>         </td>
      </tr>
      <tr>
         <td><p>131</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND_SVC_BO</p>         </td>
      </tr>
      <tr>
         <td><p>132</p>         </td>
         <td><p>CM_DEALLOCATED_ABEND_TIMER_BO</p>         </td>
      </tr>
      <tr>
         <td><p>113</p>         </td>
         <td><p>CM_RESOURCE_FAIL_NO_RETRY_BO</p>         </td>
      </tr>
      <tr>
         <td><p>134</p>         </td>
         <td><p>CM_RESOURCE_FAILURE_RETRY_BO</p>         </td>
      </tr>
      <tr>
         <td><p>135</p>         </td>
         <td><p>CM_DEALLOCATED_NORMAL_BO</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
