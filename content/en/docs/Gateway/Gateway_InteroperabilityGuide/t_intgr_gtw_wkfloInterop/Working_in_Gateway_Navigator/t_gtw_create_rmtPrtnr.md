{
    "title": "Creating a Remote Trading Partner",
    "linkTitle": "Creating a Remote Trading Partner",
    "weight": "100"
}[About the Gateway Remote Trading Partner object](#About) 

[Gateway GUI procedure](#Gateway_gui)

[Gateway command line procedure](#Gateway_commandline)

<span id="About"></span>

## About the Gateway Remote Trading Partner object

In the Remote Trading Partner object you specify information about the remote trading partner and the requested services for exchanges with that partner.

<span id="Gateway_gui"></span>

## Gateway GUI procedure

In the left pane of the Gateway Navigator main window, click to expand the **Partner Management** node.

Right-click the **Trading Partners** sub-node and from the context menu select **New**.

From the context menu, select the type of partner.

View available partner types

-   SMIME partner
-   AS1 partner
-   AS2 partner
-   AS3 partner
-   RosettaNet partner
-   SWIFTNet partner
-   OFTP partner (for OFTP R2.0 security services)

When you select a partner type, Gateway displays the *Trading Partner* properties window. The parameters displayed depend on the type of partner (protocol).

Complete the fields of the Trading Partner window.

View fields for S/MIME, AS1, AS2, AS3, RosettaNet and OFTP

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Identification criteria</strong></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Alias</strong></p>         </td>
         <td><p>Enter a name for the Trading Partner object to use for local identification operations. The name must be unique.</p>
<p>Gateway stores this alias as part of the data of each Transfer Request. You can use the alias as a substitute for the partner name parameter when depositing Transfer Requests.</p>         </td>
      </tr>
      <tr>
         <td><p>Format</p>         </td>
         <td><p>This field displays the protocol format that you selected when creating the new Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Local_Partner"></span>Local Partner</p>         </td>
         <td><p>Do not select this option.</p>         </td>
      </tr>
      <tr>
         <td><p>Name/Email</p>         </td>
         <td><p>For S/MIME or AS1, enter an email address.</p>
<p>For other protocols, enter a unique name for the Trading Partner object.</p>
<p>Maximum: 128 characters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Comments</strong></p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description of the Remote Trading Partner object.<br />
Maximum: 80 alphanumeric characters.<br />
This description is included in the displayed list of available Trading Partners.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate/Key</p>
<p>The fields displayed depend on the type of partner and the selected options.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="Use_dual_certificates"></span>Use dual certificates</p>         </td>
         <td><p>Click this button to toggle between the use of single or dual certificates. The effect of this button varies according to the context:</p>
<p>If you:</p>
<ul>
<li>select <strong>Use dual certificates</strong>:<br />
An encryption certificate is used to encrypt what is sent, and a signing certificate is used to check the signature of what is received.</li>
<li>do <span style="font-weight: bold;font-style: italic;">not</span> select <strong>Use dual certificates</strong>:<br />
A single certificate is used to encrypt what is sent, and to check the signature of what is received.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="Certificate_type"></span>Certificate:<br />
Type</p>         </td>
         <td><p>This field is visible when you do not select the Use dual certificates button.</p>
<p>Select a single certificate type to handle both outgoing and incoming messages:</p>
<ul>
<li>None</li>
<li>Secs alias<span style="font-weight: normal;">: local Axway Gateway PKI</span></li>
<li>PassPort PS entity<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
<li>PassPort PS certificate<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Certificate:<br />
Name</p>         </td>
         <td><p>This field is visible when you do <strong>not</strong> select the Use dual certificates button.</p>
<p>Enter the name of the certificate to be used to handle both outgoing and incoming messages.</p>         </td>
      </tr>
      <tr>
         <td><p>Certificate:<br />
Key password</p>         </td>
         <td><p>This field is visible when you do <strong>not</strong> select the Use dual certificates button.</p>
<p>Enter the password of the certificate key to be used to handle both outgoing and incoming messages.</p>
<p>This parameter is not available if you select <strong>SECS ALIAS</strong> as the <span style="font-style: italic;">Certificate Type.</span></p>         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
Type</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Select a certificate type for message signing:</p>
<ul>
<li><strong>None</strong></li>
<li><strong>Secs alias</strong>: local Axway Gateway PKI</li>
<li><strong>PassPort PS entity</strong>: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</li>
<li><strong>PassPort PS certificate:</strong> for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
Name</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Enter the name of the certificate to use for signing.</p>         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
Key password</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Enter the password for signing certificate key use.</p>
<p>This parameter is not available if you select <strong>SECS ALIAS</strong> as the <span style="font-style: italic;">Signing Certificate Type</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Type</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Select a certificate type for message encryption or decryption:</p>
<ul>
<li>None</li>
<li>Secs alias<span style="font-weight: normal;">: local Axway Gateway PKI</span></li>
<li>PassPort PS entity<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
<li>PassPort PS certificate:<span style="font-weight: normal;"> for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Name</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Enter the name of the certificate to use for the encryption of sent messages.</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Key password</p>         </td>
         <td><p>This field is visible when you select the Use dual certificates button.</p>
<p>Enter the password for the use of the certificate to be used for the encryption of sent messages.</p>
<p>This parameter is not available if you select <strong>SECS ALIAS</strong> as the <span style="font-style: italic;">Encryption Certificate Type</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption algo</p>         </td>
         <td><p>This field is visible when you select any option other than <strong>none</strong> from the <strong>Encryption certificate: Type field</strong>.</p>
<p>Select the algorithm to use for message and/or acknowledgement encryption:</p>
<ul>
<li>AES128<span style="font-weight: normal;"> (default)</span></li>
<li>AES256</li>
<li>DES</li>
<li>3DES</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Key encryption algo</p>         </td>
         <td><p>This field is visible when you select any option other than <strong>none</strong> from the <strong>Encryption certificate: Type field</strong>.</p>
<p>The only available value for this field is:</p>
<ul>
<li>RSA<span style="font-weight: normal;"> (default)</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Use Multiple Certificates</p>         </td>
         <td><p>Only if you are using PassPort PS</p>
<p>Select this option to use multiple certificates.</p>
<p>Refer to the Axway PassPort documentation for details.</p>         </td>
      </tr>
      <tr>
         <td><p>Default parameters for file sending</p>
<p>These fields are active only when you are creating or modifying a <strong>remote</strong> Trading Partner object (Local Partner checkbox unselected)</p>         </td>
      </tr>
      <tr>
         <td><p>Associated originator Partner</p>         </td>
         <td><p>Either:</p>
<ul>
<li>Enter the originator partner to use when sending a file, or</li>
<li>Select a partner from the drop-down list</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Default outgoing Site</p>         </td>
         <td><p>Either:</p>
<ul>
<li>Enter a default outgoing Site name, or</li>
<li>Select a Site name from the drop-down list</li>
</ul>
<p>The Site must be an existing Site on your local Axway Gateway.</p>
<p>When you send a file to a remote exchange partner, the remote partner uses this value to process the sent message.</p>         </td>
      </tr>
      <tr>
         <td><p>Remote directory (url complement)</p>         </td>
         <td><p>Not available for all types of partner</p>
<p>Specify:</p>
<ul>
<li>For AS2, the URL path of the directory where the remote exchange partner stores received data</li>
<li>For AS3, the directory where the remote partner stores received data</li>
</ul>
<p>Your remote destination exchange partner must provide you with this information.</p>
<p>This parameter is only significant when the remote exchange partner is operating as a server.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
<span id="Encrypt_file"></span>Encrypt file</p>         </td>
         <td><p>Select this option to activate encryption.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
<span id="Sign_file"></span>Sign file</p>         </td>
         <td><p>Select this option to activate message signing.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Compress file</p>         </td>
         <td><p>Select this option to activate message compression.</p>
<p>If you select this option, select a compression algorithm in the <strong>Compression algo</strong> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Compression algo</p>         </td>
         <td><p>If you select the <strong>Compress file</strong> option, select a compression algorithm from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Requested services:<br />
Request receipt</strong></p>         </td>
         <td><p>Specify whether or not you want to receive a receipt on reception of a file you send.</p>
<p>If you choose to receive a receipt, specify whether the receipt is signed or unsigned.</p>
<p>Enter one of the following values:</p>
<ul>
<li><strong>None</strong> = no receipt requested (default)</li>
<li><strong>Signed</strong> = request signed receipt</li>
<li><strong>Unsigned</strong> = request unsigned receipt</li>
</ul>
<p>If you select either the <strong>Signed</strong> or <strong>Unsigned</strong> values for this option, enter a receipt reception address in the <strong>Receipt url/email</strong> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Synchronize receipt</p>         </td>
         <td><p>Only for AS2.</p>
<p>Specify whether or not you want to synchronize receipt delivery:</p>
<ul>
<li><strong>selected:</strong> your remote partner returns a reception acknowledgement immediately on file reception and unpacking</li>
<li><strong>not selected:</strong> your remote partner returns a reception acknowledgement in a protocol session independent of the original transfer session</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Requested services:<br />
Receipt url/email</strong></p>         </td>
         <td><p>Not available for the S/MIME protocol.</p>
<p>If you choose to receive receipts of sent messages, specify the address to which the receiving partner sends the receipt.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters for file reception</p>
<p>These fields are active only when you are creating or modifying a <strong>remote</strong> Trading Partner object (Local Partner checkbox unselected)</p>         </td>
      </tr>
      <tr>
         <td><p>Force signed</p>         </td>
         <td><p>Select this option to specify that you want Gateway to require message signing on reception.</p>
<p>If you request signing by selecting the Sign file option above, you should also activate this function.</p>         </td>
      </tr>
      <tr>
         <td><p>Force encrypted</p>         </td>
         <td><p>Select this option to specify that you want Gateway to require message encryption as criteria for reception.</p>
<p>If you request encryption by selecting the Encrypt file option above, you should also activate this function.</p>         </td>
      </tr>
      <tr>
         <td><p>Force receipt requested</p>         </td>
         <td><p>Specify whether or not you want Gateway to require receipt requests on reception.</p>
<p>Select one of the following values:</p>
<ul>
<li><strong>Undefined</strong> = Do not require a receipt request (default)</li>
<li><strong>None</strong> = Ensure that no receipt is requested. Gateway rejects messages with receipt requests</li>
<li><strong>Signed</strong> = Ensure that a signed receipt is requested. Gateway only accepts messages with requests for signed receipts</li>
<li><strong>Unsigned</strong> = Ensure that a unsigned receipt is requested. Gateway only accepts messages with requests for unsigned receipts</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Force receipt url/email</p>         </td>
         <td><p>If you enter an address as a value for this parameter, Gateway checks to confirm that the receipt return path specified in the incoming message is the same. If the check fails, Gateway rejects the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced parameters...:<br />
Local file location for encoding/decoding</p>
<p>Click the <strong>Advanced...</strong> button to display the following two fields.</p>
<p>These fields enable you to specify the directory and name format of the file where transfers are processed for encoding (outgoing files) and decoding (incoming files).</p>
<p>You may want to specify a secure directory for this file, keeping in mind that the files that are decoded in this directory can be read by malicious intruders.</p>
<p>If you do not specify a directory, Gateway creates the files in<span style="font-family: monospace;"> &lt;Gateway install directory&gt;\runtime\tmp</span></p>         </td>
      </tr>
      <tr>
         <td><p>Directory path</p>         </td>
         <td><p>Enter the local physical path of the directory where transferred files are encoded and decoded.</p>         </td>
      </tr>
      <tr>
         <td><p>File name pattern</p>         </td>
         <td><p>Enter a specific file name format to enable you to identify the transferred file in the specified out directory.</p>         </td>
      </tr>
   </tbody>
</table>

Click **OK**.  
Gateway creates a new Remote Trading Partner object with the specified characteristics.

<span id="Gateway_commandline"></span>

## Gateway command line procedure

To create a Remote Trading Partner object via the command line, use the `peladm create_tradepart` command.

For details of command line use, refer to the Axway Gateway online documentation.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
