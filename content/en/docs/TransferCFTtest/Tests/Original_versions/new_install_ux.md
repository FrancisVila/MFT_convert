{
    "title": "Customize the initialize.properties file",
    "linkTitle": "Customize the initialize.properties file",
    "weight": "100"
}A common practice is to create a copy of the `initialize.properties ` file, which is located in the downloaded installation package. This gives you an initial intact version should you later need it.

Customize the `initialize.properties ` file. Use the table below to help you with parameter settings; note that the `CryptoKey_Password` is mandatory. Be sure that if you want to use special characters in a configuration file field, you protect the value by enclosing it in double quotation marks ("").

> **Note**
>
> If you are installing Transfer CFT but have another Transfer CFT profile loaded, you cannot have environment variables in the initialize.properties file for the new installation.

****Example****

To use the # character in a value, for example, protect the entire string using quotation marks "" as follows:

`CryptoKey_Password = "Aedft#439"`

If you do not enclose this value in "", the string is interpreted as: `CryptoKey_Password = Aedft`

> **Note**
>
> Some parameters can be calculated during the installation (flagged by @automatic); you can leave these fields blank.

> **Note**
>
> Parameters that have default values are flagged by @default.

<table>
   <thead>
      <tr>
<th >Parameter         </th>
<th >Automatic or default         </th>
<th >Description         </th>
<th >UCONF          </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="3" ><strong><strong>Silent installation</strong></strong>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td >Installation architecture         </td>
         <td >@default = single         </td>
         <td ><p>Defines single or cluster mode installation.</p>
<p>Values: single, first_host, additional_host</p>         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >installdir         </td>
         <td >          </td>
         <td >Transfer CFT installation directory.         </td>
         <td >cft.install_dir         </td>
      </tr>
      <tr>
         <td >accept_general_conditions         </td>
         <td >NO         </td>
         <td >Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation.         </td>
         <td >          </td>
      </tr>
      <tr>
         <td colspan="3" ><strong><strong>Basic installation</strong></strong>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td >runtimeDir         </td>
         <td >./runtime         </td>
         <td ><p>Transfer CFT runtime directory.</p>
<p>Specify the directory where you want to install the Transfer
CFT runtime directory.</p>
<p>By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or
specify a new directory. A runtime directory will be created if it does not already exist.</p>         </td>
         <td >cft.runtime_dir         </td>
      </tr>
      <tr>
         <td ><p>Full_Hostname</p>         </td>
         <td >@automatic         </td>
         <td ><p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See <strong>Note</strong>*</p>         </td>
         <td >cft.full_hostname         </td>
      </tr>
      <tr>
         <td >multinode_hostname         </td>
         <td >@automatic         </td>
         <td ><p>When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{< TransferCFTtest/suitevariablesTransferCFTName  >}}, whether it is the first host or an additional host.</p>
<p>If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost".</p>         </td>
         <td >cft.multi_node.hostnames         </td>
      </tr>
      <tr>
         <td >multinode_host_address         </td>
         <td >@automatic         </td>
         <td ><p>If you do not specify a value, the machine's FQDN address is used.</p>
<p>Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network.</p>         </td>
         <td >cft.multi_node.hostnames.&lt;hostname&gt;.host         </td>
      </tr>
      <tr>
         <td ><p>Instance_ID</p>         </td>
         <td >@default
<p> </p>         </td>
         <td >The maximum length is 24.         </td>
         <td >cft.instance_id         </td>
      </tr>
      <tr>
         <td >Instance_Group         </td>
         <td >          </td>
         <td ><p>Transfer CFT instance group.</p>
<p>The maximum length is 1000.</p>         </td>
         <td >cft.instance_group         </td>
      </tr>
      <tr>
         <td colspan="3" ><strong><strong>Security configuration</strong></strong>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td ><p>CryptoKey_Password</p>         </td>
         <td >@mandatory         </td>
         <td ><p>Seed password to generate the encryption key.</p>
<p>The password must contains at least 8 characters, contain upper and</p>
<p>lower case characters as well as numeric and special characters (*$!?+-@).</p>         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td ><p>CryptoKey_Key_File</p>         </td>
         <td >@default = $CFTDIRRUNTIME/data/crypto/crypkey         </td>
         <td >Location that stores the generated key file.         </td>
         <td >crypto.key_fname              </td>
      </tr>
      <tr>
         <td ><p>CryptoKey_Salt_File</p>         </td>
         <td >@default = $CFTDIRRUNTIME/data/crypto/crypsalt         </td>
         <td >Location that stores the generated salt file.         </td>
         <td >crypto.salt_fname         </td>
      </tr>
      <tr>
         <td colspan="3" ><strong><strong>Runtime configuration</strong></strong>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td ><p>Key</p>         </td>
         <td >          </td>
         <td ><p>Enter the license key for the Transfer CFT product.</p>
<p>The key is stored in the $CFTDIRRUNTIME/conf/cft.key.</p>
<p><em>Without the key you can install, but not start the product.</em></p>         </td>
         <td >          </td>
      </tr>
      <tr>
         <td >Catalog_File_Size         </td>
         <td >@default= 10000         </td>
         <td ><p>Sets the default catalog size.</p>         </td>
         <td >cft.cftcat.default_size         </td>
      </tr>
      <tr>
         <td >Communication_File_Size         </td>
         <td >@default = 1000         </td>
         <td >Sets the default communication file size.         </td>
         <td >cft.cftcom.default_size         </td>
      </tr>
      <tr>
         <td >PESIT_Port         </td>
         <td >@default = 1761         </td>
         <td ><p>The port number of the PeSiT protocol.</p>
<p> </p>         </td>
         <td >samples.pesitany_sap.value         </td>
      </tr>
      <tr>
         <td >PESIT_SSL_Port         </td>
         <td >@default = 1762         </td>
         <td >The port number of the PeSIT protocol using SSL.         </td>
         <td >samples.pesitssl_sap.value         </td>
      </tr>
      <tr>
         <td >COMS_Port         </td>
         <td >@default = 1765         </td>
         <td ><p>The port number of the COMS synchronous communication media.</p>
<p> </p>         </td>
         <td >samples.coms_port.value         </td>
      </tr>
      <tr>
         <td >Copilot_Port         </td>
         <td >@default = 1766         </td>
         <td ><p>Sets the port number for the Transfer CFT Copilot server that listens for</p>
<p>incoming unsecured and secured (SSL) connections.</p>
<p>The same port number is used for the Graphical User Interface and Web Services</p>
<p>with or without SSL.</p>         </td>
         <td >copilot.general.serverport         </td>
      </tr>
      <tr>
         <td >Copilot_OnlySSL         </td>
         <td >@default = Yes         </td>
         <td ><p>Copilot only allows SSL connection.</p>
<p>This value applies to the old Transfer CFT UI, Webservices and JPI.</p>
<p>If you set this to Yes, it disables the use of the HTTP server when an SSL context is
defined (HTTPS only).</p>         </td>
         <td >copilot.http.onlyssl         </td>
      </tr>
      <tr>
         <td >Copilot_SSL_Port         </td>
         <td >@default = 1767         </td>
         <td >Sets the port number for the Transfer CFT Copilot server that listens for
incoming secured (SSL with mutual authentication) connections.
Only used by the Governance.         </td>
         <td >copilot.general.ssl_serverport         </td>
      </tr>
      <tr>
         <td ><p>UI_DefaultUser_Username</p>
<p>UI_DefaultUser_Password</p>         </td>
         <td >         </td>
         <td ><p><em>UNIX systems only</em></p>
<p>The default Transfer CFT UI user/password.</p>         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td ><p>RESTAPI_Enable</p>
<p> </p>
<p> </p>         </td>
         <td >@default = Yes         </td>
         <td ><p>Setting this to Yes activates the Transfer CFT REST API Server.</p>         </td>
         <td >copilot.restapi.enable         </td>
      </tr>
      <tr>
         <td >RESTAPI_Port         </td>
         <td >1768         </td>
         <td ><p>The port number used to connect to the REST API server.</p>         </td>
         <td >copilot.restapi.serverport         </td>
      </tr>
      <tr>
         <td ><p>RESTAPI_Certificate_Path</p>
<p>RESTAPI_Cert_Pass</p>         </td>
         <td >          </td>
         <td ><p>Sets the certificate and the corresponding password to be used by the Transfer</p>
<p>CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).</p>
<ul>
<li>When REST API is enabled, you must complete these fields.</li>
<li>When Copilot_OnlySSL is activated, you must complete these fields.</li>
</ul>
<p>When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance.</p>         </td>
         <td >copilot.ssl.SslCertFile         </td>
      </tr>
      <tr>
         <td colspan="4" ><strong><strong>Multi-node and Cluster</strong></strong>         </td>
      </tr>
      <tr>
         <td >Multinode_Enable         </td>
         <td >@default = No         </td>
         <td ><p>Enable the multi-node architecture.</p>
<p>To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.</p>         </td>
         <td >cft.multi_node.enable         </td>
      </tr>
      <tr>
         <td >Multinode_Number         </td>
         <td >@default = 2         </td>
         <td >Enter the number of nodes.         </td>
         <td >cft.multi_node.nodes         </td>
      </tr>
      <tr>
         <td >LoadBalancer_Host         </td>
         <td >          </td>
         <td ><p>Specify the host address of the load balancer.</p>
<p>When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
         <td >cft.multi_node.load_balancer.host         </td>
      </tr>
      <tr>
         <td >LoadBalancer_Port         </td>
         <td >          </td>
         <td >Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.
<p>When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
         <td >cft.multi_node.load_balancer.port         </td>
      </tr>
      <tr>
         <td colspan="4" ><strong><strong>Central Governance</strong></strong>         </td>
      </tr>
      <tr>
         <td ><p>CG_Enable</p>         </td>
         <td ><p>@default = No</p>         </td>
         <td >Enter Yes to enable Central Governance connectivity.         </td>
         <td >cg.enable         </td>
      </tr>
      <tr>
         <td >CG_Host         </td>
         <td >          </td>
         <td ><p>The Central Governance host address.</p>
<p><em><em>If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.</em></em></p>         </td>
         <td >cg.host         </td>
      </tr>
      <tr>
         <td ><p>CG_Port</p>         </td>
         <td >@default = 12553         </td>
         <td ><p>The Central Governance port.</p>
<p><em><em>If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.</em></em></p>         </td>
         <td >cg.port         </td>
      </tr>
      <tr>
         <td >CG_Mutual_Port         </td>
         <td >@default = 12554         </td>
         <td ><p>The Central Governance port for Mutual Authentication.</p>
<p><em><em>If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.</em></em></p>         </td>
         <td >cg.mutual_auth_port         </td>
      </tr>
      <tr>
         <td >CG_SharedSecret         </td>
         <td >          </td>
         <td ><p>Specify the shared secret, which is needed to register with the Central Governance server.</p>
<p><em><em>If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.</em></em></p>         </td>
         <td >cg.shared_secret         </td>
      </tr>
      <tr>
         <td >CG_ConfigurationPolicy         </td>
         <td >          </td>
         <td >Specify Central Governance configuration policy to apply to the Transfer CFT
instance.         </td>
         <td >cg.configuration_policy         </td>
      </tr>
      <tr>
         <td >CG_Certificate_Path         </td>
         <td >@default = $CFTDIRRUNTIME/conf/pki/passportCA.pem         </td>
         <td >Specify the Custom Certificate to authenticate Central Governance.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td colspan="4" ><strong><strong>Sentinel Connector</strong></strong>         </td>
      </tr>
      <tr>
         <td >Sentinel_Enable         </td>
         <td >@default = No         </td>
         <td ><p>Set to Yes to enable Sentinel.</p>
<p><em><em>Do not enable this if you have enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}.</em></em></p>         </td>
         <td >sentinel.xfb.enable         </td>
      </tr>
      <tr>
         <td >Sentinel_Host         </td>
         <td >          </td>
         <td >Enter the Sentinel host address.         </td>
         <td >sentinel.trkipaddr         </td>
      </tr>
      <tr>
         <td >Sentinel_Port         </td>
         <td >@default= 1305         </td>
         <td ><p>Enter the Sentinel port.</p>
<p>You do not need to define this field if you are registering Transfer CFT with Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}.</p>         </td>
         <td >sentinel.trkipport         </td>
      </tr>
      <tr>
         <td >Sentinel_Log_Filter         </td>
         <td >@default = EWF         </td>
         <td ><p>Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal
Authorized characters are only I, W, E, F</p>
<p>You can only use each letter once.</p>         </td>
         <td >sentinel.xfb.log         </td>
      </tr>
      <tr>
         <td >Sentinel_Transfer_Filter         </td>
         <td >@default = ALL         </td>
         <td ><p>Sentinel Transfer Filter</p>
<p>Possible values are: ALL, SUMMARY, NO, ERROR</p>         </td>
         <td >sentinel.xfb.transfer         </td>
      </tr>
      <tr>
         <td >Sentinel_Use_SSL          </td>
         <td >@default = Yes         </td>
         <td >Enables an SSL connection with Sentinel.         </td>
         <td >sentinel.xfb.use_ssl         </td>
      </tr>
      <tr>
         <td >Sentinel_Certificate_Path         </td>
         <td >@default=$CFTDIRRUNTIME/conf/pki/passportCA.pem         </td>
         <td >Sentinel root certificate.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td colspan="4" ><strong>Windows Services</strong>         </td>
      </tr>
      <tr>
         <td >CFT_StartAsService         </td>
         <td >@default = No         </td>
         <td >Start Transfer CFT Server using service mode.         </td>
         <td >cft.nt.service_mode         </td>
      </tr>
      <tr>
         <td ><p>CFT_ServiceName</p>
<p>CFT_ServiceDisplayName</p>         </td>
         <td ><p>@default= Transfer_CFT</p>
<p>@default= AMPLIFY Transfer CFT</p>         </td>
         <td ><p>Transfer CFT Server Service name.</p>
<p>You cannot have spaces in the CFT_ServiceName.</p>         </td>
         <td > cft.nt.service_name         </td>
      </tr>
      <tr>
         <td >CFT_ServiceSpecificUser         </td>
         <td >@default= No         </td>
         <td >Use a specific account to start the Transfer CFT Server Service.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td ><p>CFT_ServiceUsername</p>
<p>CFT_ServicePassword</p>         </td>
         <td >          </td>
         <td >The Username (Domain\User) of the user who will start the Transfer CFT Server.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >CFT_StartType         </td>
         <td >@default= auto         </td>
         <td >Transfer CFT Server service start type: auto, manual, disabled         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >CFTUI_StartAsService         </td>
         <td >@default= No         </td>
         <td >Start Transfer CFT UI Server using service mode.         </td>
         <td >copilot.nt.service_mode         </td>
      </tr>
      <tr>
         <td >CFTUI_ServiceName
CFTUI_ServiceDisplayName         </td>
         <td ><p>@default= Transfer_CFT_UI</p>
<p>@default= AMPLIFY Transfer CFT UI</p>         </td>
         <td ><p>Transfer CFT UI Server Service name.</p>
<p>You cannot have spaces in the CFTUI_ServiceName.</p>         </td>
         <td >copilot.nt.service_name         </td>
      </tr>
      <tr>
         <td >CFTUI_ServiceSpecificUser         </td>
         <td >@default= No         </td>
         <td >Use a specific account to start the Transfer CFT UI Server Service.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >CFTUI_ServiceUsername
CFTUI_ServicePassword         </td>
         <td >          </td>
         <td >The Username (Domain\User) of the user who will start the Transfer CFT UI Server.         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td >CFTUI_StartType         </td>
         <td >@default= auto         </td>
         <td >The Transfer CFT UI Server service start type: auto, manual, disabled         </td>
         <td >N/A         </td>
      </tr>
      <tr>
         <td colspan="4" ><strong><strong>Miscellaneous</strong></strong>         </td>
      </tr>
      <tr>
         <td >JAVA_BINARY_PATH         </td>
         <td >          </td>
         <td >Java binary path used to start Transfer CFT jar files.         </td>
         <td >cft.jre.java_binary_path         </td>
      </tr>
      <tr>
         <td >IntegrityControl_Enable         </td>
         <td >@default = Yes         </td>
         <td >Activate integrity control for the Transfer CFT databases.         </td>
         <td >          </td>
      </tr>
      <tr>
         <td colspan="4" ><strong>SAML</strong>         </td>
      </tr>
      <tr>
         <td >Enable SAML         </td>
         <td >@default = No         </td>
         <td >          </td>
         <td >am.type= 'saml'         </td>
      </tr>
   </tbody>
</table>

> **Note**
>
> \*This host address defines:

- The unconf `sentinel.trkproductipaddr `parameter, which is the host address that identifies this host
- The host address used to connect this Transfer CFT Copilot server

## Password management

The passwords used in the `initialize.properties` file are encrypted in the original file when you run the installation builder. You can then use the original file as a template for future installations. Impacted passwords are prefaced by &lt;CFT_PASSWORD>, and include the following:

- CryptoKey_Password
- UI_DefaultUser_Password
- CFT_ServicePassword
- CFTUI_ServicePassword
- RESTAPI_Cert_Pass
- CG_SharedSecret
