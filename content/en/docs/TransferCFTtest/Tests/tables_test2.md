{
    "title": "Tests of Customize the initialize.properties file ",
    "linkTitle": "Tests of Customize the initialize.properties file",
    "weight": "60"
}## Flat version of <a href="../original_versions/new_install_ux" class="MCXref xref">Customize the initialize.properties file</a>

### Silent installation

#### Installation architecture

Defines single or cluster mode installation.

@default = single

Values: single, first_host, additional_host

UCONF: N/A

#### installdir

Transfer CFT installation directory.

UCONF: cft.install_dir

#### accept_general_conditions

Set to YES to accept the General Terms and Conditions in the product [license](https://www.axway.com/en/legal/contract-documents) when performing a silent installation.

@default = NO

### Basic installation

#### runtimeDir

Transfer CFT runtime directory. Specify the directory where you want to install the Transfer
CFT runtime directory.

@default = ./runtime

By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or
specify a new directory. A runtime directory will be created if it does not already exist.

UCONF: cft.runtime_dir

#### Full_Hostname

Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See **Note**\*

@default = automatic

UCONF: cft.full_hostname

#### multinode_hostname

When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{< TransferCFTtest/suitevariablesTransferCFTName  >}}, whether it is the first host or an additional host.

@default = automatic

If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost".

UCONF: cft.multi_node.hostnames

#### multinode_host_address

If you do not specify a value, the machine's FQDN address is used. Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network.

@default = automatic

UCONF: cft.multi_node.hostnames.&lt;hostname>.host

#### Instance_ID

The maximum length is 24.

@default

UCONF: cft.instance_id

#### Instance_Group

Transfer CFT instance group. The maximum length is 1000.

UCONF: cft.instance_group

### Security configuration

#### CryptoKey_Password

Seed password to generate the encryption key. The password must contains at least 8 characters, contain upper and lower case characters as well as numeric and special characters (\*$!?+-@).

@mandatory

UCONF: N/A

#### CryptoKey_Key_File

Location that stores the generated key file.

@default = $CFTDIRRUNTIME/data/crypto/crypkey

UCONF: crypto.key_fname     

#### CryptoKey_Salt_File

Location that stores the generated salt file.

@default = $CFTDIRRUNTIME/data/crypto/crypsalt

UCONF: crypto.salt_fname

### Runtime configuration

#### Key

Enter the license key for the Transfer CFT product. The key is stored in the $CFTDIRRUNTIME/conf/cft.key.

*Without the key you can install, but not start the product.*

#### Catalog_File_Size

Sets the default catalog size.

@default= 10000

UCONF: cft.cftcat.default_size

#### Communication_File_Size

Sets the default communication file size.

@default = 1000

UCONF: cft.cftcom.default_size

#### PESIT_Port

The port number of the PeSiT protocol.

@default = 1761

UCONF: samples.pesitany_sap.value

#### PESIT_SSL_Port

The port number of the PeSIT protocol using SSL.

@default = 1762

UCONF: samples.pesitssl_sap.value

#### COMS_Port

The port number of the COMS synchronous communication media.

@default = 1765

UCONF: samples.coms_port.value

#### Copilot_Port

Sets the port number for the Transfer CFT Copilot server that listens for

@default = 1766

incoming unsecured and secured (SSL) connections.

The same port number is used for the Graphical User Interface and Web Services

with or without SSL.

UCONF: copilot.general.serverport

#### Copilot_OnlySSL

Copilot only allows SSL connection.
This value applies to the old Transfer CFT UI, Webservices and JPI.
If you set this to Yes, it disables the use of the HTTP server when an SSL context is
defined (HTTPS only).

@default = Yes

UCONF: copilot.http.onlyssl

#### Copilot_SSL_Port

Sets the port number for the Transfer CFT Copilot server that listens for
incoming secured (SSL with mutual authentication) connections.
Only used by the Governance.

@default = 1767

UCONF: copilot.general.ssl_serverport

#### UI_DefaultUser_Username UI_DefaultUser_Password

*UNIX systems only*

The default Transfer CFT UI user/password.

UCONF: N/A

#### RESTAPI_Enable

Setting this to Yes activates the Transfer CFT REST API Server.

@default = Yes

UCONF: copilot.restapi.enable

#### RESTAPI_Port

The port number used to connect to the REST API server.

@default = 1768

UCONF: copilot.restapi.serverport

#### RESTAPI_Certificate_Path, RESTAPI_Cert_Pass

Sets the certificate and the corresponding password to be used by the Transfer.

CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).

- When REST API is enabled, you must complete these fields.
- When Copilot_OnlySSL is activated, you must complete these fields.

When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance.

UCONF: copilot.ssl.SslCertFile

### Multi-node and Cluster

#### Multinode_Enable

Enable the multi-node architecture. To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.

@default = No

UCONF: cft.multi_node.enable

#### Multinode_Number

Enter the number of nodes.

@default = 2

UCONF: cft.multi_node.nodes

#### LoadBalancer_Host

Specify the host address of the load balancer.
When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.

UCONF:  cft.multi_node.load_balancer.host

#### LoadBalancer_Port

Specify the load balancer port, which is redirected to the
Central Governance dedicated port of the Transfer CFT UI Server.
When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load
balancer to connect to the Transfer CFT Copilot server.

UCONF: cft.multi_node.load_balancer.port

### Central Governance

#### CG_Enable

Enter Yes to enable Central Governance connectivity.

@default = No

UCONF: cg.enable

#### CG_Host

The Central Governance host address.

**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.**

UCONF: cg.host

#### CG_Port

The Central Governance port. If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.

@default = 12553

UCONF: cg.port

#### CG_Mutual_Port

The Central Governance port for Mutual Authentication. If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.

@default = 12554

UCONF: cg.mutual_auth_port

#### CG_SharedSecret

Specify the shared secret, which is needed to register with the Central Governance server. If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.

UCONF: cg.shared_secret

#### CG_ConfigurationPolicy

Specify Central Governance configuration policy to apply to the Transfer CFT
instance.

UCONF: cg.configuration_policy

#### CG_Certificate_Path

Specify the Custom Certificate to authenticate Central Governance.

@default = $CFTDIRRUNTIME/conf/pki/passportCA.pem

UCONF: N/A

### Sentinel Connector

#### Sentinel_Enable

Set to Yes to enable Sentinel.

@default = No

**Do not enable this if you have enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}.**

UCONF: sentinel.xfb.enable

#### Sentinel_Host

Enter the Sentinel host address.

UCONF: sentinel.trkipaddr

#### Sentinel_Port

Enter the Sentinel port.

@default= 1305

You do not need to define this field if you are registering Transfer CFT with Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}.

UCONF: sentinel.trkipport

#### Sentinel_Log_Filter

Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal
Authorized characters are only I, W, E, F

@default = EWF

You can only use each letter once.

UCONF: sentinel.xfb.log

#### Sentinel_Transfer_Filter

Sentinel Transfer Filter

@default = ALL

Possible values are: ALL, SUMMARY, NO, ERROR

UCONF: sentinel.xfb.transfer

#### Sentinel_Use_SSL 

Enables an SSL connection with Sentinel.

@default = Yes

UCONF: sentinel.xfb.use_ssl

#### Sentinel_Certificate_Path

Sentinel root certificate.

@default=$CFTDIRRUNTIME/conf/pki/passportCA.pem

UCONF: N/A

### Windows Services

#### CFT_StartAsService

Start Transfer CFT Server using service mode.

@default = No

UCONF: cft.nt.service_mode

#### CFT_ServiceName, CFT_ServiceDisplayName

Transfer CFT Server Service name.

@default= Transfer_CFT, AMPLIFY Transfer CFT

You cannot have spaces in the CFT_ServiceName.

 UCONF: cft.nt.service_name

#### CFT_ServiceSpecificUser

Use a specific account to start the Transfer CFT Server Service.

@default= No

UCONF: N/A

#### CFT_ServiceUsername , CFT_ServicePassword

The Username (Domain\\User) of the user who will start the Transfer CFT Server.

UCONF: N/A

#### CFT_StartType

Transfer CFT Server service start type: auto, manual, disabled

@default= auto

UCONF: N/A

#### CFTUI_StartAsService

Start Transfer CFT UI Server using service mode.

@default= No

UCONF: copilot.nt.service_mode

#### CFTUI_ServiceName, CFTUI_ServiceDisplayName

Transfer CFT UI Server Service name.

@default= Transfer_CFT_UI, AMPLIFY Transfer CFT UI

You cannot have spaces in the CFTUI_ServiceName.

UCONF: copilot.nt.service_name

#### CFTUI_ServiceSpecificUser

Use a specific account to start the Transfer CFT UI Server Service.

@default= No

UCONF: N/A

#### CFTUI_ServiceUsername CFTUI_ServicePassword

The Username (Domain\\User) of the user who will start the Transfer CFT UI Server.

UCONF: N/A

#### CFTUI_StartType

The Transfer CFT UI Server service start type: auto, manual, disabled

@default= auto

UCONF: N/A

### Miscellaneous

#### JAVA_BINARY_PATH

Java binary path used to start Transfer CFT jar files.

UCONF: cft.jre.java_binary_path

#### IntegrityControl_Enable

Activate integrity control for the Transfer CFT databases.

@default = Yes

### SAML

#### Enable SAML

@default = No

UCONF: am.type= 'saml'

## Split table version of <a href="../original_versions/new_install_ux" class="MCXref xref">Customize the initialize.properties file</a>

#### Silent installation


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| Installation architecture  | @default = single  | Defines single or cluster mode installation.<br/> Values: single, first_host, additional_host | UCONF: N/A  |
| installdir  |   | Transfer CFT installation directory.  | UCONF: cft.install_dir  |
| accept_general_conditions  | NO  | Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation.  |   |


#### Basic installation


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| runtimeDir  | ./runtime  | Transfer CFT runtime directory.<br/> Specify the directory where you want to install the Transfer CFT runtime directory.<br/> By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or specify a new directory. A runtime directory will be created if it does not already exist. | UCONF: cft.runtime_dir  |
| Full_Hostname | @automatic  | Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See **Note*** | UCONF: cft.full_hostname  |
| multinode_hostname  | @automatic  | When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{< TransferCFTtest/suitevariablesTransferCFTName  >}}, whether it is the first host or an additional host.<br/> If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost". | UCONF: cft.multi_node.hostnames  |
| multinode_host_address  | @automatic  | If you do not specify a value, the machine's FQDN address is used.<br/> Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network. | UCONF: cft.multi_node.hostnames.&lt;hostname&gt;.host  |
| Instance_ID | @default  | The maximum length is 24.  | UCONF: cft.instance_id  |
| Instance_Group  |   | Transfer CFT instance group.<br/> The maximum length is 1000. | UCONF: cft.instance_group  |


#### Security configuration


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| CryptoKey_Password | @mandatory  | Seed password to generate the encryption key.<br/> The password must contains at least 8 characters, contain upper and<br/> lower case characters as well as numeric and special characters (*$!?+-@). | UCONF: N/A  |
| CryptoKey_Key_File | @default = $CFTDIRRUNTIME/data/crypto/crypkey  | Location that stores the generated key file.  | UCONF: crypto.key_fname  |
| CryptoKey_Salt_File | @default = $CFTDIRRUNTIME/data/crypto/crypsalt  | Location that stores the generated salt file.  | UCONF: crypto.salt_fname  |


#### Runtime configuration


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| Key |   | Enter the license key for the Transfer CFT product.<br/> The key is stored in the $CFTDIRRUNTIME/conf/cft.key.<br/> *Without the key you can install, but not start the product.* |   |
| Catalog_File_Size  | @default= 10000  | Sets the default catalog size. | UCONF: cft.cftcat.default_size  |
| Communication_File_Size  | @default = 1000  | Sets the default communication file size.  | UCONF: cft.cftcom.default_size  |
| PESIT_Port  | @default = 1761  | The port number of the PeSiT protocol.<br/>  | UCONF: samples.pesitany_sap.value  |
| PESIT_SSL_Port  | @default = 1762  | The port number of the PeSIT protocol using SSL.  | UCONF: samples.pesitssl_sap.value  |
| COMS_Port  | @default = 1765  | The port number of the COMS synchronous communication media.<br/>  | UCONF: samples.coms_port.value  |
| Copilot_Port  | @default = 1766  | Sets the port number for the Transfer CFT Copilot server that listens for<br/> incoming unsecured and secured (SSL) connections.<br/> The same port number is used for the Graphical User Interface and Web Services<br/> with or without SSL. | UCONF: copilot.general.serverport  |
| Copilot_OnlySSL  | @default = Yes  | Copilot only allows SSL connection.<br/> This value applies to the old Transfer CFT UI, Webservices and JPI.<br/> If you set this to Yes, it disables the use of the HTTP server when an SSL context is defined (HTTPS only). | UCONF: copilot.http.onlyssl  |
| Copilot_SSL_Port  | @default = 1767  | Sets the port number for the Transfer CFT Copilot server that listens for incoming secured (SSL with mutual authentication) connections. Only used by the Governance.  | UCONF: copilot.general.ssl_serverport  |
| UI_DefaultUser_Username<br/> UI_DefaultUser_Password |   | *UNIX systems only*<br/> The default Transfer CFT UI user/password. | UCONF: N/A  |
| RESTAPI_Enable<br/> <br/>  | @default = Yes  | Setting this to Yes activates the Transfer CFT REST API Server. | UCONF: copilot.restapi.enable  |
| RESTAPI_Port  | 1768  | The port number used to connect to the REST API server. | UCONF: copilot.restapi.serverport  |
| RESTAPI_Certificate_Path<br/> RESTAPI_Cert_Pass |   | Sets the certificate and the corresponding password to be used by the Transfer<br/> CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).<br/> • When REST API is enabled, you must complete these fields.<br/> • When Copilot_OnlySSL is activated, you must complete these fields.<br/> When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance. | UCONF: copilot.ssl.SslCertFile  |


#### Multi-node and Cluster


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| Multinode_Enable  | @default = No  | Enable the multi-node architecture.<br/> To use a multi-node architecture, you must define the multi-node option in the initialize.properties file. | UCONF: cft.multi_node.enable  |
| Multinode_Number  | @default = 2  | Enter the number of nodes.  | UCONF: cft.multi_node.nodes  |
| LoadBalancer_Host  |   | Specify the host address of the load balancer.<br/> When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load balancer to connect to the Transfer CFT Copilot server. | UCONF: cft.multi_node.load_balancer.host  |
| LoadBalancer_Port  |   | Specify the load balancer port, which is redirected to the Central Governance dedicated port of the Transfer CFT UI Server. When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load balancer to connect to the Transfer CFT Copilot server. | UCONF: cft.multi_node.load_balancer.port  |


#### Central Governance


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| CG_Enable | @default = No | Enter Yes to enable Central Governance connectivity.  | UCONF: cg.enable  |
| CG_Host  |   | The Central Governance host address.<br/> **If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.** | UCONF: cg.host  |
| CG_Port | @default = 12553  | The Central Governance port.<br/> **If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.** | UCONF: cg.port  |
| CG_Mutual_Port  | @default = 12554  | The Central Governance port for Mutual Authentication.<br/> **If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.** | UCONF: cg.mutual_auth_port  |
| CG_SharedSecret  |   | Specify the shared secret, which is needed to register with the Central Governance server.<br/> **If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}, you must complete this field.** | UCONF: cg.shared_secret  |
| CG_ConfigurationPolicy  |   | Specify Central Governance configuration policy to apply to the Transfer CFT instance.  | UCONF: cg.configuration_policy  |
| CG_Certificate_Path  | @default = $CFTDIRRUNTIME/conf/pki/passportCA.pem  | Specify the Custom Certificate to authenticate Central Governance.  | UCONF: N/A  |


#### Sentinel Connector


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| Sentinel_Enable  | @default = No  | Set to Yes to enable Sentinel.<br/> **Do not enable this if you have enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}.** | UCONF: sentinel.xfb.enable  |
| Sentinel_Host  |   | Enter the Sentinel host address.  | UCONF: sentinel.trkipaddr  |
| Sentinel_Port  | @default= 1305  | Enter the Sentinel port.<br/> You do not need to define this field if you are registering Transfer CFT with Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName  >}}. | UCONF: sentinel.trkipport  |
| Sentinel_Log_Filter  | @default = EWF  | Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal Authorized characters are only I, W, E, F<br/> You can only use each letter once. | UCONF: sentinel.xfb.log  |
| Sentinel_Transfer_Filter  | @default = ALL  | Sentinel Transfer Filter<br/> Possible values are: ALL, SUMMARY, NO, ERROR | UCONF: sentinel.xfb.transfer  |
| Sentinel_Use_SSL  | @default = Yes  | Enables an SSL connection with Sentinel.  | UCONF: sentinel.xfb.use_ssl  |
| Sentinel_Certificate_Path  | @default=$CFTDIRRUNTIME/conf/pki/passportCA.pem  | Sentinel root certificate.  | UCONF: N/A  |


#### Windows Services


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| CFT_StartAsService  | @default = No  | Start Transfer CFT Server using service mode.  | UCONF: cft.nt.service_mode  |
| CFT_ServiceName<br/> CFT_ServiceDisplayName | @default= Transfer_CFT<br/> @default= AMPLIFY Transfer CFT | Transfer CFT Server Service name.<br/> You cannot have spaces in the CFT_ServiceName. |  UCONF: cft.nt.service_name  |
| CFT_ServiceSpecificUser  | @default= No  | Use a specific account to start the Transfer CFT Server Service.  | UCONF: N/A  |
| CFT_ServiceUsername<br/> CFT_ServicePassword |   | The Username (Domain\User) of the user who will start the Transfer CFT Server.  | UCONF: N/A  |
| CFT_StartType  | @default= auto  | Transfer CFT Server service start type: auto, manual, disabled  | UCONF: N/A  |
| CFTUI_StartAsService  | @default= No  | Start Transfer CFT UI Server using service mode.  | UCONF: copilot.nt.service_mode  |
| CFTUI_ServiceName CFTUI_ServiceDisplayName  | @default= Transfer_CFT_UI<br/> @default= AMPLIFY Transfer CFT UI | Transfer CFT UI Server Service name.<br/> You cannot have spaces in the CFTUI_ServiceName. | vcopilot.nt.service_name  |
| CFTUI_ServiceSpecificUser  | @default= No  | Use a specific account to start the Transfer CFT UI Server Service.  | UCONF: N/A  |
| CFTUI_ServiceUsername CFTUI_ServicePassword  |   | The Username (Domain\User) of the user who will start the Transfer CFT UI Server.  | UCONF: N/A  |
| CFTUI_StartType  | @default= auto  | The Transfer CFT UI Server service start type: auto, manual, disabled  | UCONF: N/A  |


#### Miscellaneous


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| JAVA_BINARY_PATH  |   | Java binary path used to start Transfer CFT jar files.  | UCONF: cft.jre.java_binary_path  |
| IntegrityControl_Enable  | @default = Yes  | Activate integrity control for the Transfer CFT databases.  |   |


#### SAML


| Parameter  | Automatic or default  | Description  | UCONF  |
| --- | --- | --- | --- |
| Enable SAML  | @default = No  |   | UCONF: am.type= 'saml'  |


 

## Original from <a href="../original_versions/new_install_ux" class="MCXref xref">Customize the initialize.properties file</a>

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

 
