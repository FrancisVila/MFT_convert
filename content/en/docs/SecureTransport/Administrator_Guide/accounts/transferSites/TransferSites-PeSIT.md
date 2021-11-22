{
    "title": "PeSIT transfer sites",
    "linkTitle": "PeSIT transfer sites",
    "weight": "250"
}The *Add Transfer Site* page for PeSIT sites presents several sets of options.

Unlike transfer sites for other transfer protocols, a PeSIT transfer site is also used for transfers initiated by the external PeSIT partner (considered client-initiated by {{< SecureTransport/componentshortname  >}}). Only the **Site Name** is required in that case to define the partnership, so a PeSIT transfer site needs only a **Site Name** if it is not used for transfers initiated by the {{< SecureTransport/componentshortname  >}} server on which it is defined.

For a PeSIT transfer site, the **Site Name** designates the destination for an incoming routed transfer. For more information, see <a href="#Select" class="MCXref xref">Set a PeSIT default transfer site for routing</a>.

<span id="General"></span>

## General PeSIT site settings

The following table describes the general options for a PeSIT transfer site.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Remote Partner Settings</strong></p>
<p>This group of options is displayed right below your selection of <strong>Transfer Protocol</strong>: PeSIT.</p>         </td>
      </tr>
      <tr>
         <td>Host         </td>
         <td>The host name or IP address of the remote server to connect to for file transfers. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>Port         </td>
         <td>The port on the remote server to be used for file transfers. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account#Spaces" class="MCXref xref">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>Alternative addresses         </td>
         <td><p>This set of options allow you to add, delete and set a priority order of alternative endpoints. These endpoints act as backup alternatives to the configured Server-Port Site Settings and are particularly useful in cases of transfer failures. Specifying alternative endpoints as backup servers provides a way to temporarily reroute pending transfers and minimize the risk of transfer failure. As with the Server-Port site settings, the connection to each alternative endpoint is defined by its host name (or IP address) and port number.</p>
<ul>
<li>To add an alternative server endpoint, click <strong>New Address</strong>. The Alternative Addresses table expands with a new row, that allows you to enter a hostname (or IP address), a port number and save these changes.</li>
<li>To delete an alternative server endpoint, select the corresponding check-box on the same row and click <strong>Delete</strong>.</li>
<li>To reorder the list of alternative endpoints, click <strong>Reorder</strong>. A new option (upward and downward arrow) appears next to each entry. You must hover with the mouse pointer over this newly appeared option and the mouse pointer will assume the "move" shape: a four-directional arrow pointer. This indicates which alternative endpoint is in focus. You can now drag &amp; drop it up and down to the order number you want it at. Perform this action with other alternative endpoints until the list is ordered according to your needs. When you are done, click <strong>Save Order</strong> to keep the newly changed order.</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Visibility of this option is controlled with the value set for the TransferSite.AlternativeAddresses.retryPolicy configuration option. It allows you to set a "retry policy" with a list of alternative endpoints (presented in IP address: Port number pairs or hostname) you define on this screen. But before you are able to do so, you must go to Operations &gt; Server Configuration and set the policy type using either of the following values:</p>
</blockquote>
<ul>
<li><code>AllHostsOnEachRetry</code> – with this policy {{< SecureTransport/securetransportname  >}} iterates through each endpoint, one by one, starting with the first in the list. If connection not successful, {{< SecureTransport/securetransportname  >}} will continue trying each endpoint one after another until the maximum number of retries is reached. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.</li>
<li><code>OneHostOnEachRetry</code> – with this policy {{< SecureTransport/securetransportname  >}} tries to connect to the first endpoint in the list. If connection not successful, {{< SecureTransport/securetransportname  >}} will continue trying that endpoint until the maximum number of retries is reached; and then will move to the next one in the list. Following that same pattern, {{< SecureTransport/securetransportname  >}} will try each endpoint until success; or until end of list. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.</li>
<li><code>Disabled</code> (default) – this is the default value that keeps the table with endpoints entirely hidden from view.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td><p>The network zone that defines the proxies to use for transfers through this site.</p>
<ul>
<li>Select <strong>none</strong> to connect directly to the remote partner server.</li>
<li>Select <strong>any</strong> to allow {{< SecureTransport/componentshortname  >}} to select the proxy connection using a network zone that enables an SOCKS5 proxy.{{< SecureTransport/componentshortname  >}}</li>
<li>Select <strong>Default</strong> to use the default network zone proxy configuration. If no default network zone is defined, transfers from this transfer site fail.</li>
<li>Select a specific network zone to use the proxy configuration defined for that zone.</li>
</ul>
<p>For more information, see <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones#Specify2" class="MCXref xref">Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Transfer Settings</strong></p>
<p>Please note that the options described appear on display when the <strong>Show Advanced Settings</strong> option is <strong>not</strong> selected. When you select the <strong>Show Advanced Settings</strong> checkbox, these options are moved under <strong>Network Settings</strong>.<span id="TransferSet"></span></p>         </td>
      </tr>
      <tr>
         <td>Use TLS/SSL         </td>
         <td>Requires the use of TLS or SSL for communication with the partner server. When selected, additional fields appear on display.         </td>
      </tr>
      <tr>
         <td>Verify partner's certificate         </td>
         <td><p>Verify the TLS/SSL certificate of the partner site.</p>
<p>This field is displayed when the <strong>Use TLS/SSL</strong> option is selected.</p>
<p>When selected, {{< SecureTransport/componentshortname  >}} verifies whether the server certificate of the partner is chained to a trusted root using the algorithm specified in <code>AgentServers.Ssl.trustAlgorithm</code> server configuration parameter and the certificates imported in the Trusted CAs store.</p>         </td>
      </tr>
      <tr>
         <td>Enable SSL Legacy Mode         </td>
         <td>Requires the use of SSL Legacy mode for communication with the partner server. This field is displayed when the <strong>Use TLS/SSL</strong> option is selected.         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer         </td>
         <td><p>Restrict PeSIT to use only FIPS 140-2 Level 1 certified cryptographic libraries. This field is displayed when the <strong>Use TLS/SSL</strong> option is selected.</p>
<p>When you enable FIPS transfer mode, the panel expands with an additional field that lets you specify the desired set of cipher suites to be used in FIPS mode for server-initiated transfers through this site. By default, this set is populated with the cipher suites as defined in the <code>Pesit.FIPS.SIT.Ciphers</code> configuration option.</p>
<p>You can add or remove cipher suites. The supported FIPS cipher suites from which you can select when adding a new one are listed in <a href="../../../c_st_fipstransfermode#Appendix_FIPS_3980222383_1010689" class="MCXref xref">FIPS transfer mode</a>. Note that both the sender and the recipient must use supported FIPS ciphers suites. Otherwise, the transfer will fail.</p>         </td>
      </tr>
      <tr>
         <td>Login certificate         </td>
         <td><p>The local certificate to use when connecting to the partner site.</p>
<p>By default, the usage of expired X509 certificates is allowed for SIT transfers. To forbid it, set the <code>SIT.allowExpiredCertificates</code> to <code>false</code>.<br />
</p>         </td>
      </tr>
      <tr>
         <td>Partner certificate         </td>
         <td>The login certificate to use when authenticating the remote site.         </td>
      </tr>
   </tbody>
</table>

<span id="Advanced"></span>

## Advanced Settings for PeSIT Transfer sites

Scroll down to the bottom of the screen and click the **Show Advanced Settings** to expand the screen with additional options.

**Note:** Pre-Connection Settings fields have length validation. It is **not** applied by the User Interface (front end validation) when the value is **Expression Language**. In such situations it is the responsibility of the administrator to provide a valid expression and value.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Pre-connection settings</strong>         </td>
         <td><p>Select <strong>Show Advanced Settings</strong> for the following group of options to appear right below.</p>
<p>PeSIT pre-connection settings allow you to map a <em>server ID</em> and <em>password</em> (Server Settings) to the corresponding client-side <em>partner ID</em> and <em>password</em> (Partner Settings).</p>
<p>PeSIT pre-connection acts as a mechanism for additional verification prior to establishing a PeSIT connection.</p>
<p>By default, the <strong>Use Pre-Connection</strong> checkbox is <u>not</u> selected. If you leave it this way, the following rules apply, depending on the {{< SecureTransport/componentshortname  >}} role in Pre-Connection phase: </p>
<ul>
<li>{{< SecureTransport/componentshortname  >}} as <em>Server</em> – {{< SecureTransport/componentshortname  >}} does not validate the received Partner ID and Partner Password.</li>
</ul>
<ul>
<li>{{< SecureTransport/componentshortname  >}} as <em>Client</em> – {{< SecureTransport/componentshortname  >}} sends to the target PeSIT Server the Account name as a Partner ID and the Connection Partner Password (if specified) as Partner Password.</li>
</ul>
<p>When you select the <strong>Use Pre-Connection</strong> checkbox you must add either Server or Partner Settings, or both. In all cases, the Id field is required and the Password field is optional. With the input of Server or Partner Settings, the following rules apply, depending on the {{< SecureTransport/componentshortname  >}} role in the Pre-Connection phase: </p>
<ul>
<li>{{< SecureTransport/componentshortname  >}} as <em>Server</em> – {{< SecureTransport/componentshortname  >}} validates the received Partner ID and Partner Password against the configured Server ID and Server Password.</li>
</ul>
<ul>
<li>{{< SecureTransport/componentshortname  >}} as <em>Client</em> – {{< SecureTransport/securetransportname  >}} sends the configured Partner ID and Partner Password to the target PeSIT Server.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Server Id         </td>
         <td>The ID against which the Server validates the received Partner ID during the Pre-Connection phase. It can contain any symbols (up to 8 characters). Leading or trailing spaces will be trimmed.         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td>Specifies whether a password should be used during the Pre-Connection Phase. When editing a Transfer Site, the passwords are not visible and you can use this checkbox to either keep using the password in the Pre-Connection phase, or remove the password from the Database.         </td>
      </tr>
      <tr>
         <td><p>Password</p>
<p><em>(optional)</em></p>         </td>
         <td>The password against which the Server validates the received Partner password during the Pre-Connection phase. It can contain any symbols (up to 8 characters). White spaces are not allowed. Leading or trailing spaces will be trimmed.         </td>
      </tr>
      <tr>
         <td><p><strong>Partner Settings</strong></p>         </td>
         <td>These options appear when you select <strong>Pre-Connection settings</strong>.         </td>
      </tr>
      <tr>
         <td>Partner Id         </td>
         <td>The ID that the PeSIT client sends during the Pre-Connection phase. It can contain any symbols (up to 8 characters). Leading or trailing spaces will be trimmed.         </td>
      </tr>
      <tr>
         <td><p>Password</p>
<p><em>(optional)</em></p>         </td>
         <td>The password that the PeSIT client sends during the Pre-Connection phase. It can contain any symbols (up to 8 characters). White spaces are not allowed. Leading or trailing spaces will be trimmed.         </td>
      </tr>
      <tr>
         <td>Use Password         </td>
         <td>Specifies whether a password should be used during the Pre-Connection Phase. When editing a Transfer Site, the passwords are not visible and you can use this checkbox to either keep using the password in the Pre-Connection phase, or remove the password from the Database.         </td>
      </tr>
      <tr>
         <td><p><strong>Connection</strong></p>
<p><strong>Settings</strong></p>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td>Server Password Setting         </td>
         <td><p>To use a server password, select <strong>Use Password</strong> and type it in, using literal format or Expression Language. The password is required when a remote partner connects to this Server and password authentication is used. Valid passwords are string values consisting of one to eight characters.</p>         </td>
      </tr>
      <tr>
         <td>Partner Password Settings         </td>
         <td><p>To use a partner password, select <strong>Use Password</strong> and type the password in the field provided. The password is required when this Server connects to a remote partner. Valid passwords are string values consisting of one to eight characters.</p>         </td>
      </tr>
      <tr>
         <td><strong>Transfer Settings</strong>         </td>
         <td><p>These options appear when you select <strong>Show Advanced Settings</strong>.</p>
<p>Please note that when you have not selected the <strong>Show Advanced Settings</strong> checkbox, a different group of options is presented, as described <a href="#TransferSet">here</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p>Enables horizontal online compression, vertical online compression, or both for transfers initiated by the {{< SecureTransport/componentshortname  >}} Server. If the partner PeSIT server does not support the selected compression, no compression is used for these transfers.</p>
<p>{{< SecureTransport/componentshortname  >}} support all types of compression for transfers initiated by the partner PeSIT server.</p>         </td>
      </tr>
      <tr>
         <td>Resync Allowed         </td>
         <td>Enables dynamics resynchronization of exchanges during transfer, without interrupting the data exchange phase.         </td>
      </tr>
      <tr>
         <td>Checkpoint Interval         </td>
         <td><p>The maximum number of bytes in KB (equals 1024 bytes) that the sender may transmit between two consecutive checkpoints. Checkpoints are used to restart the transfer when required.</p>
<p>A value of zero indicates no checkpoints. A value of 65535 indicates an undefined interval.</p>         </td>
      </tr>
      <tr>
         <td>Checkpoint Window         </td>
         <td><p>The greatest difference allowed between the number of the last checkpoint transmitted and the number of the last checkpoint acknowledged. When this number of checkpoints are not acknowledged, the sender suspends data transmission until it receives a checkpoint acknowledgment.</p>
<p>A value of zero indicates that no acknowledgments are required.</p>         </td>
      </tr>
      <tr>
         <td>Connection Timeout         </td>
         <td><p>When SecureTransport acts as a client, the value of this field specifies the amount of time (in seconds) that SecureTransport will wait for an acknowledgment for a transfer.</p>
<p>Default value: the value specified in the <code>Pesit.Client.Inactivity.Timeout</code> configuration option.</p>
<p>Accepted values: positive integers.</p>
<p>If specified, the Connection Timeout value overwrites the <code>Pesit.Client.Inactivity.Timeout</code> value.</p>         </td>
      </tr>
      <tr>
         <td>PeSIT Buffer size         </td>
         <td>The size of the internal buffer for this transfer site in bytes. Valid values are 512 to 65535. A larger buffer improves performance. Specifies the maximum size of a PeSIT data element (PI 25). Should be greater than 800 bytes and less than 65535.         </td>
      </tr>
      <tr>
         <td>User Message Send         </td>
         <td><p>A string sent as PI 99 when the {{< SecureTransport/componentshortname  >}} Server initiates a file transfer to the partner PeSIT server. The field may contain expressions. The tool tip lists valid expressions. If {{< SecureTransport/componentshortname  >}} received the file using PeSIT, it retained the values of all the PeSIT PI codes as metadata and the PeSIT expression language variables contain those values. See also <a href="../../../c_st_expressionlanguage#Appendix_Exp_Lang_Rules_3592148187_1031337" class="MCXref xref">Expression Language</a>, especially <a href="../../../c_st_expressionlanguage/r_st_expressionlanguagepesitvariables#Appendix_Exp_Lang_Rules_3592148187_1021690" class="MCXref xref">PeSIT variables</a>.</p>
<p>The string that results from the evaluation of the expression must be at most 512 characters long.</p>         </td>
      </tr>
      <tr>
         <td>User Message Receive         </td>
         <td><p>A string included in messages sent when the {{< SecureTransport/componentshortname  >}} Server initiates a file transfer from the partner PeSIT server. The field may contain expressions.</p>
<p>The string that results from the evaluation of the expression must be at most 512 characters long.</p>         </td>
      </tr>
      <tr>
         <td>Store and Forward Mode         </td>
         <td><p>Select the Store and Forward mode:
<strong>START_NEW</strong>
or
<strong>PRESERVE</strong>.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>The Store and Forward mode selected here can be overwritten from the Send To Partner step settings.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>Originator         </td>
         <td><ul>
<li>In case of {{< SecureTransport/componentshortname  >}} initiating a new<span id="Pesit_Store&amp;Forward_PI61"></span> Store and Forward transfer, this property specifies the originator (<a href="../../../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes#Pesit_Store&amp;Forward_PI61">PI61</a>) of the transfer.</li>
<li>In case no value is specified in both this filed and the Advanced Routing Send To Partner step setting <strong>Originator</strong>, PI61 is blank.</li>
<li>When the PRESERVE store and forward mode is selected, this field is disabled as PI preserves the PI61 value.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Final Destination         </td>
         <td><ul>
<li>In case of {{< SecureTransport/componentshortname  >}} initiating a new <span id="Pesit_Store&amp;Forward_PI62"></span> Store and Forward transfer, this property specifies the final destination (<a href="../../../c_st_setup/c_st_sentinelintegration/r_st_xfb_toattributes#Pesit_Store&amp;Forward_PI62">PI62</a>) of the transfer.</li>
<li>In case no value is specified in both this field and the Advanced Routing Send To Partner step setting <strong>Final Destination</strong>, PI62 is blank.</li>
<li>When the PRESERVE store and forward mode is selected, this field is disabled as PI preserves the PI62 value.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Network Settings</strong>         </td>
         <td><p>These options appear when you select <strong>Show Advanced Settings</strong>.</p>
<p><strong>Note</strong> The following settings: <strong>Use TLS/SSL</strong> onward are described <a href="#TransferSet">here</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Simultaneous</p>
<p>transfers</p>         </td>
         <td>The maximum number of simultaneous transfers from this transfer site to remote PeSIT systems. A value of zero means no limit.         </td>
      </tr>
      <tr>
         <td>Parallel TCP connections         </td>
         <td>The number of TCP connections to make for parallel TCP (pTCP) to accelerate transfers.         </td>
      </tr>
      <tr>
         <td>Parallel TCP package size         </td>
         <td>The pTCP packet size in bytes.         </td>
      </tr>
      <tr>
         <td>Socket Send / Receive Buffer Size         </td>
         <td>The size of the pTCP buffers in bytes. Specifies the TCP Socket maximum send and receive buffer size in bytes. This setting corresponds to SO_SNDBUF and SO_RCVBUF socket parameters.         </td>
      </tr>
      <tr>
         <td>pTCP connection retry count         </td>
         <td><p>The number of attempts {{< SecureTransport/componentshortname  >}} makes for each TCP connection for pTCP.</p>
<p>When the value of the <strong>Host</strong> field is the address of load balancer for a remote PeSIT cluster, set this field to <em>connections</em> * (<em>nodes</em> - 1), where:</p>
<ul>
<li><em>connections</em> is the value of the <strong>Parallel TCP Connections</strong> field</li>
<li><em>nodes</em> is the number of nodes in the remote PeSIT cluster</li>
</ul>
<p>{{< SecureTransport/componentshortname  >}} retries the connections until all connections are with the same PeSIT remote server.</p>
<p>It specifies the maximum times the SecureTransport will attempt to re-establish a connection with the remote server in case of "Unknown session" error.</p>
<p>This is useful in cases where the remote partner is a PeSIT cluster, the address in the transfer site represents the load balancer in front of the PeSIT cluster and the individual nodes behind the Load Balancer are not accessible.</p>
<p>In such an environment, all connections have to arrive on the same partner node.</p>
<p>Depending on the load balancing configuration different number of retries or no retries (sticky session LB configuration) might be required.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> The options displayed below pTCP connection retry count are described here.

<span id="Advanced2"></span>

## Advanced SSL Settings for PeSIT Transfer sites

Advanced SSL settings allow you to define Cipher suites and SSL protocols with your current PeSIT Transfer Site. Select **Show Advanced SSL Settings** to expand the pane with available options.

 

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Show Advanced SSL Settings</strong>         </td>
      </tr>
      <tr>
         <td>Cipher suites         </td>
         <td><p>The set of cipher suites available with the current PeSIT transfer site for secure SIT connection. By default this set is populated with the cipher suites as defined in the <code>Pesit.SIT.Ciphers</code> configuration option.</p>
<p>To reset to default values, click the button next to the tooltip.</p>         </td>
      </tr>
      <tr>
         <td>Enabled SSL protocols         </td>
         <td><p>The available SSL protocols for secure SIT connection with the current PeSIT transfer sites. By default this list is populated with the SSL protocols as defined in the <code>Pesit.SIT.EnabledProtocols</code> configuration option.</p>
<p>To reset to default values, click the button next to the tooltip.</p>         </td>
      </tr>
   </tbody>
</table>

The following section provides how-to instructions for selecting a default PeSIT transfer site for routing:

-   <a href="#Select" class="MCXref xref">Set a PeSIT default transfer site for routing</a>

<span id="Select"></span>

## Set a PeSIT default transfer site for routing

{{< SecureTransport/componentshortname  >}} implements PeSIT routing as an intermediate partner by sending a received file to a PeSIT transfer site specified as the destination of the PeSIT transfer.

{{< SecureTransport/componentshortname  >}} matches the specified destination to the names of the transfer sites for the account that receives the file. If a transfer site name matches, {{< SecureTransport/componentshortname  >}} transfers the file to that site. No subscription is required. If no transfer site name matches and a default PeSIT transfer site is defined, {{< SecureTransport/componentshortname  >}} transfers the file to that site.

If there is no default site, {{< SecureTransport/componentshortname  >}} checks the **Routing Mode** value for the account. If it is **Reject**, the transfer is rejected before it starts. If it is **Accept**, the transfer is performed and the file is retained locally. If it is **Ignore**, a transfer that cannot be routed is ignored

When {{< SecureTransport/componentshortname  >}} routes a transferred file to a final PeSIT destination, {{< SecureTransport/componentshortname  >}} includes PI 61 and PI 62.

1.  Select **Accounts > User Accounts**. The *User Accounts* page is displayed.
2.  Click the name of the account for which you want to set the default transfer site.
3.  Click the **Transfer Site** tab.
4.  Select the check box next to the name of the PeSIT transfer site you want to make the default.
5.  Click **Set PeSIT Default**.  
    The default is indicated in the transfer site list.

**Related topics:**

-   <a href="../r_st_as2transfersites" class="MCXref xref">AS2 transfer sites</a>
-   <a href="../r_st_connectdirecttransfersites" class="MCXref xref">Connect:Direct transfer sites</a>
-   <a href="../r_st_fileservicesinterfaceprotocoltransfersites" class="MCXref xref">File services interface transfer sites</a>
-   <a href="../r_st_foldermonitortransfersites" class="MCXref xref">Folder Monitor transfer sites</a>
-   <a href="../transfersites-ftp" class="MCXref xref">FTP(S) transfer sites</a>
-   <a href="../transfersites-generichttp" class="MCXref xref">Generic HTTP transfer sites</a>
-   <a href="../transfersites-http" class="MCXref xref">HTTP(S) transfer sites</a>
-   <a href="../transfersites-ssh" class="MCXref xref">SSH transfer sites</a>
-   <a href="../transfersites-s2h" class="MCXref xref">System to Human transfer sites</a>
-   <a href="../t_st_transfersites" class="MCXref xref">Manage transfer sites</a>
