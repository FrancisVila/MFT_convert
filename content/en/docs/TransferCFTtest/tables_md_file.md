============================== table nb count(1) table converted to MD ========================================

| ID | Description |
| --- | --- |
| copilot\.http\.aliases | List of enabled alias-id |
| copilot\.http\.aliases\.\(alias-id\) alias | Name of the alias |
| copilot\.http\.aliases\.\(alias-id\)\.path | Path that replaces the alias in the URL |

============================== table nb count(2) table converted to MD ========================================

| Parameter | Description |

| --- | --- |

| copilot\.http\.onlyssl | Enter Yes to restrict the access of the Transfer CFT\{\{< TransferCFTtest/axwayvariablesComponentShortName \>\}\} user interface with https\. |

============================== table nb count(3) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Parameter</th><th>Options</th><th>Description</th></tr></thead><tbody><tr><td rowspan="3">copilot.nt.rootdrives</td><td>@REMOVABLE\_DRIVES</td><td>To view removable drives such as a USB&nbsp;key, CD, and so on.</td></tr><tr><td>@LOCAL\_DRIVES</td><td>To view hard drives.</td></tr><tr><td>@NET\_DRIVES</td><td>To view network drives.</td></tr></tbody></table>============================== table nb count(4) table converted to MD ========================================

| Parameter | Value |

| --- | --- |

| copilot\.misc\.client\_keep\_alive\_delay | Enter an integer for the delay in seconds\.
60 = default
0 = no keep-alive |
<br>
============================== table nb count(5) table converted to MD ========================================

| Parameter | Value |

| --- | --- |

| copilot\.misc\.ClientTimeout | Enter an integer for the timeout in minutes\.
30 = default
0 = no timeout |
<br>
============================== table nb count(6) table converted to MD ========================================

| Parameter | Value | Former value |

| --- | --- | --- |

| copilot\.webservices\.wsicomplience | \(bool\) No | \[WEBSERVICES\] WsiComplience |

| copilot\.webservices\.upload\_directory | \(dir\) $\(cft\.runtime\_dir\)/conf/ws\_upload | NA |

============================== table nb count(7) table stayed in HTML ========================================

<table data-cellspacing="0"><thead><tr><th>Supported format</th><th>Type</th><th>Extension</th></tr></thead><tbody><tr><td rowspan="3">Certificate</td><td>PKCS#12</td><td>p12, pfx, pkcs12</td></tr><tr><td>PEM</td><td>pem</td></tr><tr><td>DER</td><td>der</td></tr><tr><td rowspan="3">Private key</td><td>PEM</td><td>pem</td></tr><tr><td>DER</td><td>der</td></tr><tr><td>PKCS#8</td><td>key,<br>
pem</td></tr></tbody></table>============================== table nb count(8) table converted to MD ========================================

| Parameter | Value |

| --- | --- |

| copilot\.ssl\.SslCertFile | conf/pki/<my\_certificate\>\.p12 |

| copilot\.ssl\.SslCertPassword | Certificate password |

| copilot\.ssl\.SslKeyFile | Not used |

| copilot\.ssl\.SslKeyPassword | Not used |

============================== table nb count(9) table converted to MD ========================================

| Parameter | Value |

| --- | --- |

| copilot\.ssl\.SslCertFile | conf/pki /<my\_certificate\>\.der *or* \.pem |

| copilot\.ssl\.SslCertPassword | Not used |

| copilot\.ssl\.SslKeyFile | conf/pki /<my\_key\>\.der *or* \.pem |

| copilot\.ssl\.SslKeyPassword | Key password\, which is mandatory if the key file is encrypted PKCS\#8 |

============================== table nb count(10) table converted to MD ========================================

| Parameter | Value |

| --- | --- |

| copilot\.http\.onlyssl | • No: Default value\.
• Yes: Restricts access to the Transfer CFT Copilot server to HTTPS secured connections only\. |
<br>
|<span id="copilot.ssl.SslCipherSuites"></span>copilot.ssl.SslCipherSuites
| A comma separated list of cipher suites accepted by the Transfer CFT Copilot server\.
• “47, 10, 9, 2”: Default value.

List of supported cipher suites:
• 1 = RSA\_WITH\_NULL\_MD5
• 2 = RSA\_WITH\_NULL\_SHA
• 4 = RSA\_WITH\_RC4\_MD5
• 5 = RSA\_WITH\_RC4\_SHA
• 9 = RSA\_WITH\_DES\_CBC\_SHA1
• 10 = RSA\_WITH\_3DES\_EDE\_CBC\_SHA
• 47 = RSA\_WITH\_AES\_128\_CBC\_SHA
• 53 = RSA\_WITH\_AES\_256\_CBC\_SHA
• 59 = RSA\_WITH\_NULL\_SHA256
• 60 = RSA\_WITH\_AES\_128\_CBC\_SHA256
• 61 = RSA\_WITH\_AES\_256\_CBC\_SHA256 |
<br>| copilot\.ssl\.version\_min | Indicates the minimum version of SSL that the Copilot and the REST API server accept\.
• Default: tls\_1.0
• Possible values are: ssl\_3\.0 \(not recommended\)\, tls\_1\.0\, tls\_1\.0\, tls\_1\.2 |
<br>
============================== table nb count(11) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="14">SEND, CFTSEND</td><td>ACKMINDATE</td><td>integer</td><td>From this date on, the acknowledgement exec file can be launched.</td></tr><tr><td>ACKMINTIME</td><td>integer</td><td>From this time on, the acknowledgement exec file can be launched.</td></tr><tr><td>POSTMINDATE</td><td>integer</td><td>From this date on, the post processing exec file can be launched.</td></tr><tr><td>POSTMINTIME</td><td>integer</td><td>From this time on, the post processing exec file can be launched.</td></tr><tr><td>PREMINDATE</td><td>integer</td><td>From this date on, the preprocessing exec file can be launched.</td></tr><tr><td>PREMINTIME</td><td>integer</td><td>From this time on, the preprocessing exec file can be launched.</td></tr><tr><td>ACKEXEC</td><td>string</td><td>The acknowledgement exec file that will be launched after receiving an ACK or NACK.</td></tr><tr><td>ACKSTATE</td><td>REQUIRE/IGNORE</td><td>Specify if Transfer CFT{{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} should wait for an ACK/NACK to enter the X phase.</td></tr><tr><td>POSTSTATE</td><td>DISP</td><td>The transfer phase step as it enters the Y phase.</td></tr><tr><td>PREEXEC</td><td>string</td><td>The preprocessing exec file.</td></tr><tr><td>PRESTATE</td><td>DISP/HOLD</td><td>The transfer phase step as it enters the A phase.</td></tr><tr><td>EXECSUBPRE</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for preprocessing phase.</td></tr><tr><td>EXECSUB</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for post-processing phase.</td></tr><tr><td>EXECSUBA</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for acknowledgement phase.</td></tr></tbody></table>============================== table nb count(12) table stayed in HTML ========================================

<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="14">END</td><td>DIAGC</td><td>string</td><td>Specify a comment.</td></tr><tr><td>FNAME</td><td>string</td><td>Modify the FNAME.</td></tr><tr><td>NFNAME</td><td>string</td><td>Modify the NFNAME.</td></tr><tr><td>SIGFNAME</td><td>string</td><td>Modify the SIGFNAME.</td></tr><tr><td>RAPPL</td><td>string</td><td>Modify the RAPPL.</td></tr><tr><td>SAPPL</td><td>string</td><td>Modify the SAPPL.</td></tr><tr><td>RUSER</td><td>string</td><td>Modify the RUSER.</td></tr><tr><td>SUSER</td><td>string</td><td>Modify the SUSER.</td></tr><tr><td>RPASSWD</td><td>string</td><td>Modify the RPASSWD.</td></tr><tr><td>SPASSWD</td><td>string</td><td>Modify the SPASSWD.</td></tr><tr><td>ISTATE</td><td>NO/YES</td><td>Indicates:<br>
<ul><li>YES: The END command is only a checkpoint.</li><li>NO (default): This is the final end command indicating that the processing is over. Once the END&nbsp;completes, the transfer enters the next phase.</li></ul></td></tr><tr><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr><tr><td>APPSTATE</td><td>string</td><td>Specify an application state for the processing<br>
script that will help the script to restart at the right step if the<br>
<br>
script is relaunched.</td></tr></tbody></table>============================== table nb count(13) table converted to MD ========================================

| Parameter | Value | Description |

| --- | --- | --- |

| ACKMINDATE | integer | From this date on\, the acknowledgement exec file can be launched\. |

| ACKMINTIME | integer | From this time on\, the acknowledgement exec file can be launched\. |

| POSTMINDATE | integer | From this date on\, the post processing exec file can be launched\. |

| POSTMINTIME | integer | From this time on\, the post processing exec file can be launched\. |

| PREMINDATE | integer | From this date on\, the preprocessing exec file can be launched\. |

| PREMINTIME | integer | From this time on\, the preprocessing exec file can be launched\. |

| ACKEXEC | string | The acknowledgement exec file that will be launched after receiving an ACK or NACK\. |

| ACKSTATE | REQUIRE/IGNORE | Specify if Transfer CFT\{\{< TransferCFTtest/axwayvariablesComponentShortName \>\}\} should wait for an ACK/NACK to enter the X phase\. |

| POSTSTATE | DISP | The transfer phase step as it enters the Y phase\. |

| PREEXEC | string | The preprocessing exec file\. |

| PRESTATE | DISP/HOLD | The transfer phase step as it enters the A phase\. |

| EXECSUBPRE | LIST/SUBF/FILE | Group of files: execution policy for preprocessing phase\. |

| EXECSUB | LIST/SUBF/FILE | Group of files: execution policy for post-processing phase\. |

| EXECSUBA | LIST/SUBF/FILE | Group of files: execution policy for acknowledgement phase\. |

============================== table nb count(14) table converted to MD ========================================

| Parameter | Value | Description |

| --- | --- | --- |

| DIAGC | string | Specify a comment\. |

| FNAME | string | Modify the FNAME\. |

| NFNAME | string | Modify the NFNAME\. |

| SIGFNAME | string | Modify the SIGFNAME\. |

| RAPPL | string | Modify the RAPPL\. |

| SAPPL | string | Modify the SAPPL\. |

| RUSER | string | Modify the RUSER\. |

| SUSER | string | Modify the SUSER\. |

| RPASSWD | string | Modify the RPASSWD\. |

| SPASSWD | string | Modify the SPASSWD\. |

| ISTATE | NO/YES | Indicates:
• YES: The END command is only a checkpoint.
• NO \(default\): This is the final end command indicating that the processing is over\. Once the END completes\, the transfer enters the next phase\. |
<br>| PHASE | char | The transfer phase at which the command is applied\. |

| PHASE STEP | char | The phase step at which the command is applied\. |

| APPSTATE | string | Specify an application state for the processing script that will help the script to restart at the right step if the script is relaunched\. |

============================== table nb count(15) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| Installation architecture | @default = single | Defines single or cluster mode installation\.
Values: single\, first\_host\, additional\_host | UCONF: N/A |
<br>| installdir | | Transfer CFT installation directory\. | UCONF: cft\.install\_dir |

| accept\_general\_conditions | NO | Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation\. | |

============================== table nb count(16) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| runtimeDir | \./runtime | Transfer CFT runtime directory\.
Specify the directory where you want to install the Transfer CFT runtime directory.
By default\, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory\. Use the default directory\, or specify a new directory\. A runtime directory will be created if it does not already exist\. | UCONF: cft\.runtime\_dir |
<br>| Full\_Hostname | @automatic | Host Address of the local server: FQDN \(Fully Qualified Domain Name\) or IP Address\. See **Note**\* | UCONF: cft\.full\_hostname |

| multinode\_hostname | @automatic | When not defined\, this field is filled with the hostname of the machine where you are installing Transfer CFT\{\{< TransferCFTtest/suitevariablesTransferCFTName \>\}\}\, whether it is the first host or an additional host\.
If the hostname contains a "\." period\, the value used consists of the name of the host preceding the first period\. For example\, "myhost\.fqdn\.net" would be shortened to "myhost"\. | UCONF: cft\.multi\_node\.hostnames |
<br>| multinode\_host\_address | @automatic | If you do not specify a value\, the machine's FQDN address is used\.
Note that if there is an error in the machine's configuration\, the value taken could be incorrect\. Be sure to check that you can ping the address\, and that it is the value for the cluster network\. | UCONF: cft\.multi\_node\.hostnames\.\<hostname\>\.host |
<br>| Instance\_ID | @default | The maximum length is 24\. | UCONF: cft\.instance\_id |

| Instance\_Group | | Transfer CFT instance group\.
The maximum length is 1000\. | UCONF: cft\.instance\_group |
<br>
============================== table nb count(17) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| CryptoKey\_Password | @mandatory | Seed password to generate the encryption key\.
The password must contains at least 8 characters, contain upper and
lower case characters as well as numeric and special characters \(\*$\!?\+-@\)\. | UCONF: N/A |
<br>| CryptoKey\_Key\_File | @default = $CFTDIRRUNTIME/data/crypto/crypkey | Location that stores the generated key file\. | UCONF: crypto\.key\_fname |

| CryptoKey\_Salt\_File | @default = $CFTDIRRUNTIME/data/crypto/crypsalt | Location that stores the generated salt file\. | UCONF: crypto\.salt\_fname |

============================== table nb count(18) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| Key | | Enter the license key for the Transfer CFT product\.
The key is stored in the $CFTDIRRUNTIME/conf/cft.key.
*Without the key you can install, but not start the product.* | |
<br>| Catalog\_File\_Size | @default= 10000 | Sets the default catalog size\. | UCONF: cft\.cftcat\.default\_size |

| Communication\_File\_Size | @default = 1000 | Sets the default communication file size\. | UCONF: cft\.cftcom\.default\_size |

| PESIT\_Port | @default = 1761 | The port number of the PeSiT protocol\.
| UCONF: samples\.pesitany\_sap\.value |
<br>| PESIT\_SSL\_Port | @default = 1762 | The port number of the PeSIT protocol using SSL\. | UCONF: samples\.pesitssl\_sap\.value |

| COMS\_Port | @default = 1765 | The port number of the COMS synchronous communication media\.
| UCONF: samples\.coms\_port\.value |
<br>| Copilot\_Port | @default = 1766 | Sets the port number for the Transfer CFT Copilot server that listens for
incoming unsecured and secured (SSL) connections.
The same port number is used for the Graphical User Interface and Web Services
with or without SSL\. | UCONF: copilot\.general\.serverport |
<br>| Copilot\_OnlySSL | @default = Yes | Copilot only allows SSL connection\.
This value applies to the old Transfer CFT UI, Webservices and JPI.
If you set this to Yes\, it disables the use of the HTTP server when an SSL context is defined \(HTTPS only\)\. | UCONF: copilot\.http\.onlyssl |
<br>| Copilot\_SSL\_Port | @default = 1767 | Sets the port number for the Transfer CFT Copilot server that listens for incoming secured \(SSL with mutual authentication\) connections\. Only used by the Governance\. | UCONF: copilot\.general\.ssl\_serverport |

| UI\_DefaultUser\_Username
UI\_DefaultUser\_Password | | *UNIX systems only*
The default Transfer CFT UI user/password\. | UCONF: N/A |
<br>
| RESTAPI\_Enable

| @default = Yes | Setting this to Yes activates the Transfer CFT REST API Server\. | UCONF: copilot\.restapi\.enable |
<br>| RESTAPI\_Port | 1768 | The port number used to connect to the REST API server\. | UCONF: copilot\.restapi\.serverport |

| RESTAPI\_Certificate\_Path
RESTAPI\_Cert\_Pass | | Sets the certificate and the corresponding password to be used by the Transfer
CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).
• When REST API is enabled, you must complete these fields.
• When Copilot\_OnlySSL is activated, you must complete these fields.
When using Central Governance\, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance\. | UCONF: copilot\.ssl\.SslCertFile |
<br>
============================== table nb count(19) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| Multinode\_Enable | @default = No | Enable the multi-node architecture\.
To use a multi-node architecture\, you must define the multi-node option in the initialize\.properties file\. | UCONF: cft\.multi\_node\.enable |
<br>| Multinode\_Number | @default = 2 | Enter the number of nodes\. | UCONF: cft\.multi\_node\.nodes |

| LoadBalancer\_Host | | Specify the host address of the load balancer\.
When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment\, you require a load balancer to connect to the Transfer CFT Copilot server\. | UCONF: cft\.multi\_node\.load\_balancer\.host |
<br>| LoadBalancer\_Port | | Specify the load balancer port\, which is redirected to the Central Governance dedicated port of the Transfer CFT UI Server\. When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment\, you require a load balancer to connect to the Transfer CFT Copilot server\. | UCONF: cft\.multi\_node\.load\_balancer\.port |

============================== table nb count(20) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| CG\_Enable | @default = No | Enter Yes to enable Central Governance connectivity\. | UCONF: cg\.enable |

| CG\_Host | | The Central Governance host address\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** | UCONF: cg\.host |
<br>| CG\_Port | @default = 12553 | The Central Governance port\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** | UCONF: cg\.port |
<br>| CG\_Mutual\_Port | @default = 12554 | The Central Governance port for Mutual Authentication\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** | UCONF: cg\.mutual\_auth\_port |
<br>| CG\_SharedSecret | | Specify the shared secret\, which is needed to register with the Central Governance server\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** | UCONF: cg\.shared\_secret |
<br>| CG\_ConfigurationPolicy | | Specify Central Governance configuration policy to apply to the Transfer CFT instance\. | UCONF: cg\.configuration\_policy |

| CG\_Certificate\_Path | @default = $CFTDIRRUNTIME/conf/pki/passportCA\.pem | Specify the Custom Certificate to authenticate Central Governance\. | UCONF: N/A |

============================== table nb count(21) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| Sentinel\_Enable | @default = No | Set to Yes to enable Sentinel\.
**Do not enable this if you have enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}.** | UCONF: sentinel\.xfb\.enable |
<br>| Sentinel\_Host | | Enter the Sentinel host address\. | UCONF: sentinel\.trkipaddr |

| Sentinel\_Port | @default= 1305 | Enter the Sentinel port\.
You do not need to define this field if you are registering Transfer CFT with Central Governance\{\{< TransferCFTtest/suitevariablesCentralGovernanceName \>\}\}\. | UCONF: sentinel\.trkipport |
<br>| Sentinel\_Log\_Filter | @default = EWF | Sentinel Log Filter: \(I\)nformation\, \(W\)arning\, \(E\)rror\, \(F\)atal Authorized characters are only I\, W\, E\, F
You can only use each letter once\. | UCONF: sentinel\.xfb\.log |
<br>| Sentinel\_Transfer\_Filter | @default = ALL | Sentinel Transfer Filter
Possible values are: ALL\, SUMMARY\, NO\, ERROR | UCONF: sentinel\.xfb\.transfer |
<br>| Sentinel\_Use\_SSL | @default = Yes | Enables an SSL connection with Sentinel\. | UCONF: sentinel\.xfb\.use\_ssl |

| Sentinel\_Certificate\_Path | @default=$CFTDIRRUNTIME/conf/pki/passportCA\.pem | Sentinel root certificate\. | UCONF: N/A |

============================== table nb count(22) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| CFT\_StartAsService | @default = No | Start Transfer CFT Server using service mode\. | UCONF: cft\.nt\.service\_mode |

| CFT\_ServiceName
CFT\_ServiceDisplayName | @default= Transfer\_CFT
@default= AMPLIFY Transfer CFT | Transfer CFT Server Service name\.
You cannot have spaces in the CFT\_ServiceName\. | UCONF: cft\.nt\.service\_name |
<br>| CFT\_ServiceSpecificUser | @default= No | Use a specific account to start the Transfer CFT Server Service\. | UCONF: N/A |

| CFT\_ServiceUsername
CFT\_ServicePassword | | The Username \(Domain\User\) of the user who will start the Transfer CFT Server\. | UCONF: N/A |
<br>| CFT\_StartType | @default= auto | Transfer CFT Server service start type: auto\, manual\, disabled | UCONF: N/A |

| CFTUI\_StartAsService | @default= No | Start Transfer CFT UI Server using service mode\. | UCONF: copilot\.nt\.service\_mode |

| CFTUI\_ServiceName CFTUI\_ServiceDisplayName | @default= Transfer\_CFT\_UI
@default= AMPLIFY Transfer CFT UI | Transfer CFT UI Server Service name\.
You cannot have spaces in the CFTUI\_ServiceName\. | vcopilot\.nt\.service\_name |
<br>| CFTUI\_ServiceSpecificUser | @default= No | Use a specific account to start the Transfer CFT UI Server Service\. | UCONF: N/A |

| CFTUI\_ServiceUsername CFTUI\_ServicePassword | | The Username \(Domain\User\) of the user who will start the Transfer CFT UI Server\. | UCONF: N/A |

| CFTUI\_StartType | @default= auto | The Transfer CFT UI Server service start type: auto\, manual\, disabled | UCONF: N/A |

============================== table nb count(23) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| JAVA\_BINARY\_PATH | | Java binary path used to start Transfer CFT jar files\. | UCONF: cft\.jre\.java\_binary\_path |

| IntegrityControl\_Enable | @default = Yes | Activate integrity control for the Transfer CFT databases\. | |

============================== table nb count(24) table converted to MD ========================================

| Parameter | Automatic or default | Description | UCONF |

| --- | --- | --- | --- |

| Enable SAML | @default = No | | UCONF: am\.type= 'saml' |

============================== table nb count(25) table stayed in HTML ========================================

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<table data-cellspacing="0"><thead><tr><th>Parameter</th><th>Automatic or default</th><th>Description</th><th>UCONF&nbsp;</th></tr></thead><tbody><tr><td colspan="3">****Silent installation****</td><td>&nbsp;</td></tr><tr><td>Installation architecture</td><td>@default = single</td><td>Defines single or cluster mode installation.<br>
<br>
Values: single, first\_host, additional\_host</td><td>N/A</td></tr><tr><td>installdir</td><td>&nbsp;</td><td>Transfer CFT installation directory.</td><td>cft.install\_dir</td></tr><tr><td>accept\_general\_conditions</td><td>NO</td><td>Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation.</td><td>&nbsp;</td></tr><tr><td colspan="3">****Basic installation****</td><td>&nbsp;</td></tr><tr><td>runtimeDir</td><td>./runtime</td><td>Transfer CFT runtime directory.<br>
<br>
Specify the directory where you want to install the Transfer<br>
<br>
CFT runtime directory.<br>
<br>
<br>
By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or<br>
<br>
specify a new directory. A runtime directory will be created if it does not already exist.</td><td>cft.runtime\_dir</td></tr><tr><td>Full\_Hostname</td><td>@automatic</td><td>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See **Note**\*</td><td>cft.full\_hostname</td></tr><tr><td>multinode\_hostname</td><td>@automatic</td><td>When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{&lt; TransferCFTtest/suitevariablesTransferCFTName &gt;}}, whether it is the first host or an additional host.<br>
<br>
If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost".</td><td>cft.multi\_node.hostnames</td></tr><tr><td>multinode\_host\_address</td><td>@automatic</td><td>If you do not specify a value, the machine's FQDN address is used.<br>
<br>
Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network.</td><td>cft.multi\_node.hostnames.\<hostname>.host</hostname></td></tr><tr><td>Instance\_ID</td><td>@default<br>
&nbsp;</td><td>The maximum length is 24.</td><td>cft.instance\_id</td></tr><tr><td>Instance\_Group</td><td>&nbsp;</td><td>Transfer CFT instance group.<br>
<br>
The maximum length is 1000.</td><td>cft.instance\_group</td></tr><tr><td colspan="3">****Security configuration****</td><td>&nbsp;</td></tr><tr><td>CryptoKey\_Password</td><td>@mandatory</td><td>Seed password to generate the encryption key.<br>
<br>
The password must contains at least 8 characters, contain upper and<br>
<br>
lower case characters as well as numeric and special characters (\*$!?+-@).</td><td>N/A</td></tr><tr><td>CryptoKey\_Key\_File</td><td>@default = $CFTDIRRUNTIME/data/crypto/crypkey</td><td>Location that stores the generated key file.</td><td>crypto.key\_fname &nbsp;&nbsp;&nbsp;&nbsp;</td></tr><tr><td>CryptoKey\_Salt\_File</td><td>@default = $CFTDIRRUNTIME/data/crypto/crypsalt</td><td>Location that stores the generated salt file.</td><td>crypto.salt\_fname</td></tr><tr><td colspan="3">****Runtime configuration****</td><td>&nbsp;</td></tr><tr><td>Key</td><td>&nbsp;</td><td>Enter the license key for the Transfer CFT product.<br>
<br>
The key is stored in the $CFTDIRRUNTIME/conf/cft.key.<br>
<br>
*Without the key you can install, but not start the product.*</td><td>&nbsp;</td></tr><tr><td>Catalog\_File\_Size</td><td>@default= 10000</td><td>Sets the default catalog size.</td><td>cft.cftcat.default\_size</td></tr><tr><td>Communication\_File\_Size</td><td>@default = 1000</td><td>Sets the default communication file size.</td><td>cft.cftcom.default\_size</td></tr><tr><td>PESIT\_Port</td><td>@default = 1761</td><td>The port number of the PeSiT protocol.<br>
<br>
&nbsp;</td><td>samples.pesitany\_sap.value</td></tr><tr><td>PESIT\_SSL\_Port</td><td>@default = 1762</td><td>The port number of the PeSIT protocol using SSL.</td><td>samples.pesitssl\_sap.value</td></tr><tr><td>COMS\_Port</td><td>@default = 1765</td><td>The port number of the COMS synchronous communication media.<br>
<br>
&nbsp;</td><td>samples.coms\_port.value</td></tr><tr><td>Copilot\_Port</td><td>@default = 1766</td><td>Sets the port number for the Transfer CFT Copilot server that listens for<br>
<br>
incoming unsecured and secured (SSL) connections.<br>
<br>
The same port number is used for the Graphical User Interface and Web Services<br>
<br>
with or without SSL.</td><td>copilot.general.serverport</td></tr><tr><td>Copilot\_OnlySSL</td><td>@default = Yes</td><td>Copilot only allows SSL connection.<br>
<br>
This value applies to the old Transfer CFT UI, Webservices and JPI.<br>
<br>
If you set this to Yes, it disables the use of the HTTP server when an SSL context is<br>
<br>
defined (HTTPS only).</td><td>copilot.http.onlyssl</td></tr><tr><td>Copilot\_SSL\_Port</td><td>@default = 1767</td><td>Sets the port number for the Transfer CFT Copilot server that listens for<br>
incoming secured (SSL with mutual authentication) connections.<br>
<br>
Only used by the Governance.</td><td>copilot.general.ssl\_serverport</td></tr><tr><td>UI\_DefaultUser\_Username<br>
<br>
UI\_DefaultUser\_Password</td><td></td><td>*UNIX systems only*<br>
<br>
The default Transfer CFT UI user/password.</td><td>N/A</td></tr><tr><td>RESTAPI\_Enable<br>
<br>
&nbsp;<br>
<br>
&nbsp;</td><td>@default = Yes</td><td>Setting this to Yes activates the Transfer CFT REST API Server.</td><td>copilot.restapi.enable</td></tr><tr><td>RESTAPI\_Port</td><td>1768</td><td>The port number used to connect to the REST API server.</td><td>copilot.restapi.serverport</td></tr><tr><td>RESTAPI\_Certificate\_Path<br>
<br>
RESTAPI\_Cert\_Pass</td><td>&nbsp;</td><td>Sets the certificate and the corresponding password to be used by the Transfer<br>
<br>
CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).<br>
<ul><li>When REST API is enabled, you must complete these fields.</li><li>When Copilot\_OnlySSL is activated, you must complete these fields.</li></ul>When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance.<br>
</td><td>copilot.ssl.SslCertFile</td></tr><tr><td colspan="4">****Multi-node and Cluster****</td></tr><tr><td>Multinode\_Enable</td><td>@default = No</td><td>Enable the multi-node architecture.<br>
<br>
To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.</td><td>cft.multi\_node.enable</td></tr><tr><td>Multinode\_Number</td><td>@default = 2</td><td>Enter the number of nodes.</td><td>cft.multi\_node.nodes</td></tr><tr><td>LoadBalancer\_Host</td><td>&nbsp;</td><td>Specify the host address of the load balancer.<br>
<br>
When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load<br>
<br>
balancer to connect to the Transfer CFT Copilot server.</td><td>cft.multi\_node.load\_balancer.host</td></tr><tr><td>LoadBalancer\_Port</td><td>&nbsp;</td><td>Specify the load balancer port, which is redirected to the<br>
Central Governance dedicated port of the Transfer CFT UI Server.<br>
<br>
When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load<br>
<br>
balancer to connect to the Transfer CFT Copilot server.</td><td>cft.multi\_node.load\_balancer.port</td></tr><tr><td colspan="4">****Central Governance****</td></tr><tr><td>CG\_Enable</td><td>@default = No</td><td>Enter Yes to enable Central Governance connectivity.</td><td>cg.enable</td></tr><tr><td>CG\_Host</td><td>&nbsp;</td><td>The Central Governance host address.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.host</td></tr><tr><td>CG\_Port</td><td>@default = 12553</td><td>The Central Governance port.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.port</td></tr><tr><td>CG\_Mutual\_Port</td><td>@default = 12554</td><td>The Central Governance port for Mutual Authentication.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.mutual\_auth\_port</td></tr><tr><td>CG\_SharedSecret</td><td>&nbsp;</td><td>Specify the shared secret, which is needed to register with the Central Governance server.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.shared\_secret</td></tr><tr><td>CG\_ConfigurationPolicy</td><td>&nbsp;</td><td>Specify Central Governance configuration policy to apply to the Transfer CFT<br>
instance.</td><td>cg.configuration\_policy</td></tr><tr><td>CG\_Certificate\_Path</td><td>@default = $CFTDIRRUNTIME/conf/pki/passportCA.pem</td><td>Specify the Custom Certificate to authenticate Central Governance.</td><td>N/A</td></tr><tr><td colspan="4">****Sentinel Connector****</td></tr><tr><td>Sentinel\_Enable</td><td>@default = No</td><td>Set to Yes to enable Sentinel.<br>
<br>
**Do not enable this if you have enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}.**</td><td>sentinel.xfb.enable</td></tr><tr><td>Sentinel\_Host</td><td>&nbsp;</td><td>Enter the Sentinel host address.</td><td>sentinel.trkipaddr</td></tr><tr><td>Sentinel\_Port</td><td>@default= 1305</td><td>Enter the Sentinel port.<br>
<br>
You do not need to define this field if you are registering Transfer CFT&nbsp;with Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}.</td><td>sentinel.trkipport</td></tr><tr><td>Sentinel\_Log\_Filter</td><td>@default = EWF</td><td>Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal<br>
<br>
Authorized characters are only I, W, E, F<br>
<br>
<br>
You can only use each letter once.</td><td>sentinel.xfb.log</td></tr><tr><td>Sentinel\_Transfer\_Filter</td><td>@default = ALL</td><td>Sentinel Transfer Filter<br>
<br>
Possible values are: ALL, SUMMARY, NO, ERROR</td><td>sentinel.xfb.transfer</td></tr><tr><td>Sentinel\_Use\_SSL&nbsp;</td><td>@default = Yes</td><td>Enables an SSL connection with Sentinel.</td><td>sentinel.xfb.use\_ssl</td></tr><tr><td>Sentinel\_Certificate\_Path</td><td>@default=$CFTDIRRUNTIME/conf/pki/passportCA.pem</td><td>Sentinel root certificate.</td><td>N/A</td></tr><tr><td colspan="4">**Windows Services**</td></tr><tr><td>CFT\_StartAsService</td><td>@default = No</td><td>Start Transfer CFT Server using service mode.</td><td>cft.nt.service\_mode</td></tr><tr><td>CFT\_ServiceName<br>
<br>
CFT\_ServiceDisplayName</td><td>@default= Transfer\_CFT<br>
<br>
@default= AMPLIFY Transfer CFT</td><td>Transfer CFT Server Service name.<br>
<br>
You cannot have spaces in the CFT\_ServiceName.</td><td>&nbsp;cft.nt.service\_name</td></tr><tr><td>CFT\_ServiceSpecificUser</td><td>@default= No</td><td>Use a specific account to start the Transfer CFT Server Service.</td><td>N/A</td></tr><tr><td>CFT\_ServiceUsername<br>
<br>
CFT\_ServicePassword</td><td>&nbsp;</td><td>The Username (Domain\User) of the user who will start the Transfer CFT Server.</td><td>N/A</td></tr><tr><td>CFT\_StartType</td><td>@default= auto</td><td>Transfer CFT Server service start type: auto, manual, disabled</td><td>N/A</td></tr><tr><td>CFTUI\_StartAsService</td><td>@default= No</td><td>Start Transfer CFT UI Server using service mode.</td><td>copilot.nt.service\_mode</td></tr><tr><td>CFTUI\_ServiceName<br>
CFTUI\_ServiceDisplayName</td><td>@default= Transfer\_CFT\_UI<br>
<br>
@default= AMPLIFY Transfer CFT UI</td><td>Transfer CFT UI Server Service name.<br>
<br>
You cannot have spaces in the CFTUI\_ServiceName.</td><td>copilot.nt.service\_name</td></tr><tr><td>CFTUI\_ServiceSpecificUser</td><td>@default= No</td><td>Use a specific account to start the Transfer CFT UI Server Service.</td><td>N/A</td></tr><tr><td>CFTUI\_ServiceUsername<br>
CFTUI\_ServicePassword</td><td>&nbsp;</td><td>The Username (Domain\User) of the user who will start the Transfer CFT UI Server.</td><td>N/A</td></tr><tr><td>CFTUI\_StartType</td><td>@default= auto</td><td>The Transfer CFT UI Server service start type: auto, manual, disabled</td><td>N/A</td></tr><tr><td colspan="4">****Miscellaneous****</td></tr><tr><td>JAVA\_BINARY\_PATH</td><td>&nbsp;</td><td>Java binary path used to start Transfer CFT jar files.</td><td>cft.jre.java\_binary\_path</td></tr><tr><td>IntegrityControl\_Enable</td><td>@default = Yes</td><td>Activate integrity control for the Transfer CFT databases.</td><td>&nbsp;</td></tr><tr><td colspan="4">**SAML**</td></tr><tr><td>Enable SAML</td><td>@default = No</td><td>&nbsp;</td><td>am.type= 'saml'</td></tr></tbody></table>============================== table nb count(26) table stayed in HTML ========================================

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<table data-cellspacing="0"><thead><tr><th>Parameter</th><th>Automatic or default</th><th>Description</th><th>UCONF&nbsp;</th></tr></thead><tbody><tr><td colspan="3">****Silent installation****</td><td>&nbsp;</td></tr><tr><td>Installation architecture</td><td>@default = single</td><td>Defines single or cluster mode installation.<br>
<br>
Values: single, first\_host, additional\_host</td><td>N/A</td></tr><tr><td>installdir</td><td>&nbsp;</td><td>Transfer CFT installation directory.</td><td>cft.install\_dir</td></tr><tr><td>accept\_general\_conditions</td><td>NO</td><td>Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation.</td><td>&nbsp;</td></tr><tr><td colspan="3">****Basic installation****</td><td>&nbsp;</td></tr><tr><td>runtimeDir</td><td>./runtime</td><td>Transfer CFT runtime directory.<br>
<br>
Specify the directory where you want to install the Transfer<br>
<br>
CFT runtime directory.<br>
<br>
<br>
By default, the runtime directory is installed in a sub-directory of the Transfer CFT installation directory. Use the default directory, or<br>
<br>
specify a new directory. A runtime directory will be created if it does not already exist.</td><td>cft.runtime\_dir</td></tr><tr><td>Full\_Hostname</td><td>@automatic</td><td>Host Address of the local server: FQDN (Fully Qualified Domain Name) or IP Address. See **Note**\*</td><td>cft.full\_hostname</td></tr><tr><td>multinode\_hostname</td><td>@automatic</td><td>When not defined, this field is filled with the hostname of the machine where you are installing Transfer CFT{{&lt; TransferCFTtest/suitevariablesTransferCFTName &gt;}}, whether it is the first host or an additional host.<br>
<br>
If the hostname contains a "." period, the value used consists of the name of the host preceding the first period. For example, "myhost.fqdn.net" would be shortened to "myhost".</td><td>cft.multi\_node.hostnames</td></tr><tr><td>multinode\_host\_address</td><td>@automatic</td><td>If you do not specify a value, the machine's FQDN address is used.<br>
<br>
Note that if there is an error in the machine's configuration, the value taken could be incorrect. Be sure to check that you can ping the address, and that it is the value for the cluster network.</td><td>cft.multi\_node.hostnames.\<hostname>.host</hostname></td></tr><tr><td>Instance\_ID</td><td>@default<br>
&nbsp;</td><td>The maximum length is 24.</td><td>cft.instance\_id</td></tr><tr><td>Instance\_Group</td><td>&nbsp;</td><td>Transfer CFT instance group.<br>
<br>
The maximum length is 1000.</td><td>cft.instance\_group</td></tr><tr><td colspan="3">****Security configuration****</td><td>&nbsp;</td></tr><tr><td>CryptoKey\_Password</td><td>@mandatory</td><td>Seed password to generate the encryption key.<br>
<br>
The password must contains at least 8 characters, contain upper and<br>
<br>
lower case characters as well as numeric and special characters (\*$!?+-@).</td><td>N/A</td></tr><tr><td>CryptoKey\_Key\_File</td><td>@default = $CFTDIRRUNTIME/data/crypto/crypkey</td><td>Location that stores the generated key file.</td><td>crypto.key\_fname &nbsp;&nbsp;&nbsp;&nbsp;</td></tr><tr><td>CryptoKey\_Salt\_File</td><td>@default = $CFTDIRRUNTIME/data/crypto/crypsalt</td><td>Location that stores the generated salt file.</td><td>crypto.salt\_fname</td></tr><tr><td colspan="3">****Runtime configuration****</td><td>&nbsp;</td></tr><tr><td>Key</td><td>&nbsp;</td><td>Enter the license key for the Transfer CFT product.<br>
<br>
The key is stored in the $CFTDIRRUNTIME/conf/cft.key.<br>
<br>
*Without the key you can install, but not start the product.*</td><td>&nbsp;</td></tr><tr><td>Catalog\_File\_Size</td><td>@default= 10000</td><td>Sets the default catalog size.</td><td>cft.cftcat.default\_size</td></tr><tr><td>Communication\_File\_Size</td><td>@default = 1000</td><td>Sets the default communication file size.</td><td>cft.cftcom.default\_size</td></tr><tr><td>PESIT\_Port</td><td>@default = 1761</td><td>The port number of the PeSiT protocol.<br>
<br>
&nbsp;</td><td>samples.pesitany\_sap.value</td></tr><tr><td>PESIT\_SSL\_Port</td><td>@default = 1762</td><td>The port number of the PeSIT protocol using SSL.</td><td>samples.pesitssl\_sap.value</td></tr><tr><td>COMS\_Port</td><td>@default = 1765</td><td>The port number of the COMS synchronous communication media.<br>
<br>
&nbsp;</td><td>samples.coms\_port.value</td></tr><tr><td>Copilot\_Port</td><td>@default = 1766</td><td>Sets the port number for the Transfer CFT Copilot server that listens for<br>
<br>
incoming unsecured and secured (SSL) connections.<br>
<br>
The same port number is used for the Graphical User Interface and Web Services<br>
<br>
with or without SSL.</td><td>copilot.general.serverport</td></tr><tr><td>Copilot\_OnlySSL</td><td>@default = Yes</td><td>Copilot only allows SSL connection.<br>
<br>
This value applies to the old Transfer CFT UI, Webservices and JPI.<br>
<br>
If you set this to Yes, it disables the use of the HTTP server when an SSL context is<br>
<br>
defined (HTTPS only).</td><td>copilot.http.onlyssl</td></tr><tr><td>Copilot\_SSL\_Port</td><td>@default = 1767</td><td>Sets the port number for the Transfer CFT Copilot server that listens for<br>
incoming secured (SSL with mutual authentication) connections.<br>
<br>
Only used by the Governance.</td><td>copilot.general.ssl\_serverport</td></tr><tr><td>UI\_DefaultUser\_Username<br>
<br>
UI\_DefaultUser\_Password</td><td></td><td>*UNIX systems only*<br>
<br>
The default Transfer CFT UI user/password.</td><td>N/A</td></tr><tr><td>RESTAPI\_Enable<br>
<br>
&nbsp;<br>
<br>
&nbsp;</td><td>@default = Yes</td><td>Setting this to Yes activates the Transfer CFT REST API Server.</td><td>copilot.restapi.enable</td></tr><tr><td>RESTAPI\_Port</td><td>1768</td><td>The port number used to connect to the REST API server.</td><td>copilot.restapi.serverport</td></tr><tr><td>RESTAPI\_Certificate\_Path<br>
<br>
RESTAPI\_Cert\_Pass</td><td>&nbsp;</td><td>Sets the certificate and the corresponding password to be used by the Transfer<br>
<br>
CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).<br>
<ul><li>When REST API is enabled, you must complete these fields.</li><li>When Copilot\_OnlySSL is activated, you must complete these fields.</li></ul>When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre-define this value if you are going to register Transfer CFT with Central Governance.<br>
</td><td>copilot.ssl.SslCertFile</td></tr><tr><td colspan="4">****Multi-node and Cluster****</td></tr><tr><td>Multinode\_Enable</td><td>@default = No</td><td>Enable the multi-node architecture.<br>
<br>
To use a multi-node architecture, you must define the multi-node option in the initialize.properties file.</td><td>cft.multi\_node.enable</td></tr><tr><td>Multinode\_Number</td><td>@default = 2</td><td>Enter the number of nodes.</td><td>cft.multi\_node.nodes</td></tr><tr><td>LoadBalancer\_Host</td><td>&nbsp;</td><td>Specify the host address of the load balancer.<br>
<br>
When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load<br>
<br>
balancer to connect to the Transfer CFT Copilot server.</td><td>cft.multi\_node.load\_balancer.host</td></tr><tr><td>LoadBalancer\_Port</td><td>&nbsp;</td><td>Specify the load balancer port, which is redirected to the<br>
Central Governance dedicated port of the Transfer CFT UI Server.<br>
<br>
When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment, you require a load<br>
<br>
balancer to connect to the Transfer CFT Copilot server.</td><td>cft.multi\_node.load\_balancer.port</td></tr><tr><td colspan="4">****Central Governance****</td></tr><tr><td>CG\_Enable</td><td>@default = No</td><td>Enter Yes to enable Central Governance connectivity.</td><td>cg.enable</td></tr><tr><td>CG\_Host</td><td>&nbsp;</td><td>The Central Governance host address.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.host</td></tr><tr><td>CG\_Port</td><td>@default = 12553</td><td>The Central Governance port.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.port</td></tr><tr><td>CG\_Mutual\_Port</td><td>@default = 12554</td><td>The Central Governance port for Mutual Authentication.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.mutual\_auth\_port</td></tr><tr><td>CG\_SharedSecret</td><td>&nbsp;</td><td>Specify the shared secret, which is needed to register with the Central Governance server.<br>
<br>
**If you enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}, you must complete this field.**</td><td>cg.shared\_secret</td></tr><tr><td>CG\_ConfigurationPolicy</td><td>&nbsp;</td><td>Specify Central Governance configuration policy to apply to the Transfer CFT<br>
instance.</td><td>cg.configuration\_policy</td></tr><tr><td>CG\_Certificate\_Path</td><td>@default = $CFTDIRRUNTIME/conf/pki/passportCA.pem</td><td>Specify the Custom Certificate to authenticate Central Governance.</td><td>N/A</td></tr><tr><td colspan="4">****Sentinel Connector****</td></tr><tr><td>Sentinel\_Enable</td><td>@default = No</td><td>Set to Yes to enable Sentinel.<br>
<br>
**Do not enable this if you have enabled Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}.**</td><td>sentinel.xfb.enable</td></tr><tr><td>Sentinel\_Host</td><td>&nbsp;</td><td>Enter the Sentinel host address.</td><td>sentinel.trkipaddr</td></tr><tr><td>Sentinel\_Port</td><td>@default= 1305</td><td>Enter the Sentinel port.<br>
<br>
You do not need to define this field if you are registering Transfer CFT&nbsp;with Central Governance{{&lt; TransferCFTtest/suitevariablesCentralGovernanceName &gt;}}.</td><td>sentinel.trkipport</td></tr><tr><td>Sentinel\_Log\_Filter</td><td>@default = EWF</td><td>Sentinel Log Filter: (I)nformation, (W)arning, (E)rror, (F)atal<br>
<br>
Authorized characters are only I, W, E, F<br>
<br>
<br>
You can only use each letter once.</td><td>sentinel.xfb.log</td></tr><tr><td>Sentinel\_Transfer\_Filter</td><td>@default = ALL</td><td>Sentinel Transfer Filter<br>
<br>
Possible values are: ALL, SUMMARY, NO, ERROR</td><td>sentinel.xfb.transfer</td></tr><tr><td>Sentinel\_Use\_SSL&nbsp;</td><td>@default = Yes</td><td>Enables an SSL connection with Sentinel.</td><td>sentinel.xfb.use\_ssl</td></tr><tr><td>Sentinel\_Certificate\_Path</td><td>@default=$CFTDIRRUNTIME/conf/pki/passportCA.pem</td><td>Sentinel root certificate.</td><td>N/A</td></tr><tr><td colspan="4">**Windows Services**</td></tr><tr><td>CFT\_StartAsService</td><td>@default = No</td><td>Start Transfer CFT Server using service mode.</td><td>cft.nt.service\_mode</td></tr><tr><td>CFT\_ServiceName<br>
<br>
CFT\_ServiceDisplayName</td><td>@default= Transfer\_CFT<br>
<br>
@default= AMPLIFY Transfer CFT</td><td>Transfer CFT Server Service name.<br>
<br>
You cannot have spaces in the CFT\_ServiceName.</td><td>&nbsp;cft.nt.service\_name</td></tr><tr><td>CFT\_ServiceSpecificUser</td><td>@default= No</td><td>Use a specific account to start the Transfer CFT Server Service.</td><td>N/A</td></tr><tr><td>CFT\_ServiceUsername<br>
<br>
CFT\_ServicePassword</td><td>&nbsp;</td><td>The Username (Domain\User) of the user who will start the Transfer CFT Server.</td><td>N/A</td></tr><tr><td>CFT\_StartType</td><td>@default= auto</td><td>Transfer CFT Server service start type: auto, manual, disabled</td><td>N/A</td></tr><tr><td>CFTUI\_StartAsService</td><td>@default= No</td><td>Start Transfer CFT UI Server using service mode.</td><td>copilot.nt.service\_mode</td></tr><tr><td>CFTUI\_ServiceName<br>
CFTUI\_ServiceDisplayName</td><td>@default= Transfer\_CFT\_UI<br>
<br>
@default= AMPLIFY Transfer CFT UI</td><td>Transfer CFT UI Server Service name.<br>
<br>
You cannot have spaces in the CFTUI\_ServiceName.</td><td>copilot.nt.service\_name</td></tr><tr><td>CFTUI\_ServiceSpecificUser</td><td>@default= No</td><td>Use a specific account to start the Transfer CFT UI Server Service.</td><td>N/A</td></tr><tr><td>CFTUI\_ServiceUsername<br>
CFTUI\_ServicePassword</td><td>&nbsp;</td><td>The Username (Domain\User) of the user who will start the Transfer CFT UI Server.</td><td>N/A</td></tr><tr><td>CFTUI\_StartType</td><td>@default= auto</td><td>The Transfer CFT UI Server service start type: auto, manual, disabled</td><td>N/A</td></tr><tr><td colspan="4">****Miscellaneous****</td></tr><tr><td>JAVA\_BINARY\_PATH</td><td>&nbsp;</td><td>Java binary path used to start Transfer CFT jar files.</td><td>cft.jre.java\_binary\_path</td></tr><tr><td>IntegrityControl\_Enable</td><td>@default = Yes</td><td>Activate integrity control for the Transfer CFT databases.</td><td>&nbsp;</td></tr><tr><td colspan="4">**SAML**</td></tr><tr><td>Enable SAML</td><td>@default = No</td><td>&nbsp;</td><td>am.type= 'saml'</td></tr></tbody></table>============================== table nb count(27) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="14">SEND, CFTSEND</td><td>ACKMINDATE</td><td>integer</td><td>From this date on, the acknowledgement exec file can be launched.</td></tr><tr><td>ACKMINTIME</td><td>integer</td><td>From this time on, the acknowledgement exec file can be launched.</td></tr><tr><td>POSTMINDATE</td><td>integer</td><td>From this date on, the post processing exec file can be launched.</td></tr><tr><td>POSTMINTIME</td><td>integer</td><td>From this time on, the post processing exec file can be launched.</td></tr><tr><td>PREMINDATE</td><td>integer</td><td>From this date on, the preprocessing exec file can be launched.</td></tr><tr><td>PREMINTIME</td><td>integer</td><td>From this time on, the preprocessing exec file can be launched.</td></tr><tr><td>ACKEXEC</td><td>string</td><td>The acknowledgement exec file that will be launched after receiving an ACK or NACK.</td></tr><tr><td>ACKSTATE</td><td>REQUIRE/IGNORE</td><td>Specify if Transfer CFT{{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} should wait for an ACK/NACK to enter the X phase.</td></tr><tr><td>POSTSTATE</td><td>DISP</td><td>The transfer phase step as it enters the Y phase.</td></tr><tr><td>PREEXEC</td><td>string</td><td>The preprocessing exec file.</td></tr><tr><td>PRESTATE</td><td>DISP/HOLD</td><td>The transfer phase step as it enters the A phase.</td></tr><tr><td>EXECSUBPRE</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for preprocessing phase.</td></tr><tr><td>EXECSUB</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for post-processing phase.</td></tr><tr><td>EXECSUBA</td><td>LIST/SUBF/FILE</td><td>Group of files: execution policy for acknowledgement phase.</td></tr></tbody></table>============================== table nb count(28) table stayed in HTML ========================================

<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="14">END</td><td>DIAGC</td><td>string</td><td>Specify a comment.</td></tr><tr><td>FNAME</td><td>string</td><td>Modify the FNAME.</td></tr><tr><td>NFNAME</td><td>string</td><td>Modify the NFNAME.</td></tr><tr><td>SIGFNAME</td><td>string</td><td>Modify the SIGFNAME.</td></tr><tr><td>RAPPL</td><td>string</td><td>Modify the RAPPL.</td></tr><tr><td>SAPPL</td><td>string</td><td>Modify the SAPPL.</td></tr><tr><td>RUSER</td><td>string</td><td>Modify the RUSER.</td></tr><tr><td>SUSER</td><td>string</td><td>Modify the SUSER.</td></tr><tr><td>RPASSWD</td><td>string</td><td>Modify the RPASSWD.</td></tr><tr><td>SPASSWD</td><td>string</td><td>Modify the SPASSWD.</td></tr><tr><td>ISTATE</td><td>NO/YES</td><td>Indicates:<br>
<ul><li>YES: The END command is only a checkpoint.</li><li>NO (default): This is the final end command indicating that the processing is over. Once the END&nbsp;completes, the transfer enters the next phase.</li></ul></td></tr><tr><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr><tr><td>APPSTATE</td><td>string</td><td>Specify an application state for the processing<br>
script that will help the script to restart at the right step if the<br>
<br>
script is relaunched.</td></tr></tbody></table>============================== table nb count(29) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="4">KEEP</td><td>DIAGP</td><td>string</td><td>Specify a customized error that will be set for DIAGP in the catalog.</td></tr><tr><td>DIAGC</td><td>string</td><td>Specify a customized error that will be set for DIAGC in the catalog.</td></tr><tr><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr></tbody></table>============================== table nb count(30) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="4">HALT</td><td>DIAGP</td><td>string</td><td>Specify a customized error that will be set for DIAGP in the catalog.</td></tr><tr><td>DIAGC</td><td>string</td><td>Specify a customized error that will be set for DIAGC in the catalog.</td></tr><tr><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr></tbody></table>============================== table nb count(31) table stayed in HTML ========================================

<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="3">SUBMIT</td><td>APPSTATE</td><td>string</td><td>Specify an application state for the<br>
processing script that will allow a SUBMIT to occur at the correct script step.</td></tr><tr><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr></tbody></table>============================== table nb count(32) table stayed in HTML ========================================
<table data-cellspacing="0"><thead><tr><th>Command</th><th>Parameter</th><th>Value</th><th>Description</th></tr></thead><tbody><tr><td rowspan="3">START</td><td>PHASE</td><td>char</td><td>The transfer phase at which the command is applied.</td></tr><tr><td>MAXDURATION</td><td>integer</td><td>Restart a transfer that reached its maxduration, time in minutes {<u>0</u>...32767}.</td></tr><tr><td>PHASE&nbsp;STEP</td><td>char</td><td>The phase step at which the command is applied.</td></tr></tbody></table>