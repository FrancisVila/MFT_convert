{
    "title": "Working with Trading Partner objects",
    "linkTitle": "Working with Trading Partner objects",
    "weight": "190"
}{{< Gateway/componentlongname  >}}: Managing Partners

[Creating a Trading Partner object](#Creating_a_Trading_Partner)

[Displaying a list of all Trading Partner objects](#Displaying_a_Trading_Partner)

[Displaying a list of selected Trading Partner objects](#Selecting_a_Trading_Partner)

[Viewing the attributes of a Trading Partner object](#Viewing_the_attributes_of_a_Trading_Partner)

[Modifying a Trading Partner object](#Updating_a_Trading_Partner)

[Deleting a Trading Partner object](#Deleting_A_Trading_Partner)

<span id="Creating_a_Trading_Partner"></span>

## Creating a Trading Partner object

To create a new Trading Partner object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the **Partner Management** node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays a context menu.
3.  Select <span style="font-weight: bold;">New</span>  
    Gateway displays a context menu.
4.  Select the type of partner:

-   **SMIME partner**
-   **AS1 partner**
-   **AS2 partner**
-   **AS3 partner**
-   **RosettaNet partner**
-   **SWIFTNet partner**
-   **OFTP partner** (for OFTP R2.0 security services)

Gateway displays the <span style="font-style: italic;">Trading Partner</span> window. The parameters displayed depend on the <span style="font-style: italic;">type of partner</span> (protocol).  
If you are using:

-   SWIFTNet, go to [Configuring the Gateway/SWIFTNet environment](../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring#Creating_objects_for_SWIFTNet_transfers)
-   S/MIME, AS1, AS2, AS3, RosettaNet or OFTP, continue with the next step

Use the information in the following table to complete the fields of the <span style="font-style: italic;">Trading Partner</span> window.

#### Trading Partner – S/MIME, AS1, AS2, AS3, RosettaNet or OFTP

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadE-Column1-Header1"><p>Definition</p>         </th>
<th class="HeadD-Column1-Header1"><p>Partner type...</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Identification criteria</p>         </td>
      </tr>
      <tr>
         <td><p>Alias</p>         </td>
         <td><p>Enter a name for the Trading Partner object to use for local identification operations. The name must be unique.</p>
<p>Gateway stores this alias as part of the data of each Transfer Request. You can use the alias as a substitute for the partner name parameter when depositing Transfer Requests.</p>         </td>
         <td><p>Local and Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Format</p>         </td>
         <td><p>This field displays the protocol format that you selected when creating the new Trading Partner:</p>
<ul>
<li>SMIME</li>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>RosettaNet</li>
<li>SWIFTNet</li>
<li><span style="font-weight: bold;">CMS</span> (Cryptographic Message Syntax) for OFTP R2.0 security services</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="Local_Partner"></span>Local Partner</p>         </td>
         <td><p>Click if required:</p>
<ul>
<li><span style="font-weight: bold;">selected</span> = <span style="font-weight: bold;font-style: italic;">local</span> Trading Partner object</li>
<li><span style="font-weight: bold;">not selected</span> = <span style="font-weight: bold;font-style: italic;">remote</span> Trading Partner object (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Name/Email</p>         </td>
         <td><p>For S/MIME or AS1, enter an email address.</p>
<p>For other protocols, enter a unique name for the Trading Partner object.</p>
<p>Maximum: 128 characters. When searching the partner in Gateway, the first part of the email (before the @) is case sensitive, while the domain (after the @) is case insensitive .</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Optional</p>
<p>Enter a free-text description of the Trading Partner object.<br />
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
If you are creating a <span style="font-weight: bold;font-style: italic;">local</span> partner and you...
<ul>
<li>select <span style="font-weight: bold;">Use dual certificates</span>:<br />
A signing certificate is used to sign what is sent, and an encryption certificate is used to decrypt what is received.</li>
<li>do <span style="font-weight: bold;font-style: italic;">not</span> select <span style="font-weight: bold;">Use dual certificates</span>:<br />
A single certificate is used to sign what is sent, and is used to decrypt what is received.</li>
</ul>
If you are creating a <span style="font-weight: bold;font-style: italic;">remote</span> partner and you...
<ul>
<li>select <span style="font-weight: bold;">Use dual certificates</span>:<br />
An encryption certificate is used to encrypt what is sent, and a signing certificate is used to check the signature of what is received.</li>
<li>do <span style="font-weight: bold;font-style: italic;">not</span> select <span style="font-weight: bold;">Use dual certificates</span>:<br />
A single certificate is used to encrypt what is sent, and to check the signature of what is received.</li>
</ul>         </td>
         <td><p>Local and Remote</p>         </td>
      </tr>
      <tr>
         <td>The following <strong>three</strong> lines are visible when you <strong>do not select</strong> the <a href="#Use_dual_certificates">Use dual certificates</a> button.         </td>
      </tr>
      <tr>
         <td><span id="Certificate_type"></span><span style="font-weight: normal;">Certificate:</span><br />
<strong>Type</strong>         </td>
         <td><p>Select a single certificate type to handle both outgoing and incoming messages:</p>
<ul>
<li>None</li>
<li>Secs alias<span style="font-weight: normal;">: local Gateway PKI</span></li>
<li>PassPort PS entity<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
<li>PassPort PS certificate<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
</ul>         </td>
         <td><p>Local and Remote</p>         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal;">Certificate: </span><br />
<strong>Name</strong>         </td>
         <td><p>Enter the name of the certificate to be used to handle both outgoing and incoming messages.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><span style="font-weight: normal;">Certificate: </span><br />
<span style="font-weight: bold;">Set key password</span>         </td>
         <td><p>Opens a dialog box to enter the password of the certificate key, to be used to handle both outgoing and incoming messages.</p>
<p>This parameter is not available if you select <span style="font-weight: bold;">SECS ALIAS</span> as the <span style="font-style: italic;">Certificate Type.</span></p>
<p>When the certificate type is PassPort PS Entity, you need to enter the entity's password in this field.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td>The following <strong>six</strong> lines are visible when you <strong>do select</strong> the <a href="#Use_dual_certificates">Use dual certificates</a> button.         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
<strong>Type</strong></p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Select a certificate type for message signing:</p>
<ul>
<li><span style="font-weight: bold;">None</span></li>
<li><span style="font-weight: bold;">Secs alias</span>: local Gateway PKI</li>
<li><span style="font-weight: bold;">PassPort PS entity</span>: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</li>
<li><span style="font-weight: bold;">PassPort PS certificate:</span> for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
<strong>Name</strong></p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Enter the name of the certificate to use for signing.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Signing certificate:<br />
<strong>Set Entity password</strong></p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Enter the password for signing certificate key use.</p>
<p>This parameter is not available if you select <span style="font-weight: bold;">SECS ALIAS</span> as the <span style="font-style: italic;">Signing Certificate Type</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Type</p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Select a certificate type for message encryption or decryption:</p>
<ul>
<li>None</li>
<li>Secs alias<span style="font-weight: normal;">: local Gateway PKI</span></li>
<li>PassPort PS entity<span style="font-weight: normal;">: for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
<li>PassPort PS certificate:<span style="font-weight: normal;"> for use with the PassPort PS server. Refer to the Axway PassPort documentation for details.</span></li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Name</p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Enter the name of the certificate to use for the encryption of sent messages.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Encryption certificate:<br />
Key password</p>         </td>
         <td><p>This field is visible when you select the <a href="#Use_dual_certificates">Use dual certificates</a> button.</p>
<p>Enter the password for the use of the certificate to be used for the encryption of sent messages.</p>
<p>This parameter is not available if you select <span style="font-weight: bold;">SECS ALIAS</span> as the <span style="font-style: italic;">Encryption Certificate Type</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Encryption algo</p>         </td>
         <td><p>This field is visible when you select any option other than <span style="font-weight: bold;">none</span> from the <span style="font-weight: bold;">Encryption certificate: Type field</span>.</p>
<p>Select the algorithm to use for message and/or acknowledgment encryption:</p>
<ul>
<li><strong>AES128</strong> (default)</li>
<li><strong>AES256</strong> </li>
<li><strong>DES</strong></li>
<li><strong>3DES</strong></li>
<li><strong>RC2_40</strong> <em>(for AS2 and RosettaNet only)</em> </li>
<li><strong>RC4</strong> <em>(for AS2 and RosettaNet only)</em> </li>
</ul>
<p><strong>Note:</strong> Gateway supports RC4 with 128-bit key size. Gateway does not support RC4 with 40-bit or 64-bit key sizes.</p>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Key encryption algo</p>         </td>
         <td><p>This field is visible when you select any option other than <span style="font-weight: bold;">none</span> from the <span style="font-weight: bold;">Encryption certificate: Type field</span>.</p>
<p>The only available value for this field is:</p>
<ul>
<li><strong>RSA</strong> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Signing algo</p>         </td>
         <td><p>For creating or modifying Local Partners only.</p>
<p>This field is visible when you select any option other than <span style="font-weight: bold;">none</span> from the <a href="#Certificate_type">Certificate: Type</a> field.</p>
<p>Select the algorithm to use for signing:</p>
<ul>
<li>SHA1 with RSA <span style="font-weight: normal;">(default)</span></li>
<li>MD5 with RSA</li>
<li><strong>SHA512 with RSA</strong></li>
<li><strong>SHA256 with RSA</strong></li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>Restrictions apply to this list in FIPS mode.
See the Security Guide for further information.</p>
</blockquote>
<blockquote>
<p><strong>Note:</strong></p>
<p>The MD5 with RSA signing algorithm is not available unless the configuration option [monitor]enable_md5_hash_algo is set to yes (not recommended).</p>
</blockquote>         </td>
         <td><p>Local</p>         </td>
      </tr>
      <tr>
         <td><p>Use Multiple Certificates</p>         </td>
         <td><p>Only if you are using PassPort PS</p>
<p>Select this option to use multiple certificates.</p>
<p>Refer to the Axway PassPort documentation for details.</p>         </td>
         <td><p>Local and Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Default parameters for file sending</p>
<p>These fields are active only when you are creating or modifying a <span style="font-weight: bold;">remote</span> Trading Partner object (<a href="#Local_Partner">Local Partner</a> checkbox unselected)</p>         </td>
      </tr>
      <tr>
         <td><p>Associated originator Partner</p>         </td>
         <td><p>Either:</p>
<ul>
<li>Enter the originator partner to use when sending a file, or</li>
<li>Select a partner from the drop-down list</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Default outgoing Site</p>         </td>
         <td><p>Either:</p>
<ul>
<li>Enter a default outgoing Site name, or</li>
<li>Select a Site name from the drop-down list</li>
</ul>
<p>The Site must be an existing Site on your local Gateway.</p>
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
<p>If you select this option, select a compression algorithm in the <span style="font-weight: bold;">Compression algo</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Compression algo</p>         </td>
         <td><p>If you select the <span style="font-weight: bold;">Compress file</span> option, select a compression algorithm from the drop-down list.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Request receipt</p>         </td>
         <td><p>Specify whether or not you want to receive a receipt on reception of a file you send.</p>
<p>If you choose to receive a receipt, specify whether the receipt is signed or unsigned.</p>
<p>Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">None</span> = no receipt requested (default)</li>
<li><span style="font-weight: bold;">Signed</span> = request signed receipt</li>
<li><span style="font-weight: bold;">Unsigned</span> = request unsigned receipt</li>
</ul>
<p>If you select either the <span style="font-weight: bold;">Signed</span> or <span style="font-weight: bold;">Unsigned</span> values for this option, enter a receipt reception address in the <span style="font-weight: bold;">Receipt url/email</span> field.</p>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Synchronize receipt</p>         </td>
         <td><p>Only for AS2.</p>
<p>Specify whether or not you want to synchronize receipt delivery:</p>
<ul>
<li><span style="font-weight: bold;">selected:</span> your remote partner returns a reception acknowledgment immediately on file reception and unpacking</li>
<li><span style="font-weight: bold;">not selected:</span> your remote partner returns a reception acknowledgment in a protocol session independent of the original transfer session</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Requested services:<br />
Receipt url/email</p>         </td>
         <td><p>Not available for the S/MIME protocol.</p>
<p>If you choose to receive receipts of sent messages, specify the address to which the receiving partner sends the receipt.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters for file reception</p>
<p>These fields are active only when you are creating or modifying a <span style="font-weight: bold;">remote</span> Trading Partner object (<a href="#Local_Partner">Local Partner</a> checkbox unselected)</p>         </td>
      </tr>
      <tr>
         <td><p>Force signed</p>         </td>
         <td><p>Select this option to specify that you want Gateway to require message signing on reception.</p>
<p>If you request signing by selecting the <a href="#Sign_file">Sign file</a> option above, you should also activate this function.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Force encrypted</p>         </td>
         <td><p>Select this option to specify that you want Gateway to require message encryption as criteria for reception.</p>
<p>If you request encryption by selecting the <a href="#Encrypt_file">Encrypt file</a> option above, you should also activate this function.</p>         </td>
      </tr>
      <tr>
         <td><p>Force receipt requested</p>         </td>
         <td><p>Specify whether or not you want Gateway to require receipt requests on reception.</p>
<p>Select one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">Undefined</span> = Do not require a receipt request (default)</li>
<li><span style="font-weight: bold;">None</span> = Ensure that no receipt is requested. Gateway rejects messages with receipt requests</li>
<li><span style="font-weight: bold;">Signed</span> = Ensure that a signed receipt is requested. Gateway only accepts messages with requests for signed receipts</li>
<li><span style="font-weight: bold;">Unsigned</span> = Ensure that a unsigned receipt is requested. Gateway only accepts messages with requests for unsigned receipts</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Force receipt url/email</p>         </td>
         <td><p>If you enter an address as a value for this parameter, Gateway checks to confirm that the receipt return path specified in the incoming message is the same. If the check fails, Gateway rejects the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced parameters...:<br />
Local file location for encoding/decoding</p>
<p>Click the <span style="font-weight: bold;">Advanced...</span> button to display the following two fields.</p>
<p>These fields enable you to specify the directory and name format of the file where transfers are processed for encoding (outgoing files) and decoding (incoming files).</p>
<p>You may want to specify a secure directory for this file, keeping in mind that the files that are decoded in this directory can be read by malicious intruders.</p>
<p>If you do not specify a directory, Gateway creates the files in<span class="code"> &lt;Gateway installation directory&gt;\runtime\tmp</span></p>         </td>
      </tr>
      <tr>
         <td><p>Directory path</p>         </td>
         <td><p>Enter the local physical path of the directory where transferred files are encoded and decoded.</p>         </td>
         <td><p>Local and Remote</p>         </td>
      </tr>
      <tr>
         <td><p>File name pattern</p>         </td>
         <td><p>Enter a specific file name format to enable you to identify the transferred file in the specified out directory.</p>         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span> If you are using RosettaNet, also refer to [Configuring the RosettaNet environment](../../../protocols_about/rosettanet_about/rosettanet_config#Creating_objects_for_RosettaNet_transfers).

<span id="Displaying_a_Trading_Partner"></span>

## Displaying a list of Trading Partner objects

To display a list of all Trading Partner objects stored in the database:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays a list of all existing Trading Partner objects in the right (display) pane.

<span id="Selecting_a_Trading_Partner"></span>

## Displaying a list of Selected Trading Partner objects

To generate a list of selected Trading Partner objects:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays a context menu.
3.  Choose <span style="font-weight: bold;">Select...</span> from the context menu.  
    Gateway displays the<span style="font-style: italic;"> Select Trading Partner</span> window.
4.  In the <span style="font-style: italic;">Select Trading Partner</span> window, use the data fields to enter criteria for Trading Partner display selection. You can use one or more of the following selection criteria:

-   Name
-   Format
-   Local or Remote partner

Click <span style="font-weight: bold;">OK</span> to accept the display selection criteria.  
Gateway regenerates the Trading Partner List display in the right window, taking into account your selection criteria.

<span id="Viewing_the_attributes_of_a_Trading_Partner"></span>

## Viewing the attributes of a Trading Partner

To view the attributes of an existing Trading Partner via the GUI:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays all existing Trading Partners in the right (display) pane.
3.  In the right pane, right-click to select the Trading Partner that you want to modify.  
    Gateway displays a context menu.
4.  Select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">Trading Partner (Read only)</span> window. This window provides you with a view of all attributes for the selected Trading Partner.
5.  When you have finished viewing the information, click <span style="font-weight: bold;">Close</span> to quit the window.

<span id="Updating_a_Trading_Partner"></span>

## Modifying a Trading Partner object

To modify and update a Trading Partner object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Right-click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays all existing Trading Partners in the right (display) pane.
3.  Click the name of the Trading Partner to update. Right-click and select <span style="font-weight: bold;">Modify...</span> from the context menu.  
    Gateway displays the <span style="font-style: italic;">Trading Partner</span> window. For window details refer to [Creating a Trading Partner](#Creating_a_Trading_Partner).
4.  Make your changes and click <span style="font-weight: bold;">OK</span> to confirm.

<span class="bold_in_para">Note</span>: There are two types of Trading Partners, Local and Remote which are two distinct objects and must be treated as such. If the Remote Partner is active when modifying the Trading Partner and switching to Local Partner occurs, this may result in abnormal behavior of the product.

<span id="Deleting_A_Trading_Partner"></span>

## Deleting a Trading Partner object

To delete a Trading Partner object:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Partner Management</span> node.
2.  Click the <span style="font-weight: bold;">Trading Partners</span> sub-node.  
    Gateway displays all existing Trading Partners in the right (display) pane.
3.  Click the name of the Trading Partner that you want to delete. Right-click and select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.
4.  In the confirmation dialog box, click <span style="font-weight: bold;">Yes</span> to confirm the delete operation.  
    Alternatively, click <span style="font-weight: bold;">No</span> or <span style="font-weight: bold;">Cancel</span> to abandon the operation.  
    Gateway deletes the Trading Partner object from the database and removes the entry from the display window.

Related topics

[Working with Trading Partners (command line)](../working_with_trading_partners_cli)

[Overview: Trading Partners](../../../ov_gateway/ov_trading_partners)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
