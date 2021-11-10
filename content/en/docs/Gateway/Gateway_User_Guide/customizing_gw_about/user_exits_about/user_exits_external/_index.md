{
    "title": "External user exits",
    "linkTitle": "External user exits",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Customizing Gateway Processes

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <span style="color: #8b0000;font-weight: bold;"><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">customizing user exits</span></span><strong>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

[External user exits](#intro)

[List of external user exits](#List_external_exits)

[Details of external user exits](#Details_external_exits)

<span id="intro"></span>

## External user exits

This topic describes the external user exits supplied with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>.

External exit routines are grouped in the following exit families:

-   FT: File Transfer protocol events  
    Protocol session establishment/release, file transfer beginning/completion/abortion

<!-- -->

-   SECS: TLS and SSH Handshake events  
    Refer to [User exits: Security functions](user_exits_security_functions)

On starting, an exit process informs Gateway of the exit families it is expecting.

The following source file samples, located in the <span class="code">&lt;Gateway installation directory></span><span class="code" style="font-weight: bold;">/src/exitextc</span> directory, contain the default implementation of user exits supplied with Gateway:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>exitcnx.c</p>         </td>
         <td><p>FT family exit routines/connection (session) events</p>         </td>
      </tr>
      <tr>
         <td><p>exitxfer.c</p>         </td>
         <td><p>FT family exit routines/transfer events</p>         </td>
      </tr>
      <tr>
         <td><p>exitpcnx.c</p>         </td>
         <td><p>FT family exit routines/protocol connection events</p>         </td>
      </tr>
      <tr>
         <td><p>exitsecs.c</p>         </td>
         <td><p>SECS family TLS exit routines</p>         </td>
      </tr>
      <tr>
         <td><p>exitsech.c</p>         </td>
         <td><p>SECS family SSH exit routines</p>         </td>
      </tr>
      <tr>
         <td><p>exitmisc.c</p>         </td>
         <td><p>FT family exit routines/Site state, Transfer state and log events</p>         </td>
      </tr>
   </tbody>
</table>

Protocol-specific exit routines are supplied with internal routine call mechanisms only. Refer to [Internal user exits](../user_exits_internal).

### Cascadable exits

All cascadable exits are external exit routines that can be implemented in C or in Perl.

Each of these C and Perl routines must return:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>0:</p>         </td>
         <td><p>If nothing has been done, output parameters are discarded.</p>         </td>
      </tr>
      <tr>
         <td><p>1:</p>         </td>
         <td><p>If task has been performed successfully, returned parameters are used.</p>         </td>
      </tr>
      <tr>
         <td><p>–1:</p>         </td>
         <td><p>If an error occurs.</p>         </td>
      </tr>
   </tbody>
</table>

When a cascadable exit is activated, the corresponding C and Perl exit routines are called in this order, until one of them returns 1 or –1. If both return 0, a default exit routine is called. This default exit routine may do nothing at all (if the default behavior requires no specific processing).

Some external exits are not cascadable.

<span id="List_external_exits"></span>

## List of external user exits

The following table lists the available external exits and their associated header and source files.

Follow the links for details about using the exits.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Access Files</p>         </td>
         <td><p>User exit</p>         </td>
         <td><p>Called...</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">exitxfer.c</span> and <span class="code">exitext.h</span> (&amp; Perl)</p>         </td>
         <td><p><a href="#ExitXferBeforeBegin_C">ExitXferBeforeBegin</a></p>         </td>
         <td><p>Before the beginning of a Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitXferAfterBegin_C">ExitXferAfterBegin</a></p>         </td>
         <td><p>After the beginning of a Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitXferAfterEnd_C">ExitXferAfterEnd</a></p>         </td>
         <td><p>When the Transfer is ended</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">exitcnx.c</span> and <span class="code">exitext.h</span></p>         </td>
         <td><p><a href="#ExitIcBeforeInitReq_C">ExitIcBeforeInitReq</a></p>         </td>
         <td><p>Before making an outgoing connection request in initiator mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitIcAfterInitConf_C">ExitIcAfterInitConf</a></p>         </td>
         <td><p>After confirming an outgoing connection request in initiator mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitRcBeforeInitResp_C">ExitRcBeforeInitResp</a></p>         </td>
         <td><p>When an incoming connection request is received in responder mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitIcBeforeTermReq_C">ExitIcBeforeTermReq</a></p>         </td>
         <td><p>Before making an outgoing end of connection request in initiator mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitRcAfterTermInd_C">ExitRcAfterTermInd</a></p>         </td>
         <td><p>When an incoming connection termination request is made in responder mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitIcAfterTermConf_C">ExitIcAfterTermConf</a></p>         </td>
         <td><p>When a confirmation of an outgoing termination of connection request is made in initiator mode</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitBcAbortReq_C">ExitBcAbortReq</a></p>         </td>
         <td><p>Before aborting an outgoing connection</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitBcAbortInd_C">ExitBcAbortInd</a></p>         </td>
         <td><p>When an incoming connection abort is received</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">exitpcnx.c</span> and <span class="code">exitext.h</span> (&amp; Perl)</p>         </td>
         <td><p><a href="#ExitRcProtoConn_C">ExitRcProtoConn</a></p>         </td>
         <td><p>To accept or reject an incoming call</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">exitsecs.c</span> and <span class="code">exitext.h</span></p>         </td>
         <td><p><a href="user_exits_tls#ExitSecsGetSrvPubKey">ExitSecsGetSrvPubKey</a></p>         </td>
         <td><p>To retrieve the SECS server public key</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsSetSrvPubKey">ExitSecsSetSrvPubKey</a></p>         </td>
         <td><p>To set the SECS server public key</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsSessionInit">ExitSecsSessionInit</a></p>         </td>
         <td><p>To initialize the SECS session</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsSessionEnd">ExitSecsSessionEnd</a></p>         </td>
         <td><p>To end the SECS session</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsCheckCertList">ExitSecsCheckCertList</a></p>         </td>
         <td><p>To check the SECS Certification Path</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsComputation">ExitSecsComputation</a></p>         </td>
         <td><p>To compute the public or private SECS key</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsGetCertList">ExitSecsGetCertList</a></p>         </td>
         <td><p>To access a valid certificate to send</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsBuildCaDnList">ExitSecsBuildCaDnList</a></p>         </td>
         <td><p>To build CA accepted authorities DN list (server mode only)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="user_exits_tls#ExitSecsHandshakeDone">ExitSecsHandshakeDone</a></p>         </td>
         <td><p>At the end of the handshake phase</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">exitmisc.c</span> and <span class="code">exitext.h</span></p>         </td>
         <td><p><a href="#ExitSiteState_C">ExitSiteState</a></p>         </td>
         <td><p>Each time a Site state changes (using the <span class="code" style="font-weight: bold;">pelctl start_site</span> and <span class="code" style="font-weight: bold;">pelctl stop_site</span> control commands)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitXferState_C">ExitXferState</a></p>         </td>
         <td><p>Each time the Transfer Request state changes</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitXferMonitor_C">ExitXferMonitor</a></p>         </td>
         <td><p>Each time a Transfer must be routed (also available in Perl)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitLogMessageExt_C">ExitLogMessageExt</a></p>         </td>
         <td><p>When the internal ExitLogMessage() user exit selects a message. ExitLogMessageExt() is recommended when user processing on log messages does not have a short response time.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Details_external_exits"></span>

## Details of external user exits

<span id="ExitXferBeforeBegin_C"></span>

### Pre-process Transfer Request: ExitXferBeforeBegin\_C

#### Purpose

This exit is called before the beginning of a Transfer Request.

#### Syntax

 

int ExitXferBeforeBegin\_C(In\_SessionInfo\_t \*si, In\_ExitXferBeforeBegin\_t \*in, Out\_ExitXferBeforeBegin\_t \*out)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitXferBeforeBegin_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *si</p>         </td>
         <td><p>Structure that comprises TLS or SSH session parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitXferBeforeBegin_t *in</p>         </td>
         <td><p>Structure that comprises Transfer record parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitXferBeforeBegin_t *out</p>         </td>
         <td><p>Structure that comprises Transfer parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitXferAfterBegin_C"></span>

### In-process Transfer Request: ExitXferAfterBegin\_C

#### Purpose

This exit is called after the beginning of a Transfer Request.

#### Syntax

int ExitXferAfterBegin\_C (In\_TlsSessionInfo\_t \*si, In\_ExitXferAfterBegin\_t \*in, Out\_ExitXferAfterBegin\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitXferAfterBegin_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *si</p>         </td>
         <td><p>Structure that comprises TLS or SSH session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitXferAfterBegin_t *in</p>         </td>
         <td><p>Structure that comprises Transfer record parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitXferAfterBegin_t *out</p>         </td>
         <td><p>Structure that comprises Transfer parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitXferAfterEnd_C"></span>

### Post-process Transfer Request: ExitXferAfterEnd\_C

#### Purpose

This exit is called when the Transfer is ended.

#### Syntax

int ExitXferAfterEnd\_C ( In\_TlsSessionInfo\_t \*si, In\_ExitXferAfterEnd\_t \*in, Out\_ExitXferAfterEnd\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitXferAfterEnd_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *si</p>         </td>
         <td><p>Structure that comprises TLS or SSH session parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitXferAfterEnd_t *in</p>         </td>
         <td><p>Structure that comprises Transfer record parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitXferAfterEnd_t *out</p>         </td>
         <td><p>Structure that comprises Transfer parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitXferMonitor_C"></span>

### Processing routed Transfer Request: ExitXferMonitor\_C

#### Purpose

This exit is called whenever the Transfer is routed.

#### Syntax

int ExitXferMonitor\_C ( In\_ExitXferMonitor\_t \*in,   OutIn\_ExitXferMonitor\_t \*out\_in, Out\_ExitXferMonitor\_t \*out )

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">ExitXferMonitor_C</span></p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitXferMonitor_t *in</p>         </td>
         <td><p>Structure that comprises Transfer record parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output/input parameter</p>         </td>
         <td><p>OutIn_ExitXferMonitor_t *out_in</p>         </td>
         <td><p>This structure is used as both an input and an output structure.</p>         </td>
      </tr>
      <tr>
         <td><p>integer_user_param1</p>
<p>integer_user_param5</p>         </td>
         <td><p>User variables of type Integer</p>         </td>
      </tr>
      <tr>
         <td><p>string_user_param1</p>
<p>string_user_param5</p>         </td>
         <td><p>User variables of type String</p>         </td>
      </tr>
      <tr>
         <td><p>appli_user_param1appl</p>
<p>i_user_param2</p>         </td>
         <td><p>User variables relating to the Application object. It is highly recommended that you do not modify these variables in the exit.</p>         </td>
      </tr>
      <tr>
         <td><p>cgate_user_param1cgate</p>
<p>_user_param2</p>         </td>
         <td><p>User variables relating to the selected CGate object. It is highly recommended that you do not modify these variables in the exit.</p>         </td>
      </tr>
      <tr>
         <td><p>site_user_param1site</p>
<p>_user_param2</p>         </td>
         <td><p>User variables relating to the local Site object. It is highly recommended that you do not modify these variables in the exit.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameter</p>         </td>
         <td><p>Out_ExitXferMonitor_t *out</p>         </td>
         <td><p>Output structure that determines routing behavior for Transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>exec_type</p>         </td>
         <td><p>Execution type (Integer)</p>         </td>
      </tr>
      <tr>
         <td><p>link_to_xfer</p>         </td>
         <td><p>Parameter used to link input and output Transfers</p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-style: italic;">model_name</span></p>         </td>
         <td><p>Name of Model to apply</p>         </td>
      </tr>
      <tr>
         <td><p>perl_script_name</p>         </td>
         <td><p>Absolute path of Perl script to execute</p>         </td>
      </tr>
      <tr>
         <td><p>command_line</p>         </td>
         <td><p>Command line to execute</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameters value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error occurred. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitIcBeforeInitReq_C"></span>

### Pre-connection request: ExitIcBeforeInitReq\_C

#### Purpose

This exit is called on the initiator Site before sending a protocol connection request to a Remote Site.

#### Syntax

int ExitIcBeforeInitReq\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitIcBeforeInitReq\_t \*in, Out\_ExitIcBeforeInitReq\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitIcBeforeInitReq_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitIcBeforeInitReq_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitIcBeforeInitReq_t *out</p>         </td>
         <td><p>Structure that comprises protocol connection parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing. Gateway retries the connection request two seconds later and calls this exit routine again.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitIcAfterInitConf_C"></span>

### Confirm outgoing: ExitIcAfterInitConf\_C

#### Purpose

I: Initiator mode, c: connection, AfterInitConf: After Initialization Confirmation.

This exit is called whenever confirmation of an outgoing connection request is made in Initiator mode.

Use this user routine to:

-   Check identification parameters that the Remote Site returns in the connection confirmation
-   Decide whether Gateway can start transfers on this connection or should abort the connection

#### Syntax

int ExitIcAfterInitConf\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitIcAfterInitConf\_t \*in, Out\_ExitIcAfterInitConf\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitIcAfterInitConf_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitIcAfterInitConf_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitIcAfterInitConf_t *out</p>         </td>
         <td><p>Structure that comprises protocol connection parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitRcBeforeInitResp_C"></span>

### Confirm incoming: ExitRcBeforeInitResp\_C

#### Purpose

R: Responder mode, c: connection, BeforeInitResp: Before Initialization Response

This exit is called whenever an incoming connection request is received in Responder mode.

This exit is used to check identification parameters sent by a Remote Site and to determine whether or not Gateway should accept incoming connection indications.

#### Syntax

int ExitRcBeforeInitResp\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitRcBeforeInitResp\_t \*in, Out\_ExitRcBeforeInitResp\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitRcBeforeInitResp_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitRcBeforeInitResp_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitRcBeforeInitResp_t *out</p>         </td>
         <td><p>Structure that comprises protocol connection parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitIcBeforeTermReq_C"></span>

### Terminate outgoing: ExitIcBeforeTermReq\_C

#### Purpose

I: initiator mode, c: connection, BeforeTermReq: Before Termination Request

This exit is called whenever an outgoing termination of connection request is to be made in initiator mode.

#### Syntax

int ExitIcBeforeTermReq\_C ( In\_TlsSessionInfo\_t \*tls,   In\_ExitIcBeforeTermReq\_t \*in )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitIcBeforeTermReq_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitIcBeforeTermReq_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitRcAfterTermInd_C"></span>

### Terminate incoming: ExitRcAfterTermInd\_C

#### Purpose

R: Responder mode, c: connection, AfterTermInd: After Termination Indication

This exit is called in responder mode,  whenever an incoming connection termination request is made.

#### Syntax

int ExitRcAfterTermInd\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitRcAfterTermInd\_t \*in )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitRcAfterTermInd_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitRcAfterTermInd_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitIcAfterTermConf_C"></span>

### Terminate outgoing: ExitIcAfterTermConf\_C

#### Purpose

I: initiator mode, c: connection, AfterTermConf: After Termination Confirmation.

This exit is called whenever confirmation of an outgoing termination of a connection request is made in initiator mode.

#### Syntax

int ExitIcAfterTermConf\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitIcAfterTermConf\_t \*in )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitIcAfterTermConf_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitIcAfterTermConf_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitBcAbortReq_C"></span>

### Abort outgoing: ExitBcAbortReq\_C

#### Purpose

B: Both initiator and responder mode, c: connection, AbortReq: Abort Request

This exit is called in both initiator and responder mode whenever an abort request is to be made for an outgoing connection.

#### Syntax

int ExitBcAbortReq\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitBcAbortReq\_t \*in )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitBcAbortReq_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitBcAbortReq_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitBcAbortInd_C"></span>

### Abort incoming: ExitBcAbortInd\_C

#### Purpose

B: Both initiator and responder mode, c: connection, AbortInd: Abort Indication.

This exit is called whenever an abort indication is received for an incoming connection.

#### Syntax

int ExitBcAbortInd\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitBcAbortInd\_t \*in )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitBcAbortInd_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitBcAbortInd_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitRcProtoConn_C"></span>

### Incoming call: ExitRcProtoConn\_C

#### Purpose

R: Responder mode, c: connection, ProtoConn: Protocol Connection

This exit is called to accept or reject an incoming call.

#### Syntax

int ExitRcProtoConn\_C ( In\_TlsSessionInfo\_t \*si\_info, In\_ExitRcProtoConn\_t \*in, Out\_ExitRcProtoConn\_t \*out )

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitRcProtoConn_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *si</p>         </td>
         <td><p>Structure that comprises TLS or SSH session parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitRcProtoConn_t *in</p>         </td>
         <td><p>Structure that comprises protocol connection parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>Out_ExitRcProtoConn_t *out</p>         </td>
         <td><p>Structure that comprises protocol connection parameters modified by user.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done. Discards output parameters and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully. Uses returned parameter value and proceeds normally.</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Incoming call rejected or error.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitLogMessageExt_C"></span>

### Process log message: ExitLogMessageExt\_C

#### Purpose

This exit is called for messages that were selected by the internal ExitLogMessage() user exit.

To select a message, ExitLogMessage() must return the value EXIT\_TO\_NOTIF each time it is called with this message.

-   If user processing applied to log messages has a very short response time, you can use the internal exit ExitLogMessage() directly. This exit is embedded with the monitor system process (p\_sys for UNIX platforms).
-   If a very short response time cannot be guaranteed, it is recommended that you implement this external exit ExitLogMessageExt\_C().

#### Syntax

int ExitLogMessageExt\_C (In\_ExitLogMessageExt\_t \*in)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitLogMessageExt_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitLogMessageExt_t *in</p>         </td>
         <td><p>Structure that comprises message parameters.</p>
<p>Refer to the description of <span class="code">exitxdef.h</span> for more information on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error. Aborts current processing</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitSiteState_C"></span>

### Site state change: ExitSiteState\_C

#### Purpose

This exit is called each time the state of a Site changes (via the<span class="code"></span><span class="code" style="font-weight: bold;">pelctl start\_site</span><span class="code"></span>and<span class="code"></span><span class="code" style="font-weight: bold;">pelctl stop\_site</span><span class="code"></span>commands).

#### Syntax

int ExitSiteState\_C ( In\_TlsSessionInfo\_t \*tls, In\_ExitSiteState\_t \*in)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitSiteState_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_TlsSessionInfo_t *tls</p>         </td>
         <td><p>Structure that comprises TLS session parameters.</p>
<p>Refer to the description of <span class="code">exitxdef.h</span> for more information on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>In_ExitSiteState_t *in</p>         </td>
         <td><p>Structure that comprises Site parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error: Aborts current processing</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitXferState_C"></span>

### Transfer Request state change: ExitXferState\_C

#### Purpose

This exit is called each time the state of a Transfer Request changes.

#### Syntax

int ExitXferState\_C  ( In\_ExitXferState\_t \*in)

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>ExitXferState_C</p>         </td>
      </tr>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>In_ExitXferState_t *in</p>         </td>
         <td><p>Structure that comprises Transfer parameters.</p>
<p>Refer to the description of <span class="code">exitxdef.h</span> for more information on structures used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Nothing done</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Task performed successfully</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Error: Aborts current processing</p>         </td>
      </tr>
   </tbody>
</table>

 

Related topics

[About user exits](../)

[User exits: Security functions](user_exits_security_functions)

[TLS user exits](user_exits_tls)

[SSH user exits](user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
