{
    "title": "AS2 transfer sites",
    "linkTitle": "AS2 transfer sites",
    "weight": "190"
}Although transfers use the AS2 protocol function in a different way than the other supported protocols, you can subscribe accounts with AS2 transfer sites to applications. Among the standard applications, the Site Mailbox and Standard Router applications are appropriate for an AS2 transfer site.

Unlike transfer sites for other transfer protocols, an AS2 transfer site is also used for transfers initiated by the remote AS2 site (considered client-initiated by SecureTransport). Only the fields marked with an asterisk (`*`) as required are needed to define the partnership to enable these transfers.

For detailed information about AS2 transfers, see [AS2 transfers](../../../c_st_as2transfers).

The following table describes the AS2 protocol options for defining a transfer site.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2"><strong><span>SecureTransport</span> Server Settings</strong>
         </td>
      </tr>
      <tr>
         <td>AS2 Name<span>*</span>         </td>
         <td>
            <p>The local partnership name, which the remote AS2 site uses to identify to this <span>SecureTransport</span> Server. Each AS2 transfer site for a user must have a unique AS2 Name.</p>
            <p>You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account">Spaces in required fields</a>.</p>
         </td>
      </tr>
      <tr>
         <td>Signing Certificate         </td>
         <td>(Optional) The alias that represents the server or partner certificate used to sign a message.         </td>
      </tr>
      <tr>
         <td>Encryption Certificate         </td>
         <td>(Optional) The alias that represents the server or partner certificate used to encrypt a message.         </td>
      </tr>
      <tr>
         <td>Email         </td>
         <td>The email address used to receive information from the remote AS2 site. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td colspan="2"><strong>Remote Site Settings</strong>
         </td>
      </tr>
      <tr>
         <td>AS2 Name<span>*</span>         </td>
         <td>The remote partnership name, which the <span>SecureTransport</span> Server uses to identify to the remote AS2 site. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>URL         </td>
         <td>The URL used to access the remote site. For example, <code>https://as2.example.com:10443</code>,<code>https://172.23.34.45:10443</code>, or <code>https://[FC00:1234:2345:3456::]:10443</code>. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td>Alternative addresses         </td>
         <td>
            <p>This set of options allow you to add, delete and set a priority order of alternative endpoints. These endpoints act as backup alternatives to the configured Server-Port Site Settings and are particularly useful in cases of transfer failures. Specifying alternative endpoints as backup servers provides a way to temporarily reroute pending transfers and minimize the risk of transfer failure. With the AS2 transfer sites, the connection to each alternative endpoint is defined by its URL.</p>
            <ul>
               <li>To add an alternative server endpoint, click <b>New Address</b>. The Alternative Addresses table expands with a new row, that allows you to enter a hostname (or IP address), a port number and save these changes.               </li>
               <li>To delete an alternative server endpoint, select the corresponding check-box on the same row and click <b>Delete</b>.               </li>
               <li>To reorder the list of alternative endpoints, click <b>Reorder</b>. A new option (upward and downward arrow) appears next to each entry. You must hover with the mouse pointer over this newly appeared option and the mouse pointer will assume the "move" shape: a four-directional arrow pointer. This indicates which alternative endpoint is in focus. You can now drag &amp; drop it up and down to the order number you want it at. Perform this action with other alternative endpoints until the list is ordered according to your needs. When you are done, click <b>Save Order</b> to keep the newly changed order.                </li>
            </ul>
            <p> Visibility of this option is controlled with the value set for the <code>TransferSite.AlternativeAddresses.retryPolicy</code> configuration option. It allows you to set a "retry policy" with a list of alternative endpoints (presented in URLs with AS2 transfer sites) you define on this screen. But before you are able to do so, you must go to <b>Operations &gt; Server Configuration</b> and set the policy type using either of the following values:</p>
            <ul>
               <li><code>AllHostsOnEachRetry</code> – with this policy <span>SecureTransport</span> iterates through each endpoint, one by one, starting with the first in the list. If connection not successful, <span>SecureTransport</span> will continue trying each endpoint one after another until the maximum number of retries is reached. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.               </li>
               <li><code>OneHostOnEachRetry</code> –   with this policy <span>SecureTransport</span> tries to connect to the first endpoint in the list. If connection not successful, <span>SecureTransport</span> will continue trying that endpoint until the maximum number of retries is reached; and then will move to the next one in the list. Following that same pattern, <span>SecureTransport</span> will try each endpoint until success; or until end of list. You can set the maximum retry value by editing the <code>EventQueue.maxRetryCount</code> configuration option.                </li>
               <li><code>Disabled</code> (default) – this is the default value that keeps the table with endpoints entirely hidden from view.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>Network Zone         </td>
         <td>
            <p>The network zone that defines the proxies to use for transfers through this site.</p>
            <ul>
               <li>Select <strong>none</strong> to connect directly to the partner AS2 server.               </li>
               <li>Select <strong>any</strong> to allow <span>SecureTransport</span> to select the proxy connection using a network zone that enables an HTTP proxy.               </li>
               <li>Select <strong>Default</strong> to use the default network zone proxy configuration. If no default network zone is defined, transfers from this transfer site fail.               </li>
               <li>Select a specific network zone to use the proxy configuration defined for that zone.               </li>
            </ul>
            <p>For more information, see <a href="../../../c_st_setup/c_st_networkzones/t_st_networkzones">Specify TM Server communication ports and IP address for protocol servers on SecureTransport Edge</a>.</p>
         </td>
      </tr>
      <tr>
         <td>Enable FIPS Transfer Mode         </td>
         <td>
            <p>Restrict AS2 to use only FIPS 140-2 Level 1 certified cryptographic libraries.</p>
            <p>When you enable FIPS transfer mode, the panel expands with an additional field that lets you specify the desired set of cipher suites  to be used in FIPS mode for server-initiated transfers through this site. By default, this set is populated with the cipher suites as defined in the <code>As2.FIPS.SIT.Ciphers</code> configuration option. </p>
            <p>You can add or remove cipher suites. The supported FIPS cipher suites  from which you can select when adding a new one are listed in <a href="../../../c_st_fipstransfermode/r_st_required_ciphers_cipher_suites">Advertised ciphers and cipher suites</a>. Note that both the sender and the recipient must use supported FIPS ciphers suites. Otherwise,  the transfer will fail.</p>
         </td>
      </tr>
      <tr>
         <td>Signing Certificate         </td>
         <td>(Optional) The alias that represents the user or partner certificate used to sign a message from this site.         </td>
      </tr>
      <tr>
         <td>Encryption Certificate         </td>
         <td>(Optional) The alias that represents the user or partner certificate used to encrypt a message from this site.         </td>
      </tr>
      <tr>
         <td>Email         </td>
         <td>The email address used to receive information from <span>SecureTransport</span> Server. You cannot enter spaces-only values in this field. For more information, see <a href="../../useraccounts/t_st_create_user_account">Spaces in required fields</a>.         </td>
      </tr>
      <tr>
         <td colspan="2">  <span>*</span> Each AS2 transfer site must have a unique combination of <span>SecureTransport</span> Server AS2 Name and Remote Site AS2 Name.         </td>
      </tr>
   </tbody>
</table>

## Transfer Settings: Send Options

This subtopic provides descriptions on the Send Options and Receive Options pages for AS2 transfer sites.

The following table describes the Send Options for an AS2 transfer site.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2"><b>Send options</b>
         </td>
      </tr>
      <tr>
         <td>Send File As         </td>
         <td>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name. When you enter a new file name in this field, the AS2 message header uses the new name as the value for <code>original filename</code>.         </td>
      </tr>
      <tr>
         <td colspan="2"><i>Transfer Settings</i>
         </td>
      </tr>
      <tr>
         <td>Subject         </td>
         <td>The MIME subject to be used for outgoing messages.         </td>
      </tr>
      <tr>
         <td>Mimetype         </td>
         <td>The MIME type to be used for outgoing messages. For example, <code>application/edi-x12.</code>         </td>
      </tr>
      <tr>
         <td colspan="2"><i>Transfer Options</i>
         </td>
      </tr>
      <tr>
         <td>Timeout Transfer After <code>x</code> Minutes         </td>
         <td>The number of minutes after which a transfer is timed out if it is not successful.         </td>
      </tr>
      <tr>
         <td>Sign Using         </td>
         <td>The algorithm to be used to sign messages from this site.         </td>
      </tr>
      <tr>
         <td>Encrypt Using         </td>
         <td>
            <p>The algorithm used to encrypt messages from this site.</p>
            <p>The RC2/40, RC2/64 and RC2/128 algorithms are not FIPS compliant.</p>
         </td>
      </tr>
      <tr>
         <td>Compress         </td>
         <td>Select this check box to enable compression.         </td>
      </tr>
      <tr>
         <td>Enable Chunking         </td>
         <td>Select this check box to enable chunking.         </td>
      </tr>
      <tr>
         <td colspan="2"><i>Receipts</i>
         </td>
      </tr>
      <tr>
         <td>Request receipts for all Transfers         </td>
         <td>Select this check box to request receipts for all transfers.         </td>
      </tr>
      <tr>
         <td>Require Signed Receipt         </td>
         <td>If you select the <strong>Request receipts for all transfers</strong> check box, select the check box to require those receipts to be signed.         </td>
      </tr>
      <tr>
         <td> Request:<br/>Synchronous<br/>Asynchronous         </td>
         <td>
            <p>Specify whether you want receipts to be synchronous or asynchronous. If you select asynchronous receipts, specify whether you want to receive those receipts via HTTP or HTTPS.</p>
            <p>If you request receipts via asynchronous HTTP and you specify an SSL connection in <em>Receive Options</em>, you receive receipts via HTTPS instead of HTTP.</p>
         </td>
      </tr>
   </tbody>
</table>

## Transfer Settings: Receive Options

The following table describes the Receive Options for an AS2 transfer site.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>      </tr>
      <tr>
         <td colspan="2"><b>Receive Options</b>
         </td>
      </tr>
      <tr>
         <td>Receive File As         </td>
         <td>
            <p>Select the check box to specify a file name. You can use the expression language to specify the criteria you want to match. The expression uses the criteria provided to create a new file name from the original file name when the transfer is received. You can use the <span>SecureTransport</span>-specific variable <code>${stenv.rawsource}</code> which takes the value from the <code>original filename</code> in the AS2 message header. See <a href="../../../c_st_expressionlanguage">Expression Language</a> for information on <span>SecureTransport</span>-specific variables.</p>
         </td>
      </tr>
      <tr>
         <td>Require SSL Connection         </td>
         <td>
            <p>Select this check box to require an SSL connection for transfers received.</p>
            <p>If you request receipts via asynchronous HTTP and you specify an SSL connection, you receive receipts via HTTPS instead of HTTP.</p>
         </td>
      </tr>
      <tr>
         <td>Require Signature         </td>
         <td>Select this check box to require transfers received to be signed.         </td>
      </tr>
      <tr>
         <td>Require Encryption         </td>
         <td>Select this check box to require transfers received to be encrypted.         </td>
      </tr>
   </tbody>
</table>

## Advanced SSL Settings

The following table describes the Advanced SSL Settings for an AS2 transfer site.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2"><strong>Show Advanced SSL Settings</strong>
         </td>
      </tr>
      <tr>
         <td>Cipher suites         </td>
         <td>
            <p>The set of cipher suites available with the current AS2 transfer site for secure SIT connection. By default this set is populated with the cipher suites as defined in the <code>As2.SIT.Ciphers</code> configuration option.</p>
            <p>To reset to default values, click the button next to the tooltip.</p>
         </td>
      </tr>
      <tr>
         <td>Enabled SSL protocols         </td>
         <td>
            <p>The available SSL protocols for secure SIT connection with the current AS2 transfer site. By default this option uses the SSL protocols as defined in the <code>As2.SIT.EnabledProtocols</code> configuration option.</p>
            <p>To reset to default values, click the button next to the tooltip.</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Use a subscription to a Basic application or a Site Mailbox application to process files received by an AS2 transfer site.<br/>When using asynchronous receipts for outgoing AS2 transfers, post-transmission actions execute, even if the AS2 transfer has failed. This occurs because the transfer initially reports success, triggering the post-transmission action. After the post-transmission action is triggered, an asynchronous failure message is returned, causing the transfer to fail.         </td>
      </tr>
</table>

**Related topics:**

-   [Connect:Direct transfer sites](../r_st_connectdirecttransfersites)
-   [File services interface transfer sites](../r_st_fileservicesinterfaceprotocoltransfersites)
-   [Folder Monitor transfer sites](../r_st_foldermonitortransfersites)
-   [FTP(S) transfer sites](../transfersites-ftp)
-   [Generic HTTP transfer sites](../transfersites-generichttp)
-   [HTTP(S) transfer sites](../transfersites-http)
-   [PeSIT transfer sites](../transfersites-pesit)
-   [SSH transfer sites](../transfersites-ssh)
-   [System to Human transfer sites](../transfersites-s2h)
-   [Manage transfer sites](../t_st_transfersites)
