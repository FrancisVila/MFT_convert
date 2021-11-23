{
    "title": "User exits: Security functions",
    "linkTitle": "User exits: security functions",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Customizing Gateway Processes

[Overview](#Overview)

[Activating Security exits](#Activating)

[SECS exit scheduling mechanisms](#SECS)

[Return values](#Return)

[Shared parameters](#Shared_parameters)

<span id="Overview"></span>

## Overview

The Handshake negotiation at the start of each TLS and SSH layer session enables the client to authenticate the server identity by using public key techniques (and, optionally, for the server to authenticate the client). It also enables the client and server to cooperate in creating symmetric keys for encryption, decryption, and detection of modifications.

User exits provide you with a means of customizing the way these services are processed.

For details about the individual security exits, refer to:

-   [TLS user exits](../user_exits_tls)
-   [SSH user exits](../user_exits_ssh)

<span id="Activating"></span>

## Activating Security exits

To activate security exit function process calls:

-   In the configuration menu, set the
    **[Connection control method](../../../../configuration_start_here/config_gateway_paras#connection_control_method)** parameter to <span style="font-style: italic;">Exit</span>.  
    See *Security Guide > [Managing TLS Security Profiles](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/TLS_Security_profiles__GUI_.htm)* and *Security Guide > [Managing TLS Security Profiles (command line)](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/TLS/managing_tls_security_profiles_CLI.htm)* for further information.
-   For SSH, activate the <span class="code" style="font-weight: bold;">exit\_scheduling</span> parameter.  
    See *Security Guide > [Managing SSH Security Profiles](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/SSH_Security_profiles__GUI_.htm)* and
    *[Managing SSH Security Profiles (command line)](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/SSH/managing_ssh_security_profiles_CLI.htm)* for further information.

<span id="SECS"></span>

## SECS exit scheduling mechanisms

Gateway exit scheduling is based on user exit routine mechanisms that occur in the Supervisor Module (SUP) of the Gateway server. These mechanisms are referred to in Gateway documentation as <span style="font-style: italic;">notif</span> mechanisms.

The following schema illustrates how the Gateway Supervisor Module (SUP) user exit mechanism (notif) schedules security exits.

<img src="/Images/Gateway/SECexit.png" class="mediumWidth" />

1.  If activated in the configuration, during the handshake process the SECS process calls an exit. The Supervisor process (SUP) registers the request and places it in a queue.
2.  One of the SECS <span style="font-style: italic;">notif</span> family user processes (SUP exit mechanisms) retrieves the request from the queue, processes it and returns a response to the Supervisor. To process the request, the <span style="font-style: italic;">notif</span> process uses user-specified processing code.
3.  The Supervisor then transmits the response to the request sender: SECS.

<span id="Return"></span>

## Return values

A Security exit routine returns the following two types of value to the Gateway Supervisor (SUP) process:

-   [Exit processing return code](#return_code)
-   [Application operation result values](#result_value)

<span id="return_code"></span>

### Exit processing return code

Each exit routine returns an integer value. This value is a return code that indicates the general result of the exit execution. The following table lists the possible return values and their meanings.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Value</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1</p>         </td>
         <td><p>Exit function execution is correct.</p>         </td>
      </tr>
      <tr>
         <td><p>0</p>         </td>
         <td><p>No operation was carried out during the exit call. Gateway must use internal mechanisms to perform the function.</p>
<p>This value is useful when you do not want to use all exits.</p>         </td>
      </tr>
      <tr>
         <td><p>–1</p>         </td>
         <td><p>A fatal error occurred while executing the exit function. The current session is aborted.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="result_value"></span>

### Application operation result value: status and reason fields

The status field takes one of the following values:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Value</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>0</p>         </td>
         <td><p>The exit function result is OK (for example, the received certification path is correct, or the RSA computation returns an acceptable result).</p>         </td>
      </tr>
      <tr>
         <td><p>–1</p>         </td>
         <td><p>The exit function returned a value that leads to a disconnection or to a TLS alert. For example, from the accepted authorities DN list, it was impossible to build a valid certification path to send to the server.</p>         </td>
      </tr>
   </tbody>
</table>

If the status field is set to <span class="code">–1</span>, you can specify a reason for the disconnection (for example, the certification path received was too long). Recognized reason values are available in the <span class="code">exitxdef.h</span> file and are exit-dependent. Gateway interprets recognized reason values to send TLS Alerts.

<span style="font-weight: bold;">Warning:</span> <span style="font-style: italic;">Do not confuse the status and reason fields with the overall return code defined above.</span>

### Examples

ExitSecsCheckCertList

#### Example 1

The certificate verification process is performed via an access to an OCSP (Online Certificate Status Protocol ) server. This server is down and a connection timeout indicates that the server was unreachable. Your exit program returns an overall return code of <span class="code">–1</span>.

#### Example 2

If both the OCSP server answers and the certification path are valid, the overall return code is <span class="code">1</span> and the output status must be set to <span class="code">0</span>. There is no need to complete the reason field.

#### Example 3

If the server indicates that one of the path certificates was revoked, the overall return code is still <span class="code">1</span> since there was no error while processing the verification. However, the output status must be set to <span class="code">–1</span>. You then specify the reason as ITP\_SECS\_CERT\_REVOKED, as defined in <span class="code">secsudefs.h</span>, which you should include.

<span id="Shared_parameters"></span>

## Shared parameters

### Session identifier: session\_identifier

To establish a correlation between various exits (exits called in the same TLS/SSL or SSH session), a session identifier is provided in each exit input structure in the<span class="code"> exitxdef.h</span> file. For each secured session, the session identifier remains the same throughout the duration of the session and while Gateway is running.

### SECS user context: secs\_ucontext

A user context field is provided in each exit output and input structure (except for the <span class="code">In\_ExitSecsInit\_t</span> structure). It enables you to maintain and modify your own session context.

This user context field can be modified at any step of the exit function call. This new value is taken into account and is provided in the next exit input structure.

Related topics

[About user exits](../../)

[External user exits](../)

[TLS user exits](../user_exits_tls)

[SSH user exits](../user_exits_ssh)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
