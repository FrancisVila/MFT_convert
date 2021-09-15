{
    "title": "CFTXXX - Default networks",
    "linkTitle": "CFTXXX - Default networks",
    "weight": "490"
}# <span id="Defining_default_network_parameters__command_line_"></span>Defining CFTTCP

This topic describes the CFTTCP command. Use this command to define the network parameters of partners
for a given type of network.

Related
topics

-   [CFTTCP syntax](../../../command_summary)

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/cnxin">CNXIN</a> </p>
         </td>
         <td>
            <p>Maximum number of sessions allocated to this partner, for 
 incoming connections (server mode).</p>
            <p>The maximum value supported for each system is indicated 
 in the CNXINOUT parameter comment, in tabular form.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/cnxinout">CNXINOUT</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of sessions for communicating with this 
 partner over this network resource.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/cnxout">CNXOUT</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of sessions for outgoing connections with 
 this partner (requester mode).</p>
            <p>The maximum value supported for each system is indicated 
 in the CNXINOUT parameter comment, in tabular form.</p>
            <p>The parameters CNXIN, CNXOUT and CNXINOUT are independent 
 with respect to each other.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name identifying the partner.</p>
            <p>This value makes reference to a partner description (CFTPART 
 ID = ...).</p>
            <p>When ID is set to the CFTPARM command DEFAULT parameter 
 value, the command describes the default network configuration of a calling 
 partner (hence operation in SERVER mode if the partner is only a REQUESTER). 
 In this case, the parameters specific to a partner and the parameters 
 specific to outgoing calls (DIALNO, CNXOUT, RETRY*, O*TIME) are not applicable.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/imaxtime">IMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum time after which the partner can no longer call 
 over this type of network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="imintime.htm">IMINTIME</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Minimum time before which the partner cannot call over 
 this type of network.</p>
            <p>IMINTIME, IMAXTIME hence represent the authorized time 
 slot for calls coming from this partner over this type of network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omaxtime">OMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum time after which the partner can no longer be called 
 over this type of network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omintime">OMINTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Minimum time before which the partner cannot be called 
 over this type of network.</p>
            <p>OMINTIME, OMAXTIME therefore represent the permitted time 
 slot for calling this partner over this type of network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retrym">RETRYM</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of reconnection attempts.</p>
            <p>If this parameter equals 0 and if the initial connection 
 fails, no further reconnection attempts are made.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retryn">RETRYN</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Corresponds to the number of reconnection attempts with 
 a time interval of RETRYW between attempts.</p>
            <p>When RETRYN attempts have been made without success, Transfer 
 CFT divides RETRYN by two and multiplies RETRYW by two and then begins 
 the sequence again up to the total number of times specified (RETRYM).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retryw">RETRYW</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Time interval between reconnection attempts (expressed 
 in minutes).</p>
            <p>Example:</p>
            <p>RETRYW = 01,<br/>RETRYN = 08,<br/>RETRYM = 20</p>
            <p>means:</p>
            <ul>
               <li>eight 
 retries at one-minute intervals,               </li>
               <li>four 
 retries at two-minute intervals,               </li>
               <li>two retries 
 at four-minute intervals,               </li>
               <li>one retry 
 after an eight-minute interval,               </li>
               <li>five 
 retries at sixteen-minute intervals.               </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

## <span id="CFTXXX_CFTTCP_cmd"></span>CFTTCP

z/OS, IBM i , UNIX, Windows

The CFTTCP command defines the network parameters associated with a
partner for a TCP/IP connection.

Each partner can only have one CFTTCP object.

In DELETE mode, the following parameters must be defined:

-   ID parameter
-   CLASS parameter
    if its value is not the default value 1

Only the parameters specific to the CFTTCP object are described. The
complete list of the permitted parameters is nevertheless given below.

<span id="TCP/IP"></span>Command syntax: [CFTTCP](../../../command_summary)

Use this command to define the network parameters associated
with a partner for a TCP/IP connection.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/host">HOST</a>
</p>
         </td>
         <td>
            <p>HOST     = (string64, string64, 
 …)</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/verify">VERIFY</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Option to verify the IIP address (HOST) on an incoming 
 connection request (the first 'n' digits of the caller number are checked).</p>
            <p>If VERIFY = 0, no verification is performed.</p>
            <p> </p>
            <p>The correspondent IP address or the list of correspondent 
 IP addresses with which the user wants to start a session. The maximum 
 number of addresses for this list is 4.</p>
            <p>This address (expressed in the form of a character string) 
 may be defined:</p>
            <ul>
               <li>either 
 with the real IP address in the "dot notation" (for example: 
 192.9.200.10)               </li>
               <li>or with 
 the logical name HOSTNAME associated with the real IP address and configured 
 in the corresponding "database" file (HOST), supplied with any 
 TCP/IP package               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/class">CLASS</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Class of the TCP local resource(s) used to establish the 
 connection with the partner.</p>
            <p>This class value is defined in the CFTNET command corresponding 
 to the network access method used to communicate with the partner.</p>
            <p>This parameter is used for an outgoing connection request, 
 to select this CFTTCP using the protocol imposed by CFTPART (this mechanism 
 allowing several CFTTCP commands to be associated with a CFTPART command).</p>
            <p>This parameter gives rise to a simple verification for 
 an incoming connection request.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="imintime.htm">IMINTIME</a>  </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The minimum time of the authorized time slot for calls 
 coming over this type of network, or with the partner if defined in CFTPART, 
 before which the partner cannot be called.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/imaxtime">IMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The maximum time of the authorized time slot for calls 
 coming over this type of network, or with a partner if defined in CFTPART, 
 after which the partner can no longer be called.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omintime">OMINTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The authorized time slot for calls coming over this type 
 of network. </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/omaxtime">OMAXTIME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The maximum time of the authorized time slot for calls 
 over the network type or by the partner if defined, after which the partner 
 can no longer make a call over this type of network.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retrym">RETRYM</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Use this field to specify the number of reconnection attempts 
 to make with a time interval</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/cnxinout">CNXINOUT</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of communication sessions.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/cnxin">CNXIN</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of sessions for input connections.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/cnxout">CNXOUT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Maximum number of sessions for output connections.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retryw">RETRYW</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The time interval (expressed in minutes) between reconnection 
 attempts.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/retryn">RETRYN</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Use this field to specify the number of reconnection attempts 
 to make with a time interval of retryw 
 between attempts.</p>
         </td>
      </tr>
   </tbody>
</table>

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTTCP   MODE     = CREATE,  
 /* TCP access point  */</p>
            <p> ID   = PARIS5,   /* to the 
 PARIS5 partner     */</p>
            <p>  HOST   = SUN3,</p>
            <p>  RETRYM  = 6,   /* reconnection 
 attempt    */</p>
            <p>  RETRYN   = 4,          /* 
 parameters     */</p>
            <p>  RETRYW   = 2</p>
         </td>
      </tr>
   </tbody>
</table>

The PARIS5 partner has a TCP/IP address corresponding to
the mnemonic SUN3.

The intervals between connection attempts, or retries,
are calculated by the following algorithm:

-   4 retries
    at 2-minute intervals
-   2 retries
    at 4-minute intervals
