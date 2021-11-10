{
    "title": "Internal user exits",
    "linkTitle": "Internal user exits",
    "weight": "220"
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

[Internal user exits](#intro)

[List of internal user exits](#List_internal_exits)

[Details of internal user exits](#Details_internal_exits)

<span id="intro"></span>

## Internal user exits

This topic describes the internal user exits supplied with Gateway.

Internal exits are implemented via synchronous calls from the Gateway Supervisor module processes to user routines defined in exit source files.

### Exit file locations

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">File (extension)         </th>
<th class="HeadD-Column1-Header1">Location         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Exit header files (<span class="code">.h</span>)</p>         </td>
         <td><p>&lt;Gateway installation directory&gt;<strong>/inc</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Exit source files (<span class="code">.c</span>)</p>         </td>
         <td><p>sub-directories in<br />
<span class="code">&lt;Gateway installation directory&gt;</span><span class="code" style="font-weight: bold;">/src</span></p>         </td>
      </tr>
   </tbody>
</table>

<span id="List_internal_exits"></span>

## List of internal user exits

The following table lists the available internal exits and their associated header and source files.

Follow the links for details about using the exits.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Access Files         </th>
<th class="HeadE-Column1-Header1">User exit         </th>
<th class="HeadD-Column1-Header1">Called...         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="codeBold_in_para">exitsecu.c</span> and <span class="codeBold_in_para">exitsecu.h</span></p>         </td>
         <td><p><a href="#ExitCheckUserLogin">ExitCheckUserLogin</a></p>         </td>
         <td><p>When a user logs on to Gateway</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitCheckUserLogout">ExitCheckUserLogout</a></p>         </td>
         <td><p>When a user logs out of Gateway</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitCheckUserAccessOnObject">ExitCheckUserAccessOnObject</a></p>         </td>
         <td><p>When a user accesses a controlled resource</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitCheckFileAccess">ExitCheckFileAccess</a></p>         </td>
         <td><p>When a user requests a file transfer</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitCheckUserAccess">ExitCheckUserAccess</a></p>         </td>
         <td><p>When a user requests access to a protected resource</p>         </td>
      </tr>
      <tr>
         <td><p><span class="codeBold_in_para">exitcs.c</span> and <span class="codeBold_in_para">exituser.h</span></p>         </td>
         <td><p><a href="#ExitCSLogin">ExitCSLogin</a></p>         </td>
         <td><p>When a user attempts to connect to Gateway from a remote client station</p>         </td>
      </tr>
      <tr>
         <td><p><span class="codeBold_in_para">exitpsit.c</span> and <span class="codeBold_in_para">exituser.h</span></p>         </td>
         <td><p><a href="#ExitPesitMsg">ExitPesitMsg</a></p>         </td>
         <td><p>On reception of FPDU_MSG (PeSIT message user exit routine)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitPesitPreConnection">ExitPesitPreConnection</a></p>         </td>
         <td><p>On receiving a PeSIT pre-connection message (PeSIT pre-connection user exit routine)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitPesitGetAppli">ExitPesitGetAppli</a></p>         </td>
         <td><p>On receiving an incoming PeSIT Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p><span class="codeBold_in_para">et3exitc.c</span> and <span class="codeBold_in_para">et3publi.h</span></p>         </td>
         <td><p><a href="#Et3EncodeParameters">Et3EncodeParameters</a></p>         </td>
         <td><p>In Responder/Sender mode, when representing a bank exchange partner, Gateway calls the Et3EncodeParameters exit function when it receives the ETEBAC 3 parameter card.</p>         </td>
      </tr>
      <tr>
         <td><p>et3exitb.c <span style="font-weight: normal;">and</span> et3publi.h</p>         </td>
         <td><p><a href="#Et3DecodeParameters">Et3DecodeParameters</a></p>         </td>
         <td><p>In Initiator/Sender mode, when representing the client exchange partner, Gateway calls the Et3DecodeParameters exit function with the Gateway parameter card corresponding to the Transfer Request.</p>         </td>
      </tr>
      <tr>
         <td><p>et3exitf.c <span style="font-weight: normal;">and</span> et3exitf.h</p>         </td>
         <td><p><a href="#Et3ExitFProcessing">Et3ExitFProcessing</a></p>         </td>
         <td><p>In Responder/Sender mode, Gateway calls the Et3ExitFProcessing exit function on file reception.</p>         </td>
      </tr>
      <tr>
         <td><p>et5exitb.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#Et5ExitConnectInd">Et5ExitConnectInd</a></p>         </td>
         <td><p>When Gateway operates in server mode and a CONNECT fpdu is received.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitCreateInd">Et5ExitCreateInd</a></p>         </td>
         <td><p>When Gateway operates in server mode and a CREATE fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitDeselectInd">Et5ExitDeselectInd</a></p>         </td>
         <td><p>When Gateway operates in server mode and a DESELECT fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitDtfEndInd">Et5ExitDtfEndInd</a></p>         </td>
         <td><p>When Gateway operates in server mode and a DTF.END fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitSelectInd">Et5ExitSelectInd</a></p>         </td>
         <td><p>When Gateway operates in server mode and a SELECT fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitTransEndInd">Et5ExitTransEndInd</a></p>         </td>
         <td><p>When a TRANS.END fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#Et5ExitOpenInd">Et5ExitOpenInd</a></p>         </td>
         <td><p>When an OPEN fpdu is received</p>         </td>
      </tr>
      <tr>
         <td><p>exitsds.c <span style="font-weight: normal;">and</span> exitsds.h</p>         </td>
         <td><p><a href="#ExitSdsMemo">ExitSdsMemo</a></p>         </td>
         <td><p>On transfer creation</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitSdsLogin">ExitSdsLogin</a></p>         </td>
         <td><p>When a client connects to an SD5 server</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitSdsSelect">ExitSdsSelect</a></p>         </td>
         <td><p>When an SD5 server locates detects a selectable transfer</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitSdsSigPar">ExitSdsSigPar</a></p>         </td>
         <td><p>When a client requests a signature or paraphe (contextual authorization)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitSdsCancel">ExitSdsCancel</a></p>         </td>
         <td><p>The SD5 server calls ExitSdsCancel on each cancel request originating at the client machine.</p>         </td>
      </tr>
      <tr>
         <td><p>exitodt.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#ExitOdtGetAppli">ExitOdtGetAppli</a></p>         </td>
         <td><p>To retrieve a Gateway Application object with OFTP (Odette) protocol</p>         </td>
      </tr>
      <tr>
         <td><p>exitpop3.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#ExitPop3GetAppli">ExitPop3GetAppli</a></p>         </td>
         <td><p>To retrieve a Gateway Application object with POP3 protocol</p>         </td>
      </tr>
      <tr>
         <td><p>exitftp.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#ExitFtpGetAppli">ExitFtpGetAppli</a></p>         </td>
         <td><p>To retrieve a Gateway Application object with FTP protocol</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitFtpSetReturnCode">ExitFtpSetReturnCode</a></p>         </td>
         <td><p>For each FTP command received (except for <span class="code">USER</span>, <span class="code">PASS</span> and <span class="code">SYST</span>)</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitFtpRespPasv">ExitFtpRespPasv</a></p>         </td>
         <td><p>In Responder mode before formatting and sending <span class="code" style="font-weight: bold;">PASV</span> response</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitFtpCmdPort">ExitFtpCmdPort</a></p>         </td>
         <td><p>In Initiator mode before formatting and sending <span class="code" style="font-weight: bold;">PORT</span> command</p>         </td>
      </tr>
      <tr>
         <td><p>exithttp.c <span style="font-weight: normal;">and</span> exithttp.h</p>         </td>
         <td><p><a href="#ExitHttpGetAppli">ExitHttpGetAppli</a></p>         </td>
         <td><p>In server mode, on reception of a PUT or POST HTTP request.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitHttpPutBodyResponseReceived">ExitHttpPutBodyResponseReceived</a></p>         </td>
         <td><p>In client mode, on reception of a PUT or POST request response. Gateway calls the exit after sending the requested file, before it sends the end-of-transfer notification.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitHttpRequestReceived2">ExitHttpRequestReceived2</a></p>         </td>
         <td><p>In server mode, on reception of a request, before processing CGate and pre-connection exits.</p>         </td>
      </tr>
      <tr>
         <td><p>exitlog.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#ExitLogArchived">ExitLogArchived</a></p>         </td>
         <td><p>When the log file is archived</p>         </td>
      </tr>
      <tr>
         <td><p><a href="#ExitLogMessage">ExitLogMessage</a></p>         </td>
         <td><p>Before a record is written in the log file</p>         </td>
      </tr>
      <tr>
         <td><p>exitstat.c <span style="font-weight: normal;">and</span> exituser.h</p>         </td>
         <td><p><a href="#ExitStatMessage">ExitStatMessage</a></p>         </td>
         <td><p>Before a statistics record is formatted and written in the Gateway stat file</p>         </td>
      </tr>
      <tr>
         <td><p>exitstat.c <span style="font-weight: normal;">and</span> exitstat.h</p>         </td>
         <td><p><a href="#ExitStatArchived">ExitStatArchived</a></p>         </td>
         <td><p>When the statistic file is archived</p>         </td>
      </tr>
      <tr>
         <td><p>exitlgin.c <span style="font-weight: normal;">and</span> exitclnt.h</p>         </td>
         <td><p><a href="#ExitLoginParam">ExitLoginParam</a></p>         </td>
         <td><p>Before a user logs in to Gateway. It is executed in the current user process context and is intended for the user to supply the (default) login parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>exitckrq.c <span style="font-weight: normal;">and</span> exitclnt.h</p>         </td>
         <td><p><a href="#ExitCheckXferRequest">ExitCheckXferRequest</a></p>         </td>
         <td><p>Before accessing a file (for a Transfer Request)</p>         </td>
      </tr>
      <tr>
         <td><p>exitfs.c <span style="font-weight: normal;">and</span> exitrte.h</p>         </td>
         <td><p><a href="user_exits_rule_tables#ExitAfterFileStoringEvent">ExitAfterFileStoringEvent</a></p>         </td>
         <td><p>Before scanning a Directory Scanning type Rule Table</p>         </td>
      </tr>
      <tr>
         <td><p>exit temp <span style="font-weight: normal;">and</span> exitrte.h</p>         </td>
         <td><p><a href="user_exits_rule_tables#ExitAfterTemporalEvent">ExitAfterTemporalEvent</a></p>         </td>
         <td><p>Before scanning a Scheduling type Rule Table</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Details_internal_exits"></span>

## Details of internal user exits

<span id="ExitLoginParam"></span>

### Supply login parameters: ExitLoginParam

#### Purpose

This exit is called before you log in to Gateway. It is executed in your process context, and enables you to supply the (default) login parameters.

#### Syntax

void ExitLoginParam ( char \*user\_name,    int szName,    char \*password, int szPass, char \*newpassword, int szNPass )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">ExitLoginParam         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>user_name</p>         </td>
         <td><p>Login name for the user</p>         </td>
      </tr>
      <tr>
         <td><p>szName</p>         </td>
         <td><p>user_name buffer size</p>         </td>
      </tr>
      <tr>
         <td><p>password</p>         </td>
         <td><p>Login password for that user_name</p>         </td>
      </tr>
      <tr>
         <td><p>szPass</p>         </td>
         <td><p>Password buffer size</p>         </td>
      </tr>
      <tr>
         <td><p>newpassword</p>         </td>
         <td><p>New login password</p>         </td>
      </tr>
      <tr>
         <td><p>szNPass</p>         </td>
         <td><p>New password buffer size</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>user_name</p>         </td>
         <td><p>Login name</p>         </td>
      </tr>
      <tr>
         <td><p>password</p>         </td>
         <td><p>Login password for that user_name</p>         </td>
      </tr>
      <tr>
         <td><p>newpassword</p>         </td>
         <td><p>New login password</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckUserLogin"></span>

### Login: ExitCheckUserLogin

#### Purpose

This exit is called after ExitLoginParam when you log in to Gateway. ExitCheckUserLogin validates the login request parameters.

#### Syntax

int ExitCheckUserLogin (void \*\*login\_token, char \*user\_name, char \*password)

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckUserLogin</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>user_name</p>         </td>
         <td><p>User login name</p>         </td>
      </tr>
      <tr>
         <td><p>password</p>         </td>
         <td><p>User login password</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Continue with Gateway security checking</p>         </td>
      </tr>
      <tr>
         <td><p>E_UDENIED</p>         </td>
         <td><p>Login denied by user routine</p>         </td>
      </tr>
      <tr>
         <td><p>E_UALLOWED</p>         </td>
         <td><p>Login accepted by user routine</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckUserLogout"></span>

### Logout: ExitCheckUserLogout

#### Purpose

This exit is called when you log out of Gateway. It allows you to release the user context and liberate allocated space.

#### Syntax

int ExitCheckUserLogout ( void \*login\_token )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckUserLogout</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Return code from the exit routine is ignored</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckUserAccessOnObject"></span>

### Access resource: ExitCheckUserAccessOnObject

#### Purpose

This exit is called when a user accesses a controlled resource, that is, a Gateway object.

Before the user performs a read, write, update, delete or admin operation on a specific Gateway object, such as a Site or an Application, this exit is called to check that the user has the required access rights to the object in question.

#### Syntax

int ExitCheckUserAccessOnObject ( void \*login\_token, int resource, int access ExitObjectRecord\_t \*object )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckUserAccessOnObject</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>resource</p>         </td>
         <td><p>Resource ID (refer to <span class="code">exitsecu.h</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>Requested access type (refer to <span class="code">exitsecu.h</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>object</p>         </td>
         <td><p>Data structure that describes the attributes for the object. This data structure is read only and contains object attributes that identify a unique object instance.</p>
<p>Note that *object is null when:</p>
<ul>
<li>The resource is USER_LOGFILE</li>
<li>A user access request affects a set of objects rather than a specific instance. For example Select(), OpenSet(), CloseSet(), purge().</li>
</ul>
<p>When <span style="font-style: italic;font-weight: bold;">*object</span> is null, return E_UUNDEFINED to pass access control to Gateway.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Continue with Gateway security checking</p>         </td>
      </tr>
      <tr>
         <td><p>E_UDENIED</p>         </td>
         <td><p>Access denied by user routine</p>         </td>
      </tr>
      <tr>
         <td><p>E_UALLOWED</p>         </td>
         <td><p>Access accepted by user routine</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckFileAccess"></span>

### Request file transfer: ExitCheckFileAccess

#### Purpose

When a user requests a file transfer, this exit is called to validate access to the required file. If the exit routine denies access, the Transfer Request is rejected. Otherwise, it is accepted.

The default action in the supplied sample codes always accepts it.

#### Syntax

int ExitCheckFileAccess ( void \*login\_token, char \*file, int access )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckFileAccess</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>file</p>         </td>
         <td><p>File to be transferred</p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>Requested access type (refer to <span class="code">exitsecu.h</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Continue with Gateway security checking</p>         </td>
      </tr>
      <tr>
         <td><p>E_UDENIED</p>         </td>
         <td><p>Access denied by user routine</p>         </td>
      </tr>
      <tr>
         <td><p>E_UALLOWED</p>         </td>
         <td><p>Access accepted by user routine</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckUserAccess"></span>

### Access: ExitCheckUserAccess

#### Purpose

When a user accesses (via read/write/update/delete/admin) a protected resource (Site, Application, Transfer Request, User Record, Access Rights Record, Model, and so on), Gateway calls ExitCheckUserAccess() to validate the access request. If the exit routine accepts the request, the access is honored. If the exit routine denies the request, the access is rejected. If the exit routine doesn't care (default action in the supplied sample codes), Gateway continues the validation with its own user database definition.

The request is accepted if, and only if, at least one of the following conditions exists:

-   the user is an administrator, or
-   the required access on the resource is granted in the associated access rights record

If the required resource is a transfer request, the user must either be the request creator or have the <span style="font-style: italic;">access all transfers</span> privilege.

#### Syntax

<span style="font-weight: bold;">int ExitCheckUserAccess ( void \*login\_token, int resource, int access )</span>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckUserAccess</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to user context</p>         </td>
      </tr>
      <tr>
         <td><p>resource</p>         </td>
         <td><p>Resource ID</p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>Requested access type</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Continue with Gateway security checking</p>         </td>
      </tr>
      <tr>
         <td><p>E_UDENIED</p>         </td>
         <td><p>Access denied by user routine</p>         </td>
      </tr>
      <tr>
         <td><p>E_UALLOWED</p>         </td>
         <td><p>Access accepted by user routine</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCSLogin"></span>

### Remote client login: ExitCSLogin

#### Purpose

This exit enables you to check the identification of a user who attempts to connect to Gateway from a remote client station.

This exit function is linked with the client station server process.

#### Syntax

int ExitCSLogin(char \* username, char \* password)

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCSLogin</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>user_name</p>         </td>
         <td><p>User login name</p>         </td>
      </tr>
      <tr>
         <td><p>password</p>         </td>
         <td><p>User login password</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>login_token</p>         </td>
         <td><p>Pointer to context for user</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>The user is authorized</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>The password is not recognized. The connection request is rejected</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitPesitMsg"></span>

### Receive PeSIT message: ExitPesitMsg

#### Purpose

This user exit routine is called on reception of an FPDU\_MSG. On return, FPDU\_ACKMSG is sent to the partner Site with diagnostic code (PI 2) equal to zero.

<span style="font-weight: bold;">Note:</span> The received <span class="code">msg</span> field is converted into the local machine character set before passing to this EXIT.

#### Syntax

int ExitPesitMsg ( char \*origin, char \*destination, int file\_type, char \*file\_name, int xfer\_id, unsigned char \*msg, int len )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitPesitMsg</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>origin</p>         </td>
         <td><p>PI 3</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>PI 4</p>         </td>
      </tr>
      <tr>
         <td><p>file type</p>         </td>
         <td><p>PI 11</p>         </td>
      </tr>
      <tr>
         <td><p>filename</p>         </td>
         <td><p>PI 12</p>         </td>
      </tr>
      <tr>
         <td><p>transfer ID</p>         </td>
         <td><p>PI 13</p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>PI 91</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>length of <span class="code">msg</span></p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>The return code from the exit routine is ignored.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitPesitPreConnection"></span>

### Pre-connect PeSIT: ExitPesitPreConnection

#### Purpose

PeSIT pre-connection user exit routine. On reception of a PeSIT pre-connection message, this exit is called to validate the message content (user ID and password).

-   If the return code is 1, the request is accepted and a PeSIT ACK message is sent.
-   If the return code is -1, the request is rejected and a PeSIT NAK message is sent.

Other return code values are reserved for future use.

-   If accepted, the "requestor" field can also be filled to indicate the expected requestor ID in the incoming FPDU\_CONNECT. In this case, the requestor ID (PI 3) in the incoming FPDU\_CONNECT must match the specified value.
-   Otherwise the FPDU\_CONNECT is rejected with a diagnostic = 304 (unauthorized requestor ID). If the "requestor" is not filled, the PI 3 value is validated depending on the Gateway Site definition.

<span style="font-weight: bold;">Note:</span> In this exit, all character fields are converted to the character set for the local machine.

#### Syntax

int ExitPesitPreConnection ( char \*userID, char \*password, char \*requestor, int bufsz )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitPesitPreConnection</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>userID</p>         </td>
         <td><p>User ID from the received pre-connection message</p>         </td>
      </tr>
      <tr>
         <td><p>password</p>         </td>
         <td><p>Password from the received pre-connection message</p>         </td>
      </tr>
      <tr>
         <td><p>requestor</p>         </td>
         <td><p>Associated requestor ID to validate</p>         </td>
      </tr>
      <tr>
         <td><p>bufsz</p>         </td>
         <td><p>Buffer size of "requestor" field</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Accept the pre-connection request</p>         </td>
      </tr>
      <tr>
         <td><p>-1</p>         </td>
         <td><p>Refuse the pre-connection request</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitPesitGetAppli"></span>

### Get Application object for PeSIT: ExitPesitGetAppli

#### Purpose

This user exit routine is called when Gateway receives a Transfer Request. It enables users to determine the application to use, based on the protocol elements received.

#### Syntax

Int ExitPesitGetAppli ( const char \*origin, const char \*destination, const char \*file\_type, const char \*file\_name, const char \*xfer\_id, const char \*file\_label, const char \*msg, char \*application, int len )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitPesitGetAppli</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>origin</p>         </td>
         <td><p>PI 3 / PI 61 (in case of Store-and-Forward)</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>PI 4 / PI 62 (in case of Store-and-Forward)</p>         </td>
      </tr>
      <tr>
         <td><p>file_type</p>         </td>
         <td><p>PI 11</p>         </td>
      </tr>
      <tr>
         <td><p>file_name</p>         </td>
         <td><p>PI 12</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_id</p>         </td>
         <td><p>PI 13</p>         </td>
      </tr>
      <tr>
         <td><p>file_label</p>         </td>
         <td><p>PI 37</p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>PI 99</p>         </td>
      </tr>
      <tr>
         <td><p>application</p>         </td>
         <td><p>Buffer for the desired application name</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>Length of application buffer</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>application</p>         </td>
         <td><p>Application to use</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>No application found. Abort the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Use the application returned in application buffer</p>         </td>
      </tr>
      <tr>
         <td><p>0</p>         </td>
         <td><p>No user action. Use the default PeSIT application</p>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1">         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>         </td>
         <td>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitOdtGetAppli"></span>

### Get Application object for OFTP: ExitOdtGetAppli

#### Purpose

Use this OFTP protocol exit routine to retrieve the Gateway Application object to use for the file transfer. This exit allows you to use Gateway Application objects even if both fields of the SFID command are already being used for other purposes.

Gateway calls this exit after receiving an SFID command. The SFID fields are the arguments used to search for the Application name.

The results are stored in the <span class="code">buffer</span> parameter whose size is <span class="code">len</span> bytes. The Gateway internal Application allows you to receive any file. Application characteristics include:

-   You cannot delete or modify this Application
-   No code conversion or record padding is possible with this Application

#### Syntax

int ExitOdtGetAppli ( char \*dest\_alias, char \*filename, time\_t date, char \*user\_field, char \*destination, char \*originator, char \*buffer, int len )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitOdtGetAppli</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>dest_alias</p>         </td>
         <td><p>Remote Site of connection</p>         </td>
      </tr>
      <tr>
         <td><p>filename</p>         </td>
         <td><p>File name set in SFID FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>date</p>         </td>
         <td><p>Date and time field of SFID FPDU, converted to time_t format</p>         </td>
      </tr>
      <tr>
         <td><p>user_field</p>         </td>
         <td><p>Content of user field in SFID FPDU</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>Alias name of final destination</p>         </td>
      </tr>
      <tr>
         <td><p>originator</p>         </td>
         <td><p>Alias name of origin</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>Max length of buffer parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>buffer</p>         </td>
         <td><p>Buffer to store Application name</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Gateway Application found and stored in buffer parameter</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>No Application found: use internal Application</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>No Application found: Transfer Request is rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>The sample function (<span class="code">exitodt.c</span>) provides one example that uses a matching table. You can customize this example to suit your own requirements.</p>         </td>
      </tr>
      <tr>
         <td><p>Additional information</p>         </td>
         <td><p>For more information on OFTP, refer to <a href="../../../protocols_about/oftp_about">About OFTP</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitFtpGetAppli"></span>

### Get Application object for FTP: ExitFtpGetAppli

#### Purpose

This exit is called to retrieve the Application if the Remote Site parameter <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>).

Gateway calls this exit immediately after receiving an FTP <span class="code" style="font-weight: bold;">STOR</span> or <span class="code" style="font-weight: bold;">STOU</span> command. The result must be stored in the <span class="code">buffer</span> parameter whose size is <span class="code">len</span> bytes.

#### Syntax

int <span style="font-weight: bold;">ExitFtpGetAppli</span>(

   char \*<span style="font-weight: bold;">dest\_alias</span>,

   char \*<span style="font-weight: bold;">filename</span>,

   short <span style="font-weight: bold;">data\_code</span>,

   char \*<span style="font-weight: bold;">appli\_name</span>,

   char \*<span style="font-weight: bold;">destination</span>,

   char \*<span style="font-weight: bold;">originator</span>,

   char \*<span style="font-weight: bold;">buffer</span>,

   int <span style="font-weight: bold;">len</span>)

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitFtpGetAppli</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>dest_alias</p>         </td>
         <td><p>Remote Site of connection</p>         </td>
      </tr>
      <tr>
         <td><p>filename</p>         </td>
         <td><p>FTP filename</p>         </td>
      </tr>
      <tr>
         <td><p>short data_code</p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>appli_name</p>         </td>
         <td><p>Content of <span class="code">SITE P_APPLI</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>Alias of final destination</p>         </td>
      </tr>
      <tr>
         <td><p>originator</p>         </td>
         <td><p>Alias of origin</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>Max length of <span class="code">buffer</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>buffer</p>         </td>
         <td><p>Buffer to store Application name</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Application is found and stored in the <span class="code">buffer</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>No Application found and default FTP internal Application used</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>No Application found and Transfer rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>The sample function (<span class="code">exitftp.c</span>) provides an example using a matching table from data code of transfer and destination alias name. Any other method can be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Additional information</p>         </td>
         <td><p>For more information on FTP, refer to <a href="../../../protocols_about/ftp_about">About FTP</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitFtpSetReturnCode"></span>

### Customize FTP: ExitFtpSetReturnCode

#### Purpose

This exit allows customized actions on reception of an FTP command on the server side. It is called for each FTP command received (except for <span class="code">USER</span>, <span class="code">PASS</span> and <span class="code">SYST</span>). Use the exit function to:

-   Do nothing: Gateway continues processing as usual.
-   Supply a return code and message: Gateway skips the command processing and responds immediately with the code and message supplied by the exit. This feature is useful for two reasons:
    -   It simulates a positive completion return code for commands that are not supported.
    -   It forces a negative completion return code for commands that are not accepted.

#### Syntax

int <span style="font-weight: bold;">ExitFtpSetReturnCode</span>(

   int <span style="font-weight: bold;">ftp\_ref</span>,  /\* current ftp reference \*/

   char \*<span style="font-weight: bold;">ftp\_cmd</span>,  /\* current ftp command \*/

   int \*<span style="font-weight: bold;">ftp\_code</span>,  /\* code to be returned \*/

   char \*<span style="font-weight: bold;">ftp\_msg</span>)  /\* message to return \*/

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitFtpSetReturnCode</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>ftp_ref</p>         </td>
         <td><p>The reference for the current control connection for the command.</p>         </td>
      </tr>
      <tr>
         <td><p>ftp_cmd</p>         </td>
         <td><p>The complete FTP command received, including all parameters except CRLF.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>ftp_code</p>         </td>
         <td><p>This parameter is mandatory. It is the code that must be returned in response to this command.</p>
<p>If the ftp_code is set to 0, the exit function does nothing and Gateway processes the command as usual.</p>
<p>If the ftp_code is set to a non-0 value, the command is not processed and Gateway immediately responds with this ftp_code.</p>         </td>
      </tr>
      <tr>
         <td><p>ftp_msg</p>         </td>
         <td><p>This parameter is optional and is only used if the returned ftp_code value is not 0.</p>
<p>If ftp_code is a non-0 value, this is the message sent. If the ftp_code is not 0 and the ftp_msg contains no message (strlen(ftp_msg) is 0), Gateway uses the standard message associated with the ftp_code.</p>
<p>This parameter should not be used unless there is a very specific reason to do so. The message must not exceed 200 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>The return value is always 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Additional information</p>         </td>
         <td><p>For more information on FTP, refer to <a href="../../../protocols_about/ftp_about">About FTP</a>.</p>         </td>
      </tr>
   </tbody>
</table>

#### ExitFtpSetReturnCode default code

This is the code supplied by default with Gateway. It does nothing and lets Gateway behave as if there were no exit function.

int ExitFtpSetReturnCode(int ftp\_ref, char \*ftp\_cmd, int \*ftp\_code, char \*ftp\_msg){  \*ftp\_code = 0;  ftp\_msg\[0\] = 0;if (\*ftp\_code &gt; 0)  LogPrintf(LOG\_INFO, "EXITFTP (%d) reply code set to %d for \\ command \\"%s\\"\\n", ftp\_ref, \*ftp\_code, ftp\_cmd);return(0);}

#### Example 1

Simulating a positive completion response

This example shows how to simulate a positive completion for commands that are not implemented in Gateway.

int ExitFtpSetReturnCode (int ftp\_ref, char \*ftp\_cmd, int \*ftp\_code, char \*ftp\_msg){ \*ftp\_code = 0;  ftp\_msg\[0\] = 0;  if (memcmp(ftp\_cmd, MKD, 3) == 0)  \*ftp\_code = 257;  else if (memcmp(ftp\_cmd, RMD, 3) == 0)  \*ftp\_code = 250;  else if (memcmp(ftp\_cmd, CWD, 3) == 0)  \*ftp\_code = 250;  else if (memcmp(ftp\_cmd, CDUP, 4) == 0)  \*ftp\_code = 200;  if (\*ftp\_code &gt; 0) LogPrintf(LOG\_INFO, "EXITFTP (%d) reply code set to %d for \\ command \\"%s\\"\\n", ftp\_ref, \*ftp\_code, ftp\_cmd);  return(0);}

#### Example 2

Forcing a negative completion response

This example shows how to force a negative completion for some commands. If you decide that the server should never receive files, you should intercept <span class="code">STOR</span> and <span class="code">STOU</span> commands and answer with a 502 (command not implemented) or 532 (need account for storing file) return code. In addition, the <span class="code">ftp\_msg</span> parameter is used to reply with a non-standard message.

int ExitFtpSetReturnCode (int ftp\_ref, char \*ftp\_cmd, int \*ftp\_code, char \*ftp\_msg){ \*ftp\_code = 0;  ftp\_msg\[0\] = 0;  if ((memcmp(ftp\_cmd, STOR, 4) == 0) || (memcmp(ftp\_cmd, STOU, 4) == 0))  { \*ftp\_code = 502;  strcpy(ftp\_msg, Sorry, but this server will refuse \\ any store command);  }  if (\*ftp\_code &gt; 0) LogPrintf(LOG\_INFO, "EXITFTP (%d) reply code set to %d for \\ command \\"%s\\"\\n", ftp\_ref, \*ftp\_code, ftp\_cmd);return(0);}

<span id="ExitFtpRespPasv"></span><span id="ExitFtpCmdPort"></span>

### Customize FTP: ExitFtpRespPasv and ExitFtpCmdPort

The signatures of user exit functions supports IPv6 addresses. Input and output parameters of the exit point to a generic container that is able to store IPv4 and IPv6 addresses. When customizing the exit functions,you need to inspect the sa\_family member of the input parameters and cast this container according to its value (AF\_INET for IPv4 and AF\_INET6 for IPv6).

The provided sample, which works on IPv4 addresses is updated to reflect the changes. For IPv6, the checks need to take into account the length of the address which is 128 bits and the CIDR notation used for defining the mask (number of bits in the address identifying the network <span class="code">-- &lt;address>/&lt;mask>)</span>

#### Purpose

Gateway is designed to be deployed on the front side of a DMZ (DeMilitarized Zone). It is likely to be hidden from peers by a device which translates TCP addresses. Such devices generally intercept and modify FTP <span class="code" style="font-weight: bold;">PORT/EPRT</span> commands and <span class="code" style="font-weight: bold;">PASV/EPSV</span> responses according to the translations applied, so that they remain transparent for peers. However, they cannot intercept and modify in FTP sessions that rely on an encrypted transport layer as with TLS.

In order to support such devices (in a very limited range of applications), the ExitFtpRespPasv and ExitFtpCmdPort exits enable users to translate the address to send to a peer, before encryption.

In Responder mode, Gateway calls ExitFtpRespPasv before formatting and sending a <span class="code" style="font-weight: bold;">PASV/EPSV</span> response.

In Initiator mode, Gateway calls ExitFtpCmdPort before formatting and sending a <span class="code" style="font-weight: bold;">PORT/EPRT</span> command.

The purpose of these two exits is to transform the TCP address that is sent to the FTP peer from the one that locally identifies the bound data port to the one that describes it from the other side of an address translation device (that is, from a LAN to an internet address, or from DMZ or private network to public network address).

Additionally, for informative purposes, ExitFtpRespPasv and ExitFtpCmdPort supply the local and remote addresses of the control session in the local area network. These addresses should be the only data used by the address translation algorithm, and thus should be sufficient to reproduce the translation.

#### Syntax

void ExitFtpRespPasv ( struct sockaddr\_in localCtrlAddr, struct sockaddr\_in remoteCtrlAddr, struct sockaddr\_in \*localDataAddr )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitFtpRespPasv</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>localCtrlAddr</p>         </td>
         <td><p>The value of the local TCP address (IP address and port number) of the control connection, as seen by the local system</p>         </td>
      </tr>
      <tr>
         <td><p>remoteCtrlAddr</p>         </td>
         <td><p>The value of the remote TCP address (IP address and port number) of the control connection, as seen by the local system</p>         </td>
      </tr>
      <tr>
         <td><p>localDataAddr</p>         </td>
         <td><p>Pointer to the local TCP address (IP address and port number) of the data connection, as seen by the local system. This address will be used by FTP to generate the <span class="code" style="font-weight: bold;">PORT/EPRT</span> command / <span class="code" style="font-weight: bold;">PASV/EPSV</span> response. The function is free to change the content of the pointed structure.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>localDataAddr</p>         </td>
         <td><p>Pointer to the local TCP address (IP address + port number) of the data connection, as seen by the local system. This address is be used by FTP to generate the <span class="code" style="font-weight: bold;">PORT/EPRT</span> command / <span class="code" style="font-weight: bold;">PASV/EPSV</span> response. The function is free to change the content of the pointed structure.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>The return value is always 0. There is no error case support for this exit.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

A sample code is provided. It translates the IP part of the given local TCP address of the data session according to a static array, named <span class="code">ipTransTable</span>, and included in <span class="code">exitftp.c</span>.

If the remote address of the control session is in the local area, the local address of the data session is not translated. Local addresses are defined by a second static array, <span class="code">ipLanTable</span>, in <span class="code">exitftp.c</span>, that defines IP patterns and sub-network masks that must match LAN IP addresses. By default, this implementation is surrounded by "#if 0" instructions, and thus is not included in the binary components of Gateway.

<span id="ExitHttpGetAppli"></span>

### Get Application object for HTTP: ExitHttpGetAppli

#### Purpose

This exit is called to retrieve the Application if the Remote Site parameter <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>).

When operating in server mode, Gateway calls this exit on reception of a PUT or POST request.

#### Syntax

<span style="font-weight: bold;">int ExitHttpGetAppli (char \*dest\_alias, char \*filename, short data\_code, char \*appli\_name, char \*destination, char \*originator, char \*buffer, int len)</span>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitHttpGetAppli</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>dest_alias</p>         </td>
         <td><p>Remote Site of the connection</p>         </td>
      </tr>
      <tr>
         <td><p>filename</p>         </td>
         <td><p>Content of protocol filename</p>         </td>
      </tr>
      <tr>
         <td><p>data_code</p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>appli_name</p>         </td>
         <td><p>Content of <span class="code">SITE P_APPLI</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>Alias of the final destination</p>         </td>
      </tr>
      <tr>
         <td><p>originator</p>         </td>
         <td><p>Alias of the transfer originator</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>Max length of buffer parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>buffer</p>         </td>
         <td><p>Buffer to store Application name</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Application is found and stored in the <span class="code">buffer</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>No Application found and default HTTP internal Application used</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>No Application found and Transfer rejected</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitHttpPutBodyResponseReceived"></span>

### Handling received HTML page: ExitHttpPutBodyResponseReceived

#### Purpose

Use this exit to handle the HTML page received in response to a PUT or POST request.

In client mode, Gateway calls this exit on reception of a PUT or POST request. It calls the exit after sending the requested file, before it sends the end-of-transfer notification.

#### Syntax

<span style="font-weight: bold;">void ExitHttpPutBodyResponseReceived (NotifXferRecord\_t \*xfer, char \*request\_url, HttpHeaderField\_t request\[\], int request\_c, char \*response\_status, HttpHeaderField\_t response\[\], int response\_c, char \*response\_body)</span>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitHttpPutBodyResponseReceived</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>xfer</p>         </td>
         <td><p>Transfer file structure as defined in <span class="code">exitxdef.h</span></p>         </td>
      </tr>
      <tr>
         <td><p>request_url</p>         </td>
         <td><p>URL of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>request</p>         </td>
         <td><p>Table containing the HTTP fields used to send the file</p>         </td>
      </tr>
      <tr>
         <td><p>request_c</p>         </td>
         <td><p>Number of elements contained in the table that is specified in the <span style="font-style: italic;">request</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>response_status</p>         </td>
         <td><p>Status line from the HTTP response message</p>         </td>
      </tr>
      <tr>
         <td><p>response</p>         </td>
         <td><p>Table containing the HTTP response message fields</p>         </td>
      </tr>
      <tr>
         <td><p>response_c</p>         </td>
         <td><p>Number of elements contained in the table that is specified in the <span style="font-style: italic;">response</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>response_body</p>         </td>
         <td><p>HTML page identified in <span style="font-style: italic;">response</span></p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitHttpRequestReceived2"></span>

### Collecting HTTP request information: ExitHttpRequestReceived2

#### Purpose

This exit provides the user with information about incoming HTTP requests.

In server mode, Gateway calls this exit on reception of a request, before processing CGate and pre-connection exits.

#### Syntax

<span style="font-weight: bold;">void ExitHttpRequestReceived2 (int ref\_http, In\_TlsSessionInfo\_t \*tls\_infos, char \*sessionId, char \*request\_url, HttpHeaderField\_t request\[\], int request\_c, HttpCgiParam\_t url\_param\[\], int url\_param\_c, HttpCgiParam\_t post\_param\[\], int post\_param\_c, char \*buffer, int len)</span>

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitHttpRequestReceived2</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>ref_http</p>         </td>
         <td><p>Local HTTP transfer context number</p>         </td>
      </tr>
      <tr>
         <td><p>tls_infos</p>         </td>
         <td><p>In_TLS_sessioninfo_t pre-connection exit structure, as defined in<span class="code"> exitxdef.h</span></p>         </td>
      </tr>
      <tr>
         <td><p>sessionId</p>         </td>
         <td><p>Identity of the session (only if this identification method is selected in the <a href="../../../configuration_start_here/config_protocols_about/config_http_options">HTTP options</a> in the configuration menu)</p>         </td>
      </tr>
      <tr>
         <td><p>request_url</p>         </td>
         <td><p>URL of the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>request</p>         </td>
         <td><p>Table containing the HTTP fields used to send the file</p>         </td>
      </tr>
      <tr>
         <td><p>request_c</p>         </td>
         <td><p>Number of elements contained in the table that is specified in the <span class="code">request</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>url_param</p>         </td>
         <td><p>Table containing URL CGI fields for the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>url_param_c</p>         </td>
         <td><p>Number of elements contained in the table that is specified in the <span class="code">url_param</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>post_param</p>         </td>
         <td><p>Table containing URL CGI fields for POST requests</p>         </td>
      </tr>
      <tr>
         <td><p>post_param_c</p>         </td>
         <td><p>Number of elements contained in the table that is specified in the <span class="code">post_param</span> parameter</p>         </td>
      </tr>
      <tr>
         <td><p>len</p>         </td>
         <td><p>Length of the <span class="code">OutProtoSpecS</span> field</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>OutProtoSpecStr</p>         </td>
         <td><p>User field that can receive a string of characters. This string can be passed to the <span class="code">proto_spec_string</span> parameter of the pre-connection exit</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitPop3GetAppli"></span>

### Get Application object for POP3: ExitPop3GetAppli

#### Purpose

This exit is called to retrieve the Application if the Remote Site parameter <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>).

Gateway calls this exit immediately after receiving a mail header. The result must be stored in the <span class="code">buffer</span> parameter whose size is <span style="font-style: italic;">bufsize</span> bytes.

#### Syntax

int ExitPop3GetAppli ( char \*originator, char \*destination, char \*from, char \*to, char \*xfer\_ident, char \*subject, char \*filename, char \*appli\_name, char \*buffer, int bufsize )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitPop3GetAppli</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>originator</p>         </td>
         <td><p>POP3 server ID as defined in the Site object</p>         </td>
      </tr>
      <tr>
         <td><p>destination</p>         </td>
         <td><p>Login USERID as defined in the Site object</p>         </td>
      </tr>
      <tr>
         <td><p>from</p>         </td>
         <td><p>The from: field in mail header</p>         </td>
      </tr>
      <tr>
         <td><p>to</p>         </td>
         <td><p>The to: field in mail header</p>         </td>
      </tr>
      <tr>
         <td><p>xfer_ident</p>         </td>
         <td><p>The message_id: in mail header</p>         </td>
      </tr>
      <tr>
         <td><p>subject</p>         </td>
         <td><p>The subject: field in mail header</p>         </td>
      </tr>
      <tr>
         <td><p>appli_name</p>         </td>
         <td><p>The proposed Application name (if any)</p>         </td>
      </tr>
      <tr>
         <td><p>file_name</p>         </td>
         <td><p>Reserved</p>         </td>
      </tr>
      <tr>
         <td><p>bufsize</p>         </td>
         <td><p>Max length of buffer parameter</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>buffer</p>         </td>
         <td><p>Buffer to store the desired Application name</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Application is found and stored in the "buffer" parameter</p>         </td>
      </tr>
      <tr>
         <td><p>1</p>         </td>
         <td><p>No Application found and default internal Application used</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>No Application found and Transfer rejected</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>The sample function (<span class="code">exitpop3.c</span>) provides an example using the proposed Application name (if any). Any other method can be applied.</p>         </td>
      </tr>
      <tr>
         <td><p>Additional information</p>         </td>
         <td><p>For more information on POP3, refer to <a href="../../../protocols_about/smtp_pop3_about">About SMTP/POP3</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitLogArchived"></span>

### Process log file archive: ExitLogArchived

#### Purpose

This exit is called after archiving the log file, if asynchronous batch processing program for log archiving is not used.

#### Syntax

int ExitLogArchived ( char \*path\_name )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitLogArchived</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>path_name</p>         </td>
         <td><p>Pathname of the file that is archived</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>The return value of this function is always 0</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitStatMessage"></span>

### Create statistics file: ExitStatMessage

#### Purpose

This exit is called before a statistics record is formatted and written in the Gateway stat file. You can use this function to create a specific user STAT file.

#### Syntax

int ExitStatMessage ( NotifXferRecord\_t \*param )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitStatMessage</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>param</p>         </td>
         <td><p>Pointer to the public structure of the Transfer parameters.</p>
<p>Refer to <span class="code">exitxdef.h</span> for more details on the structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>0</p>         </td>
         <td><p>If no stat record is to be formatted by Gateway</p>         </td>
      </tr>
      <tr>
         <td><p>n</p>         </td>
         <td><p>Statistics record format number to be formatted by Gateway</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitStatArchived"></span>

### Leave stats: ExitStatArchived

#### Purpose

This exit is called after archiving the stat file archiving, if asynchronous batch processing program for statistics archiving is not used.

#### Syntax

int ExitStatArchived ( char \*path\_name )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitStatArchived</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>path_name</p>         </td>
         <td><p>Pathname of the file that is archived</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>The return value of this function is always 0</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitCheckXferRequest"></span>

### Check Transfer Request: ExitCheckXferRequest

#### Purpose

This exit is called by a client program when a user issues a Transfer Request. Typical client programs are Gateway commands and operator interface.

Use this exit to check external security or to modify Transfer Requests depending on Gateway username or other external parameters (such as system user).

Note: Unlike other user access control exits which run on the server side, this routine is called from a client program and runs on the client side. Unless ExitCheckXferRequest is in a shared library (such as DLL), you must re-link all client programs when this routine is modified.

#### Syntax

int ExitCheckXferRequest ( char \*itp\_user\_name, ItpXferRequest\_t \*req )

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitCheckXferRequest</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>itp_user_name</p>         </td>
         <td><p>Gateway user name (can be different from system user name)</p>         </td>
      </tr>
      <tr>
         <td><p>req</p>         </td>
         <td><p>Transfer Request to check or modify.</p>
<p>Refer to <span class="code">itpdefs.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>req</p>         </td>
         <td><p>Transfer Request to check or modify.</p>
<p>Refer to <span class="code">itpdefs.h</span> for more details on structure used.</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>E_UUNDEFINED</p>         </td>
         <td><p>Return No exit user action (access accepted)</p>         </td>
      </tr>
      <tr>
         <td><p>E_UDENIED</p>         </td>
         <td><p>Access denied by user routine</p>         </td>
      </tr>
      <tr>
         <td><p>E_UALLOWED</p>         </td>
         <td><p>Access accepted by user routine</p>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitLogMessage"></span>

### Write log file record: ExitLogMessage

#### Purpose

This exit is called before a record is written in the log file.

#### Syntax

int ExitLogMessage(LogMessage \*msg, char \*text)

<table>
         
         
         
         
   
   <thead>
      <tr>
<th colspan="3" class="HeadD-Column1-Header1"><p>ExitLogMessage</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input parameters</p>         </td>
         <td><p>msg</p>         </td>
         <td><p>Pointer to the message descriptor. The message descriptor contains the following parameters:</p>
<ul>
<li>time_t time_stampdate of the event corresponding to the message</li>
<li>char ident[20+1]message identification (example: SUP101W)</li>
<li>int param_countnumber of variable parameters in the message (information not supplied in this version)</li>
<li>char *param_value[20]values of variable parameters in the message (information not supplied in this version)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>text</p>         </td>
         <td><p>Pointer to the message text</p>         </td>
      </tr>
      <tr>
         <td><p>Output parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Return</p>         </td>
         <td><p>EXIT_TO_NOTIF</p>         </td>
         <td><p>Returns the value <span class="code">EXIT_TO_NOTIF</span> if the external exit ExitLogMessageExt_C() must be notified for this log message.</p>         </td>
      </tr>
      <tr>
         <td><p>0</p>         </td>
         <td><p>If the user processing applied on log messages has a very short response time, this normal user routine ExitLogMessage() embedded with the monitor system process (p_sys for UNIX platforms) can be used directly. Whenever a very short response time cannot be guaranteed, it is recommended to implement the user processing code in the external exit ExitLogMessageExt_C().</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About user exits](../)

[User exits and Rule Tables](user_exits_rule_tables)

[User exits in Perl](user_exits_perl)

[About protocols](../../../protocols_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
