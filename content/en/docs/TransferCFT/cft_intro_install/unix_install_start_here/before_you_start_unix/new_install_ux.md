{
    "title": "Customize the initialize.properties file",
    "linkTitle": "3. Customize the initialize.properties file",
    "weight": "150"
}A common practice is to create a copy of the `initialize.properties ` file, which is located in the downloaded installation package. This gives you an initial intact version should you later need it.

Customize the `initialize.properties ` file. Use the table below to help you with parameter settings; note that the `CryptoKey_Password` is mandatory. Be sure that if you want to use special characters in a configuration file field, you protect the value by enclosing it in double quotation marks ("").

> **Note:**
>
> If you are installing Transfer CFT but have another Transfer CFT profile loaded, you cannot have environment variables in the initialize.properties file for the new installation.

Example

To use the # character in a value, for example, protect the entire string using quotation marks "" as follows:

CryptoKey\_Password = "Aedft#439"

If you do not enclose this value in "", the string is interpreted as: `CryptoKey_Password = Aedft`

> **Note:**
>
> Some parameters can be calculated during the installation (flagged by @automatic); you can leave these fields blank.

> **Note:**
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
         <td><strong>Silent installation</strong>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Installation architecture         </td>
         <td>@default = single         </td>
         <td><p>Defines single or cluster mode installation.</p>
<p>Values: single, first_host, additional_host</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td>installdir         </td>
         <td>          </td>
         <td>Transfer CFT installation directory.         </td>
         <td>cft.install_dir         </td>
      </tr>
      <tr>
         <td><strong>Basic installation</strong>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>runtimeDir         </td>
         <td>./runtime         </td>
         <td><p>Transfer CFT runtime directory.</p>
<p>Specify the directory where you want to install the Transfer
CFT runtime directory.</p>
<p>By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or
specify a new directory. A runtime directory will be created if it does not already exist.</p>
<p>Directory paths cannot contain spaces.</p>         </td>
         <td>cft.runtime_dir         </td>
      </tr>
      <tr>
         <td><p>Full_Hostname</p>         </td>
         <td>@automatic         </td>
         <td><p>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See <strong>Note</strong>*</p>         </td>
         <td>cft.full_hostname         </td>
      </tr>
      <tr>
         <td>multinode_hostname         </td>
         <td>@automatic         </td>
         <td><p>When not defined, this field is filled with the hostname of the machine where you are installing {{< TransferCFT/transfercftname  >}}, whether it is the first host or an additional host.</p>
<p>If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost".</p>         </td>
         <td>cft.multi_node.hostnames         </td>
      </tr>
      <tr>
         <td>multinode_host_address         </td>
         <td>@automatic         </td>
         <td><p>If you do not specify a value, the machine's FQDN address is used.</p>
<p>Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network.</p>         </td>
         <td>cft.multi_node.hostnames.&lt;hostname&gt;.host         </td>
      </tr>
      <tr>
         <td><p>Instance_ID</p>         </td>
         <td>@default
<p> </p>         </td>
         <td>The maximum length is 24.         </td>
         <td>cft.instance_id         </td>
      </tr>
      <tr>
         <td>Instance_Group         </td>
         <td>          </td>
         <td><p>Transfer CFT instance group.</p>
<p>The maximum length is 1000.</p>         </td>
         <td>cft.instance_group         </td>
      </tr>
      <tr>
         <td><strong>Security configuration</strong>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>CryptoKey_Password</p>         </td>
         <td>@mandatory         </td>
         <td><p>Seed password to generate the encryption key.</p>
<p>The password must contains at least 8 characters, contain upper and</p>
<p>lower case characters as well as numeric and special characters (*$!?+-@).</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td><p>CryptoKey_Key_File</p>         </td>
         <td>@default = $CFTDIRRUNTIME/data/crypto/crypkey         </td>
         <td>Location that stores the generated key file.         </td>
         <td>crypto.key_fname              </td>
      </tr>
      <tr>
         <td><p>CryptoKey_Salt_File</p>         </td>
         <td>@default = $CFTDIRRUNTIME/data/crypto/crypsalt         </td>
         <td>Location that stores the generated salt file.         </td>
         <td>crypto.salt_fname         </td>
      </tr>
      <tr>
         <td><strong>Runtime configuration</strong>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Key</p>         </td>
         <td>          </td>
         <td><p>Key for Transfer CFT. The key is stored in the $CFTDIRRUNTIME/conf/cft.key.</p>
<p>Without the key you can install, but not start the product.</p>         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Catalog_File_Size         </td>
         <td>@default= 10000         </td>
         <td><p>Sets the default catalog size.</p>         </td>
         <td>cft.cftcat.default_size         </td>
      </tr>
      <tr>
         <td>Communication_File_Size         </td>
         <td>@default = 1000         </td>
         <td>Sets the default communication file size.         </td>
         <td>cft.cftcom.default_size         </td>
      </tr>
      <tr>
         <td>PESIT_Port         </td>
         <td>@default = 1761         </td>
         <td><p>The port number of the PeSiT protocol.</p>
<p> </p>         </td>
         <td>samples.pesitany_sap.value         </td>
      </tr>
      <tr>
         <td>PESIT_SSL_Port         </td>
         <td>@default = 1762         </td>
         <td>The port number of the PeSIT protocol using SSL.         </td>
         <td>samples.pesitssl_sap.value         </td>
      </tr>
      <tr>
         <td>COMS_Port         </td>
         <td>@default = 1765         </td>
         <td><p>The port number of the COMS synchronous communication media.</p>
<p> </p>         </td>
         <td>samples.coms_port.value         </td>
      </tr>
      <tr>
         <td>Copilot_Port         </td>
         <td>@default = 1766         </td>
         <td><p>Sets the port number for the Transfer CFT Copilot server that listens for</p>
<p>incoming unsecured and secured (SSL) connections.</p>
<p>The same port number is used for the Graphical User Interface and Webservices</p>
<p>with or without SSL.</p>         </td>
         <td>copilot.general.serverport         </td>
      </tr>
      <tr>
         <td>Copilot_OnlySSL         </td>
         <td>@default = Yes         </td>
         <td><p>When you set to <strong>Yes</strong>, Copilot only allows SSL connections, and disables use of the HTTP server.</p>
<p>This  affects the old Transfer CFT UI, Webservices, and JPI.</p>
<p> </p>         </td>
         <td>copilot.http.onlyssl         </td>
      </tr>
      <tr>
         <td>Copilot_SSL_Port         </td>
         <td>@default = 1767         </td>
         <td>Sets the port number for the Transfer CFT Copilot server that listens for
incoming secured (SSL with mutual authentication) connections.
Only used by the Governance.         </td>
         <td>copilot.general.ssl_serverport         </td>
      </tr>
      <tr>
         <td><p>UI_DefaultUser_Username</p>
<p>UI_DefaultUser_Password</p>         </td>
         <td>         </td>
         <td><p><em>UNIX systems only</em></p>
<p>The default Transfer CFT UI user/password.</p>         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td><p>RESTAPI_Enable</p>
<p> </p>
<p> </p>         </td>
         <td>@default = Yes         </td>
         <td><p>Activates the Transfer CFT REST API Server.</p>
<p>The port number used to connect to the REST API server.</p>         </td>
         <td>copilot.restapi.enable         </td>
      </tr>
      <tr>
         <td>RESTAPI_Port         </td>
         <td>1768         </td>
         <td><p>The port number used to connect to the REST API server.</p>         </td>
         <td>copilot.restapi.serverport         </td>
      </tr>
      <tr>
         <td><p>RESTAPI_Certificate_Path</p>
<p>RESTAPI_Cert_Pass</p>         </td>
         <td>          </td>
         <td><p>Sets the certificate and its password to be used by the Transfer</p>
<p>CFT REST API Server and for HTTPS connections with Copilot (old</p>
<p>Transfer CFT UI, Web services, and JPI).</p>
<ul>
<li>When REST API is enabled, these cannot be empty</li>
<li>When Copilot_OnlySSL is activated, these cannot be empty.</li>
</ul>
<p>When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance.</p>         </td>
         <td>copilot.ssl.SslCertFile         </td>
      </tr>
      <tr>
         <td><strong>Multi-node and Cluster</strong>         </td>
      </tr>
      <tr>
         <td>Multinode_Enable         </td>
         <td>@default = No         </td>
         <td><p>Enable the multi-node architecture.</p>
<p>To use a multi-node architecture, you must define the multinode option in the initialize.properties file.</p>         </td>
         <td>cft.multi_node.enable         </td>
      </tr>
      <tr>
         <td>Multinode_Number         </td>
         <td>@default = 2         </td>
         <td>Enter the number of nodes.         </td>
         <td>cft.multi_node.nodes         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Host         </td>
         <td>          </td>
         <td>Specify the host address of the load balancer.
<p>When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.</p>         </td>
         <td>cft.multi_node.load_balancer.host         </td>
      </tr>
      <tr>
         <td>LoadBalancer_Port         </td>
         <td>          </td>
         <td><p>Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.</p>
When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.         </td>
         <td>cft.multi_node.load_balancer.port         </td>
      </tr>
      <tr>
         <td><strong>Central Governance</strong>         </td>
      </tr>
      <tr>
         <td><p>CG_Enable</p>         </td>
         <td><p>@default = No</p>         </td>
         <td>Enter Yes to enable Central Governance connectivity.         </td>
         <td>cg.enable         </td>
      </tr>
      <tr>
         <td>CG_Host         </td>
         <td>          </td>
         <td><p>The Central Governance host address.</p>
<p>If you enabled {{< TransferCFT/centralgovernancename  >}}, you must complete this field.</p>         </td>
         <td>cg.host         </td>
      </tr>
      <tr>
         <td><p>CG_Port</p>         </td>
         <td>@default = 12553         </td>
         <td><p>Central Governance port.</p>
<p>When CG is enabled, this cannot be empty.</p>         </td>
         <td>cg.port         </td>
      </tr>
      <tr>
         <td>CG_Mutual_Port         </td>
         <td>@default = 12554         </td>
         <td><p>The Central Governance port for Mutual Authentication.</p>
<p>If you enabled {{< TransferCFT/centralgovernancename  >}}, you must complete this field.</p>         </td>
         <td>cg.mutual_auth_port         </td>
      </tr>
      <tr>
         <td>CG_RestAPI_Port         </td>
         <td>@default = 8081         </td>
         <td><p>Specify the port to use to communicate with Central Governance's REST API (this port is only used when am.type=cg).</p>
<p>If you enabled {{< TransferCFT/centralgovernancename  >}}, you must complete this field.</p>         </td>
         <td>cg.restapi_port         </td>
      </tr>
      <tr>
         <td>CG_SharedSecret         </td>
         <td>          </td>
         <td><p>Specify the shared secret, which is needed to register with the Central Governance server.</p>
<p>If you enabled {{< TransferCFT/centralgovernancename  >}}, you must complete this field.</p>         </td>
         <td>cg.shared_secret         </td>
      </tr>
      <tr>
         <td>CG_ConfigurationPolicy         </td>
         <td>          </td>
         <td>Specify Central Governance configuration policy to apply on the Transfer CFT
instance.         </td>
         <td>cg.configuration_policy         </td>
      </tr>
      <tr>
         <td>CG_Certificate_Path         </td>
         <td>@default = $CFTDIRRUNTIME/conf/pki/passportCA.pem         </td>
         <td>Specify Custom Certificate to authenticate Central Governance.         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td><strong>Sentinel Connector</strong>         </td>
      </tr>
      <tr>
         <td>Sentinel_Enable         </td>
         <td>@default = No         </td>
         <td><p>Set to Yes to enable Sentinel.</p>
<p>Do not enable this if you have enabled {{< TransferCFT/centralgovernancename  >}}.</p>         </td>
         <td>sentinel.xfb.enable         </td>
      </tr>
      <tr>
         <td>Sentinel_Host         </td>
         <td>          </td>
         <td>Enter the Sentinel host address.         </td>
         <td>sentinel.trkipaddr         </td>
      </tr>
      <tr>
         <td>Sentinel_Port         </td>
         <td>@default= 1305         </td>
         <td><p>Enter the Sentinel port.</p>
<p>You do not need to define this field if you are registering Transfer CFT with {{< TransferCFT/centralgovernancename  >}}.</p>         </td>
         <td>sentinel.trkipport         </td>
      </tr>
      <tr>
         <td>Sentinel_Log_Filter         </td>
         <td>@default = EWF         </td>
         <td><p>Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal
Authorized characters are only I, W, E, F</p>
<p>You can only use each letter once.</p>         </td>
         <td>sentinel.xfb.log         </td>
      </tr>
      <tr>
         <td>Sentinel_Transfer_Filter         </td>
         <td>@default = ALL         </td>
         <td><p>Sentinel Transfer Filter</p>
<p>Possible values are: ALL, SUMMARY, NO, ERROR</p>         </td>
         <td>sentinel.xfb.transfer         </td>
      </tr>
      <tr>
         <td>Sentinel_Use_SSL          </td>
         <td>@default = Yes         </td>
         <td>Enables an SSL connection with Sentinel.         </td>
         <td>sentinel.xfb.use_ssl         </td>
      </tr>
      <tr>
         <td>Sentinel_Certificate_Path         </td>
         <td>@default=$CFTDIRRUNTIME/conf/pki/passportCA.pem         </td>
         <td>Sentinel root certificate.         </td>
         <td>N/A         </td>
      </tr>
      <tr>
         <td><strong>Miscellaneous</strong>         </td>
      </tr>
      <tr>
         <td>JAVA_BINARY_PATH         </td>
         <td>          </td>
         <td>Java binary path used to start Transfer CFT jar files.         </td>
         <td>cft.jre.java_binary_path         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> \*This host address defines:

-   The unconf `sentinel.trkproductipaddr `parameter, which is the host address that identifies this host
-   The host address used to connect this Transfer CFT Copilot server

## Password management

The passwords used in the `initialize.properties` file are encrypted in the original file when you run the installation builder. You can then use the original file as a template for future installations. Impacted passwords are prefaced by &lt;CFT\_PASSWORD>, and include the following:

-   CryptoKey\_Password
-   UI\_DefaultUser\_Password
-   CFT\_ServicePassword
-   CFTUI\_ServicePassword
-   RESTAPI\_Cert\_Pass
-   CG\_SharedSecret
