
| ID  | Description  |

| --- | --- |

| copilot.http.aliases  | List of enabled alias-id  |

| copilot.http.aliases.(alias-id) alias  | Name of the alias  |

| copilot.http.aliases.(alias-id).path  | Path that replaces the alias in the URL  |




| Parameter  | Description  |

| --- | --- |

| copilot.http.onlyssl  | Enter Yes to restrict the access of the Transfer CFT{{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} user interface with https.  |




| Parameter  | Value  |

| --- | --- |

| copilot.misc.client_keep_alive_delay  | Enter an integer for the delay in seconds.<br/> 60 = default<br/> 0 = no keep-alive |








| Parameter  | Value  |

| --- | --- |

| copilot.misc.ClientTimeout  | Enter an integer for the timeout in minutes.<br/> 30 = default<br/> 0 = no timeout |








| Parameter  | Value  | Former value  |

| --- | --- | --- |

| copilot.webservices.wsicomplience  | (bool) No  | [WEBSERVICES] WsiComplience  |

| copilot.webservices.upload_directory  | (dir) $(cft.runtime_dir)/conf/ws_upload  | NA  |













| Parameter | Value |

| --- | --- |

| copilot.ssl.SslCertFile | conf/pki/&lt;my_certificate&gt;.p12 |

| copilot.ssl.SslCertPassword | Certificate password |

| copilot.ssl.SslKeyFile | Not used |

| copilot.ssl.SslKeyPassword | Not used |








| Parameter | Value |

| --- | --- |

| copilot.ssl.SslCertFile | conf/pki /&lt;my_certificate&gt;.der *or* .pem |

| copilot.ssl.SslCertPassword | Not used |

| copilot.ssl.SslKeyFile | conf/pki /&lt;my_key&gt;.der *or* .pem |

| copilot.ssl.SslKeyPassword | Key password, which is mandatory if the key file is encrypted PKCS#8 |








| Parameter | Value |

| --- | --- |

| copilot.http.onlyssl |  • No: Default value.<br/> • Yes: Restricts access to the Transfer CFT Copilot server to HTTPS secured connections only. |

| <span id="copilot.ssl.SslCipherSuites"></span>copilot.ssl.SslCipherSuites<br/>  | A comma separated list of cipher suites accepted by the Transfer CFT Copilot server.<br/> • “47, 10, 9, 2”: Default value.<br/> <br/> List of supported cipher suites:<br/> • 1 = RSA_WITH_NULL_MD5<br/> • 2 = RSA_WITH_NULL_SHA<br/> • 4 = RSA_WITH_RC4_MD5<br/> • 5 = RSA_WITH_RC4_SHA<br/> • 9 = RSA_WITH_DES_CBC_SHA1<br/> • 10 = RSA_WITH_3DES_EDE_CBC_SHA<br/> • 47 = RSA_WITH_AES_128_CBC_SHA<br/> • 53 = RSA_WITH_AES_256_CBC_SHA<br/> • 59 = RSA_WITH_NULL_SHA256<br/> • 60 = RSA_WITH_AES_128_CBC_SHA256<br/> • 61 = RSA_WITH_AES_256_CBC_SHA256 |

| copilot.ssl.version_min  | Indicates the minimum version of SSL that the Copilot and the REST API server accept.<br/> • Default: tls_1.0<br/> • Possible values are: ssl_3.0 (not recommended), tls_1.0, tls_1.0, tls_1.2 |









| Parameter  | Value  | Description  |

| --- | --- | --- |

| ACKMINDATE  | integer  | From this date on, the acknowledgement exec file can be launched.  |

| ACKMINTIME  | integer  | From this time on, the acknowledgement exec file can be launched.  |

| POSTMINDATE  | integer  | From this date on, the post processing exec file can be launched.  |

| POSTMINTIME  | integer  | From this time on, the post processing exec file can be launched.  |

| PREMINDATE  | integer  | From this date on, the preprocessing exec file can be launched.  |

| PREMINTIME  | integer  | From this time on, the preprocessing exec file can be launched.  |

| ACKEXEC  | string  | The acknowledgement exec file that will be launched after receiving an ACK or NACK.  |

| ACKSTATE  | REQUIRE/IGNORE  | Specify if Transfer CFT{{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} should wait for an ACK/NACK to enter the X phase.  |

| POSTSTATE  | DISP  | The transfer phase step as it enters the Y phase.  |

| PREEXEC  | string  | The preprocessing exec file.  |

| PRESTATE  | DISP/HOLD  | The transfer phase step as it enters the A phase.  |

| EXECSUBPRE  | LIST/SUBF/FILE  | Group of files: execution policy for preprocessing phase.  |

| EXECSUB  | LIST/SUBF/FILE  | Group of files: execution policy for post-processing phase.  |

| EXECSUBA  | LIST/SUBF/FILE  | Group of files: execution policy for acknowledgement phase.  |








| Parameter  | Value  | Description  |

| --- | --- | --- |

| DIAGC  | string  | Specify a comment.  |

| FNAME  | string  | Modify the FNAME.  |

| NFNAME  | string  | Modify the NFNAME.  |

| SIGFNAME  | string  | Modify the SIGFNAME.  |

| RAPPL  | string  | Modify the RAPPL.  |

| SAPPL  | string  | Modify the SAPPL.  |

| RUSER  | string  | Modify the RUSER.  |

| SUSER  | string  | Modify the SUSER.  |

| RPASSWD  | string  | Modify the RPASSWD.  |

| SPASSWD  | string  | Modify the SPASSWD.  |

| ISTATE  | NO/YES  | Indicates:<br/> • YES: The END command is only a checkpoint.<br/> • NO (default): This is the final end command indicating that the processing is over. Once the END completes, the transfer enters the next phase. |

| PHASE  | char  | The transfer phase at which the command is applied.  |

| PHASE STEP  | char  | The phase step at which the command is applied.  |

| APPSTATE  | string  | Specify an application state for the processing script that will help the script to restart at the right step if the script is relaunched.  |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| Installation architecture  | @default = single  | Defines single or cluster mode installation.<br/> Values: single, first_host, additional_host | UCONF: N/A  |

| installdir  |   | Transfer CFT installation directory.  | UCONF: cft.install_dir  |

| accept_general_conditions  | NO  | Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation.  |   |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| runtimeDir  | ./runtime  | Transfer CFT runtime directory.<br/> Specify the directory where you want to install the Transfer CFT runtime directory.<br/> By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or specify a new directory. A runtime directory will be created if it does not already exist. | UCONF: cft.runtime_dir  |

| Full_Hostname | @automatic  | Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See **Note*** | UCONF: cft.full_hostname  |

| multinode_hostname  | @automatic  | When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{&lt; TransferCFTtest/suitevariablesTransferCFTName &gt;}}, whether it is the first host or an additional host.<br/> If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost". | UCONF: cft.multi_node.hostnames  |

| multinode_host_address  | @automatic  | If you do not specify a value, the machine's FQDN address is used.<br/> Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network. | UCONF: cft.multi_node.hostnames.&lt;hostname&gt;.host  |

| Instance_ID | @default  | The maximum length is 24.  | UCONF: cft.instance_id  |

| Instance_Group  |   | Transfer CFT instance group.<br/> The maximum length is 1000. | UCONF: cft.instance_group  |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| CryptoKey_Password | @mandatory  | Seed password to generate the encryption key.<br/> The password must contains at least 8 characters, contain upper and<br/> lower case characters as well as numeric and special characters (*$!?+-@). | UCONF: N/A  |

| CryptoKey_Key_File | @default = $CFTDIRRUNTIME/data/crypto/crypkey  | Location that stores the generated key file.  | UCONF: crypto.key_fname  |

| CryptoKey_Salt_File | @default = $CFTDIRRUNTIME/data/crypto/crypsalt  | Location that stores the generated salt file.  | UCONF: crypto.salt_fname  |








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








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| Multinode_Enable  | @default = No  | Enable the multi-node architecture.<br/> To use a multi-node architecture, you must define the multi-node option in the initialize.properties file. | UCONF: cft.multi_node.enable  |

| Multinode_Number  | @default = 2  | Enter the number of nodes.  | UCONF: cft.multi_node.nodes  |

| LoadBalancer_Host  |   | Specify the host address of the load balancer.<br/> When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load balancer to connect to the Transfer CFT Copilot server. | UCONF: cft.multi_node.load_balancer.host  |

| LoadBalancer_Port  |   | Specify the load balancer port, which is redirected to the Central Governance dedicated port of the Transfer CFT UI Server. When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load balancer to connect to the Transfer CFT Copilot server. | UCONF: cft.multi_node.load_balancer.port  |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| CG_Enable | @default = No | Enter Yes to enable Central Governance connectivity.  | UCONF: cg.enable  |

| CG_Host  |   | The Central Governance host address.<br/> **If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.** | UCONF: cg.host  |

| CG_Port | @default = 12553  | The Central Governance port.<br/> **If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.** | UCONF: cg.port  |

| CG_Mutual_Port  | @default = 12554  | The Central Governance port for Mutual Authentication.<br/> **If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.** | UCONF: cg.mutual_auth_port  |

| CG_SharedSecret  |   | Specify the shared secret, which is needed to register with the Central Governance server.<br/> **If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.** | UCONF: cg.shared_secret  |

| CG_ConfigurationPolicy  |   | Specify Central Governance configuration policy to apply to the Transfer CFT instance.  | UCONF: cg.configuration_policy  |

| CG_Certificate_Path  | @default = $CFTDIRRUNTIME/conf/pki/passportCA.pem  | Specify the Custom Certificate to authenticate Central Governance.  | UCONF: N/A  |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| Sentinel_Enable  | @default = No  | Set to Yes to enable Sentinel.<br/> **Do not enable this if you have enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}.** | UCONF: sentinel.xfb.enable  |

| Sentinel_Host  |   | Enter the Sentinel host address.  | UCONF: sentinel.trkipaddr  |

| Sentinel_Port  | @default= 1305  | Enter the Sentinel port.<br/> You do not need to define this field if you are registering Transfer CFT with Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}. | UCONF: sentinel.trkipport  |

| Sentinel_Log_Filter  | @default = EWF  | Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal Authorized characters are only I, W, E, F<br/> You can only use each letter once. | UCONF: sentinel.xfb.log  |

| Sentinel_Transfer_Filter  | @default = ALL  | Sentinel Transfer Filter<br/> Possible values are: ALL, SUMMARY, NO, ERROR | UCONF: sentinel.xfb.transfer  |

| Sentinel_Use_SSL  | @default = Yes  | Enables an SSL connection with Sentinel.  | UCONF: sentinel.xfb.use_ssl  |

| Sentinel_Certificate_Path  | @default=$CFTDIRRUNTIME/conf/pki/passportCA.pem  | Sentinel root certificate.  | UCONF: N/A  |








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








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| JAVA_BINARY_PATH  |   | Java binary path used to start Transfer CFT jar files.  | UCONF: cft.jre.java_binary_path  |

| IntegrityControl_Enable  | @default = Yes  | Activate integrity control for the Transfer CFT databases.  |   |








| Parameter  | Automatic or default  | Description  | UCONF  |

| --- | --- | --- | --- |

| Enable SAML  | @default = No  |   | UCONF: am.type= 'saml'  |






