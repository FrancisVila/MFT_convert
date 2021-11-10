{
    "title": "Working with Trading Partner objects (command line)",
    "linkTitle": "Command line operations",
    "weight": "200"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Partners

<span class="code" style="font-weight: bold;">[peladm\_create\_tradepart](#peladm_create_tradepart)</span>

<span class="code" style="font-weight: bold;">[peldsp\_display\_tradepart](#peldsp_display_tradepart)</span>

<span class="code" style="font-weight: bold;">[peldsp\_select\_tradepart](#peldsp_select_tradepart)</span>

<span class="code" style="font-weight: bold;">[peladm\_update\_tradepart](#peladm_update_tradepart)</span>

<span class="code" style="font-weight: bold;">[peladm\_delete\_tradepart](#peladm_delete_tradepart)</span>

<span style="font-weight: bold;">Note:</span> If you are using SWIFTNet, refer to [Configuring the Gateway/SWIFTNet environment](../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring) for specific parameters.

<span id="peladm_create_tradepart"></span>

## Creating a Trading Partner: peladm create\_tradepart

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm create_tradepart</span> [see parameters below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new Trading Partner object.</p>
<p>You can specify one of two types of Trading Partner:</p>
<ul>
<li>Local</li>
<li>Remote</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Parameter name (and abbreviation)</p>         </td>
         <td><p><span style="font-weight: bold;">Description</span></p>         </td>
         <td><p>For local or remote</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-name (-n)</span></p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>For S/MIME or AS1, enter an email address.</p>
<p>For other protocols, enter a unique name for the Trading Partner object.</p>
<p>The remote business exchange partner uses this name to identify the local partner.</p>
<p>Maximum: 128 characters.</p>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-format (-f)</span></p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter one of the following protocol formats for exchanges with the remote partner:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>RN</li>
<li>CMS<span style="font-weight: normal;"> (for OFTP)</span></li>
<li>SWIFTNET</li>
</ul>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span></p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter a name for the Trading Partner object to use for local identification operations. The name must be unique.</p>
<p>Gateway stores this alias as part of the data of each Transfer Request. You can use the alias as a substitute for the partner <span class="code">name</span> parameter when depositing Transfer Requests.</p>
<p>By default, the alias is the <span class="code">name (-n)</span> value set to uppercase and truncated to 31 characters.</p>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p>-certificate_name (-ctfn)</p>         </td>
         <td><p>Enter the SECS certificate name to use for the partner.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-comments (-cts)</p>         </td>
         <td><p>Optionally, enter a free-text description of the Trading Partner object.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p>-compress (-c)</p>         </td>
         <td><p>Specify whether or not you want to apply compression to the data contained in sent messages:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = compress sent messages</li>
<li><span style="font-weight: bold;">N</span> = (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-compress_algo (-ca)</p>         </td>
         <td><p><span style="font-weight: normal;">Enter the algorithm to use for message and/or receipt compression.</span></p>
<p>You can only enter the following value:</p>
<ul>
<li>ZLIB</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_name (-dn)</p>         </td>
         <td><p>Enter:</p>
<ul>
<li>For AS2, the URL path of the directory where the remote exchange partner stores received data</li>
<li>For AS3, the directory where the remote partner stores received data</li>
</ul>
<p>Your remote destination exchange partner must provide you with this information.</p>
<p>This parameter is only significant when the remote exchange partner is operating as a server.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-dir_path (-dp)</p>         </td>
         <td><p>Enter the local physical path of the file where transferred files are encoded and decoded.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-encrypt (-e)</p>         </td>
         <td><p>Specify whether or not you want to encrypt the data contained in sent messages:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Encrypt sent messages</li>
<li><span style="font-weight: bold;">N</span> = Do not encrypt (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-encryption_algo (-ea)</span></p>         </td>
         <td><p>Enter the algorithm to use for message and/or receipt encryption. One of:</p>
<ul>
<li><strong>AES128</strong> (default)</li>
<li><strong>AES256</strong></li>
<li><strong>DES</strong></li>
<li><strong>3DES</strong></li>
<li><strong>RC2_40</strong> <em>(for AS2 and RosettaNet only)</em> </li>
<li><strong>RC4</strong> <em>(for AS2 and RosettaNet only)</em> </li>
</ul>
<p><strong>Note:</strong> Gateway supports RC4 with 128-bit key size. Gateway does not support RC4 with 40-bit or 64-bit key sizes.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-encryption_obj_name (-eon)</p>         </td>
         <td><p>Enter the name of the encryption certificate.</p>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p>-encryption_obj_password (-eop)</p>         </td>
         <td><p>Enter the password to use with the encryption certificate.</p>
<p>Do not use this parameter if you enter SECS_ALIAS for <span class="code">encryption_obj_type</span>.</p>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p>-encryption_obj_type (-eot)</p>         </td>
         <td><p>Enter the type of encryption certificate to use for encrypting sent messages. One of:</p>
<ul>
<li>NONE</li>
<li><span style="font-weight: bold;">SECS_ALIAS</span>: local Gateway PKI</li>
<li>XPP_ENTITY<span style="font-weight: normal;">: for use with the PassPort PS server.<br />
Refer to the Axway PassPort documentation for details.</span></li>
<li><span style="font-weight: bold;">XPP_CERTIFICATE</span>: for use with the PassPort PS server.<br />
Refer to the Axway PassPort documentation for details.</li>
</ul>         </td>
         <td><p>Local and remote</p>         </td>
      </tr>
      <tr>
         <td><p>-file_component (-fc)</p>         </td>
         <td><p>Enter the name of the file where the exchange partner stores received data.</p>
<p>Your remote destination exchange partner must provide you with this information.</p>
<p>This parameter is only significant when the remote exchange partner is operating as a server.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-force_encrypted (-fe)</p>         </td>
         <td><p>Specify whether or not you want Gateway to require message encryption as a criteria for reception:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Ensure received message is encrypted. Gateway rejects unencrypted messages.</li>
<li><span style="font-weight: bold;">N</span> = (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-force_receipt_request (-frr)</p>         </td>
         <td><p>Specify whether or not you want Gateway to require receipt requests on reception. Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">Undef</span> = Do not require a receipt request (default)</li>
<li>None<span style="font-weight: normal;"> = Ensure that no receipt is requested. Gateway rejects messages with receipt requests</span></li>
<li><span style="font-weight: bold;">Signed</span> = Ensure that a signed receipt is requested. Gateway only accepts messages with requests for signed receipts.</li>
<li>Unsigned<span style="font-weight: normal;"> = Ensure that a unsigned receipt is requested. Gateway only accepts messages with requests for unsigned receipts.</span></li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-force_receipt_request_to (-frrto)</p>         </td>
         <td><p>If you enter an address as a value for this parameter, Gateway checks to confirm that the receipt return path specified in the incoming message is the same. If the check fails, Gateway rejects the message.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-force_signed (-fs)</p>         </td>
         <td><p>Specify whether or not you want Gateway to require for message signing on reception:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Check if received messages are signed. Gateway rejects unsigned messages</li>
<li><span style="font-weight: bold;">N</span> = No signing required. Gateway accepts all incoming messages (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-is_local (-loc)</p>         </td>
         <td><p>Specify if the Trading Partner object you are creating is for a local or a remote partner:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = local Trading Partner object</li>
<li><span style="font-weight: bold;">N</span> = remote Trading Partner object (default)</li>
</ul>         </td>
         <td><p>Local</p>         </td>
      </tr>
      <tr>
         <td><p>-key_encryption_algo (-kea)</p>         </td>
         <td><p>Enter the algorithm to use for key encryption.</p>
<p>You can enter only the following value:</p>
<ul>
<li><span style="font-weight: bold;">RSA</span> (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request (-rr)</p>         </td>
         <td><p>Specify whether or not you want to receive a receipt for the reception of a file you send. If you choose to receive a receipt, specify whether the receipt is signed or unsigned.</p>
<p>Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">None</span> = no receipt requested (default)</li>
<li><span style="font-weight: bold;">Signed</span> = request signed receipt</li>
<li><span style="font-weight: bold;">Unsigned</span> = request unsigned receipt</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request_synchronized (-rrs)</p>         </td>
         <td><p>Specify whether or not you want to synchronize receipt delivery so that the receipt is generated and delivered in the same protocol session as the original transfer:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = Yes, synchronize</li>
<li><span style="font-weight: bold;">N</span> = No, do not synchronize (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-receipt_request_to (-rrto)</p>         </td>
         <td><p>If you choose to receive receipts of sent messages, specify the address to which the receiving partner sends the receipt.</p>
<p>For:</p>
<ul>
<li>AS1 - The default return address is the email address you entered as the <span class="code">name (-n)</span> value. You can specify an alternative email address in this parameter</li>
<li>AS2 asynchronous mode - Enter a return URL or email address</li>
<li>AS3 - Enter a return URL or email address</li>
<li>SWIFTNet (<span style="font-style: italic;">FileAct, Real time only</span>) - Refer to <a href="../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring#olh_remote_trading_partner_swiftnet">Configuring the Gateway/SWIFTNet environment</a></li>
</ul>
<p>For other protocols, Gateway does not use this parameter.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-remote_site (-rs)</p>         </td>
         <td><p>Default outgoing Site name. The Site must be an existing Site on your local Gateway.</p>
<p>When you send a file to a remote exchange partner, the remote partner uses this value to process the sent message.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-sign (-s)</p>         </td>
         <td><p>Specify whether or not you want signing of the data contained in sent messages:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = sign sent messages</li>
<li><span style="font-weight: bold;">N</span> = (default)</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-sign_obj_name (-son)</p>         </td>
         <td><p>Enter the name of the signing certificate.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-sign_obj_password (-sop)</p>         </td>
         <td><p>Enter the password to use with the signing certificate.</p>
<p>Do not use this parameter if you enter SECS_ALIAS for <span class="code">sign_obj_type</span>.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-sign_obj_type (-sot)</p>         </td>
         <td><p>Enter the type of signing certificate to use on sent messages. One of:</p>
<ul>
<li>NONE</li>
<li>SECS_ALIAS<span style="font-weight: normal;">: local Gateway PKI</span></li>
<li>XPP_ENTITY<span style="font-weight: normal;">: for use with the PassPort PS server.<br />
Refer to the Axway PassPort documentation for details.</span></li>
<li><span style="font-weight: bold;">XPP_CERTIFICATE</span>: for use with the PassPort PS server.<br />
Refer to the Axway PassPort documentation for details.</li>
</ul>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>-signing_algo (-sa)</p>         </td>
         <td><p>Enter the algorithm to use for message and/or receipt signing. One of:</p>
<ul>
<li>SHA1withRSA <span style="font-weight: normal;">(default)</span></li>
<li>MD5withRSA</li>
<li><p><strong>SHA256withRSA</strong>*<strong></strong></p></li>
<li><p><strong>SHA512withRSA</strong>*<strong></strong></p></li>
</ul>
<p>* Available only for AS1, AS2 and AS3.</p>         </td>
         <td><p>Local</p>         </td>
      </tr>
      <tr>
         <td><p>-tradepart_org_name (-org)</p>         </td>
         <td><p>When you send a file to a remote exchange partner, the remote partner uses this value to process the sent message.</p>         </td>
         <td><p>Remote</p>         </td>
      </tr>
      <tr>
         <td><p>Example 1: creating a remote partner for AS2</p>         </td>
         <td><p>The following command creates a remote Trading Partner object with the characteristics:</p>
<ul>
<li>name = PartnerRemote1</li>
<li>format = AS2</li>
<li>alias = AS2PR1</li>
<li>default remote target = CYCL_XIP1REC_AS2</li>
<li>signing = yes</li>
<li>encryption = yes</li>
<li>receipt = yes</li>
<li>receipt URL =<br />
http://hpx15:8382/user1/transfer?user=user1&amp;password=user1</li>
<li>signed receipt forced</li>
<li>compression = yes</li>
<li>compression algo = ZLIB</li>
<li>signing algo = MD5withRSA</li>
<li>encryption algo = 3DES</li>
<li>encryption certificate type = XPP_CERTIFICATE</li>
<li>encryption certificate name = XPPUSER1</li>
<li>encryption certificate password = xppuser1</li>
<li>signing object type = XPP_CERTIFICATE</li>
<li>signing object name = XPPUSER1</li>
<li>signing object password = xppuser1</li>
</ul>
<p>peladm create_tradepart</p>
<p>   -n PartnerRemote1</p>
<p>   -f AS2</p>
<p>   -a AS2PR1</p>
<p>   -rs CYCL_XIP1REC_AS2</p>
<p>   -s Y</p>
<p>   -e Y</p>
<p><span style="font-weight: bold;">   -rr signed</span></p>
<p>   -rrto 'http://hpx15:8382/user1/transfer?user=user1&amp;password=user1'</p>
<p>   -frr signed</p>
<p>   -c Y</p>
<p>   -ca ZLIB</p>
<p>   -sa MD5withRSA</p>
<p>   -ea 3DES</p>
<p>   -eot XPP_CERTIFICATE</p>
<p>   -eon XPPUSER1</p>
<p>   -eop xppuser1</p>
<p>   -sot XPP_CERTIFICATE</p>
<p>   -son XPPUSER1</p>
<p>   -sop xppuser1</p>         </td>
      </tr>
      <tr>
         <td><p>Example 2: creating a local partner for AS2</p>         </td>
         <td><p>The following command creates a local Trading Partner object with the characteristics:</p>
<ul>
<li>name = PartnerLocal1</li>
<li>format = AS2</li>
<li>alias = AS2PL1</li>
<li>local = yes</li>
<li>signing algo = SHA1withRSA</li>
<li>encryption certificate type = XPP_CERTIFICATE</li>
<li>encryption certificate name = GW</li>
<li>signing object type = XPP_CERTIFICATE</li>
<li>signing object name = GW</li>
</ul>
<p>peladm create_tradepart</p>
<p>   -n PartnerLocal1</p>
<p>   -a AS2PL1</p>
<p>   -f AS2</p>
<p>   -loc Y</p>
<p>   -sa SHA1withRSA</p>
<p>   -eot XPP_CERTIFICATE</p>
<p>   -eon GW</p>
<p>   -sot XPP_CERTIFICATE</p>
<p>   -son GW</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_display_tradepart"></span>

## Displaying a Trading Partner: peldsp display\_tradepart

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp display_tradepart {-name} [-format] [-alias]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the characteristics of a selected Trading Partner object.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Parameter name (and abbreviation)</p>         </td>
         <td><p><strong>Description</strong></p>         </td>
      </tr>
      <tr>
         <td><p>-name (-n)</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the name of the Trading Partner object for which you want to display the characteristics.</p>         </td>
      </tr>
      <tr>
         <td><p>-format (-f)</p>         </td>
         <td><p>Enter the format of the Trading Partner object for which you want to display the characteristics.</p>
<p>Enter one of:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>RN</li>
<li>CMS<span style="font-weight: normal;"> (for OFTP)</span></li>
<li>SWIFTNET</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-alias (-a)</p>         </td>
         <td><p>Enter the alias of the Trading Partner object for which you want to display the characteristics.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the following command to display the characteristics of a selected AS2-type Trading Partner object:</p>
<p>peldsp display_tradepart</p>
<p>   -f AS2</p>
<p>   -n user1_as1@domain.com</p>
<p> </p>
<p>trade_name='user1_as1@domain.com'</p>
<p>trade_alias='AS2_2'</p>
<p>trade_format='AS2'</p>
<p>trade_is_local='N'</p>
<p>trade_comments=''</p>
<p>trade_dir_path=''</p>
<p>trade_file_component=''</p>
<p>trade_sign_obj_type='XPP_ENTITY'</p>
<p>trade_sign_obj_name='USER2'</p>
<p>trade_sign_obj_password=''</p>
<p>trade_encryption_obj_type='XPP_ENTITY'</p>
<p>trade_encryption_obj_name='USER2'</p>
<p>trade_encryption_obj_password=''</p>
<p>trade_tradepart_org_name='part 1'</p>
<p>trade_remote_site='GW1'</p>
<p>trade_dir_name='/'</p>
<p>trade_encrypt='Y'</p>
<p>trade_sign='Y'</p>
<p>trade_compress='Y'</p>
<p>trade_compress_algo='ZLIB'</p>
<p>trade_encryption_algo='AES128'</p>
<p>trade_key_encryption_algo='RSA'</p>
<p>trade_signing_algo='SHA1withRSA'</p>
<p>trade_receipt_request='signed'</p>
<p>trade_receipt_request_to=''</p>
<p>trade_receipt_request_synchronized='N'</p>
<p>trade_force_receipt_request='undefined'</p>
<p>trade_force_signed='N'</p>
<p>trade_force_encrypted='N'</p>
<p>trade_force_receipt_request_to=''</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peldsp_select_tradepart"></span>

## Selecting a Trading Partner: peldsp select\_tradepart

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peldsp select_tradepart {-name} [-alias] [-format] [-is_local]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to select a given Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Parameter name (and abbreviation)</p>         </td>
         <td><p><strong>Description</strong></p>         </td>
      </tr>
      <tr>
         <td><p>-format (-f)</p>         </td>
         <td><p>Protocol format. Enter one of:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>RN</li>
<li>CMS<span style="font-weight: normal;"> (for OFTP)</span></li>
<li>SWIFTNET</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-name (-n)</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the unique Trading Partner name.</p>         </td>
      </tr>
      <tr>
         <td><p>-alias (-a)</p>         </td>
         <td><p>Enter a name for the Trading Partner object to use as selection criteria.</p>
<p>Gateway stores this alias as part of the data of each Transfer Request. You can use the alias as a substitute for the partner <span class="code">name</span> parameter when depositing Transfer Requests.</p>
<p>By default, the alias is the <span class="code">name (-n)</span> value set to uppercase and truncated to 31 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>-is_local (-loc)</p>         </td>
         <td><p>Enter one of:</p>
<ul>
<li><span style="font-weight: bold;">Y</span> = local</li>
<li><span style="font-weight: bold;">N</span> = remote (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following example selects the AS1 Trading Partner object named <span style="font-style: italic;">user1_as1@domain.com</span>:</p>
<p>peldsp select_tradepart</p>
<p>   -n user1_as1@domain.com</p>
<p>   -f AS1</p>         </td>
      </tr>
   </tbody>
</table>

<span id="peladm_update_tradepart"></span>

## Modifying a Trading Partner: peladm update\_tradepart

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm update_tradepart</span> [parameters]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to modify the characteristics of a Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Refer to the parameters for the <span class="code" style="font-weight: bold;"><a href="#peladm_create_tradepart">peladm create_tradepart</a></span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the following command to modify the Trading Partner object named <span style="font-style: italic;">MyTrade</span>:</p>
<p>peladm update_tradepart</p>
<p>   -n MyTrade</p>
<p>   -f AS2</p>
<p>   -rs CYCL_XIP1REC_AS2</p>
<p>   -s N</p>
<p>   -e N</p>
<p>   -c N</p>         </td>
      </tr>
   </tbody>
</table>

**Note**: There are two types of Trading Partners, Local and Remote which are two distinct objects and must be treated as such. If the Remote Partner is active when modifying the Trading Partner and switching to Local Partner occurs, this may result in abnormal behavior of the product.

<span id="peladm_delete_tradepart"></span>

## Deleting a Trading Partner: peladm delete\_tradepart

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">peladm delete_tradepart {-name} [-format] [-alias]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a Trading Partner.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Parameter name (and abbreviation)</p>         </td>
         <td><p><strong>Description</strong></p>         </td>
      </tr>
      <tr>
         <td><p>-name (-n)</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the unique Trading Partner name.</p>         </td>
      </tr>
      <tr>
         <td><p>-format (-f)</p>         </td>
         <td><p>Protocol format. Enter one of:</p>
<ul>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>SMIME</li>
<li>RN</li>
<li><strong>CMS</strong> (for OFTP)</li>
<li>SWIFTNET</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-alias (-a)</p>         </td>
         <td><p>Enter an alias for the Trading Partner object you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following example deletes the AS1 Trading Partner object named <span style="font-style: italic;">user1_as1@domain.com</span>:</p>
<p>peladm delete_tradepart</p>
<p>   -n user1_as1@domain.com</p>
<p>   -f AS1</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Overview: Trading Partners](../../../ov_gateway/ov_trading_partners)

[Working with Trading Partners (GUI)](../working_with_trading_partners_(gui))

[Configuring the Gateway/SWIFTNet environment](../../../connectors_about/swiftnet_about/swiftnet_connector/swiftnet_configuring)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
