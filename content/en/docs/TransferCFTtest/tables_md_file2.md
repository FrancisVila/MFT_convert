\| ID \| Description \|
\| \-\-\- \| \-\-\- \|
\| copilot\.http\.aliases \| List of enabled alias\-id \|
\| copilot\.http\.aliases\.\(alias\-id\) alias \| Name of the alias \|
\| copilot\.http\.aliases\.\(alias\-id\)\.path \| Path that replaces the alias in the URL \|
\| Parameter \| Description \|

\| \-\-\- \| \-\-\- \|

\| copilot\.http\.onlyssl \| Enter Yes to restrict the access of the Transfer CFT\{\{< TransferCFTtest/axwayvariablesComponentShortName \>\}\} user interface with https\. \|

\| Parameter \| Value \|

\| \-\-\- \| \-\-\- \|

\| copilot\.misc\.client\_keep\_alive\_delay \| Enter an integer for the delay in seconds\.
60 = default
0 = no keep\-alive \|
<br>\| Parameter \| Value \|

\| \-\-\- \| \-\-\- \|

\| copilot\.misc\.ClientTimeout \| Enter an integer for the timeout in minutes\.
30 = default
0 = no timeout \|
<br>\| Parameter \| Value \| Former value \|

\| \-\-\- \| \-\-\- \| \-\-\- \|

\| copilot\.webservices\.wsicomplience \| \(bool\) No \| \[WEBSERVICES\] WsiComplience \|

\| copilot\.webservices\.upload\_directory \| \(dir\) $\(cft\.runtime\_dir\)/conf/ws\_upload \| NA \|

\| Parameter \| Value \|

\| \-\-\- \| \-\-\- \|

\| copilot\.ssl\.SslCertFile \| conf/pki/<my\_certificate\>\.p12 \|

\| copilot\.ssl\.SslCertPassword \| Certificate password \|

\| copilot\.ssl\.SslKeyFile \| Not used \|

\| copilot\.ssl\.SslKeyPassword \| Not used \|

\| Parameter \| Value \|

\| \-\-\- \| \-\-\- \|

\| copilot\.ssl\.SslCertFile \| conf/pki /<my\_certificate\>\.der *or* \.pem \|

\| copilot\.ssl\.SslCertPassword \| Not used \|

\| copilot\.ssl\.SslKeyFile \| conf/pki /<my\_key\>\.der *or* \.pem \|

\| copilot\.ssl\.SslKeyPassword \| Key password\, which is mandatory if the key file is encrypted PKCS\#8 \|

\| Parameter \| Value \|

\| \-\-\- \| \-\-\- \|

\| copilot\.http\.onlyssl \| • No: Default value\.
• Yes: Restricts access to the Transfer CFT Copilot server to HTTPS secured connections only\. \|
<br>
\|<span id="copilot.ssl.SslCipherSuites"></span>copilot.ssl.SslCipherSuites
\| A comma separated list of cipher suites accepted by the Transfer CFT Copilot server\.
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
• 61 = RSA\_WITH\_AES\_256\_CBC\_SHA256 \|
<br>\| copilot\.ssl\.version\_min \| Indicates the minimum version of SSL that the Copilot and the REST API server accept\.
• Default: tls\_1.0
• Possible values are: ssl\_3\.0 \(not recommended\)\, tls\_1\.0\, tls\_1\.0\, tls\_1\.2 \|
<br>\| Parameter \| Value \| Description \|

\| \-\-\- \| \-\-\- \| \-\-\- \|

\| ACKMINDATE \| integer \| From this date on\, the acknowledgement exec file can be launched\. \|

\| ACKMINTIME \| integer \| From this time on\, the acknowledgement exec file can be launched\. \|

\| POSTMINDATE \| integer \| From this date on\, the post processing exec file can be launched\. \|

\| POSTMINTIME \| integer \| From this time on\, the post processing exec file can be launched\. \|

\| PREMINDATE \| integer \| From this date on\, the preprocessing exec file can be launched\. \|

\| PREMINTIME \| integer \| From this time on\, the preprocessing exec file can be launched\. \|

\| ACKEXEC \| string \| The acknowledgement exec file that will be launched after receiving an ACK or NACK\. \|

\| ACKSTATE \| REQUIRE/IGNORE \| Specify if Transfer CFT\{\{< TransferCFTtest/axwayvariablesComponentShortName \>\}\} should wait for an ACK/NACK to enter the X phase\. \|

\| POSTSTATE \| DISP \| The transfer phase step as it enters the Y phase\. \|

\| PREEXEC \| string \| The preprocessing exec file\. \|

\| PRESTATE \| DISP/HOLD \| The transfer phase step as it enters the A phase\. \|

\| EXECSUBPRE \| LIST/SUBF/FILE \| Group of files: execution policy for preprocessing phase\. \|

\| EXECSUB \| LIST/SUBF/FILE \| Group of files: execution policy for post\-processing phase\. \|

\| EXECSUBA \| LIST/SUBF/FILE \| Group of files: execution policy for acknowledgement phase\. \|

\| Parameter \| Value \| Description \|

\| \-\-\- \| \-\-\- \| \-\-\- \|

\| DIAGC \| string \| Specify a comment\. \|

\| FNAME \| string \| Modify the FNAME\. \|

\| NFNAME \| string \| Modify the NFNAME\. \|

\| SIGFNAME \| string \| Modify the SIGFNAME\. \|

\| RAPPL \| string \| Modify the RAPPL\. \|

\| SAPPL \| string \| Modify the SAPPL\. \|

\| RUSER \| string \| Modify the RUSER\. \|

\| SUSER \| string \| Modify the SUSER\. \|

\| RPASSWD \| string \| Modify the RPASSWD\. \|

\| SPASSWD \| string \| Modify the SPASSWD\. \|

\| ISTATE \| NO/YES \| Indicates:
• YES: The END command is only a checkpoint.
• NO \(default\): This is the final end command indicating that the processing is over\. Once the END completes\, the transfer enters the next phase\. \|
<br>\| PHASE \| char \| The transfer phase at which the command is applied\. \|

\| PHASE STEP \| char \| The phase step at which the command is applied\. \|

\| APPSTATE \| string \| Specify an application state for the processing script that will help the script to restart at the right step if the script is relaunched\. \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| Installation architecture \| @default = single \| Defines single or cluster mode installation\.
Values: single\, first\_host\, additional\_host \| UCONF: N/A \|
<br>\| installdir \| \| Transfer CFT installation directory\. \| UCONF: cft\.install\_dir \|

\| accept\_general\_conditions \| NO \| Set to YES to accept the General Terms and Conditions in the product <a href="https://www.axway.com/en/legal/contract-documents">license</a> when performing a silent installation\. \| \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| runtimeDir \| \./runtime \| Transfer CFT runtime directory\.
Specify the directory where you want to install the Transfer CFT runtime directory.
By default\, the runtime directory is installed in a sub\-directory of the Transfer CFT installation directory\. Use the default directory\, or specify a new directory\. A runtime directory will be created if it does not already exist\. \| UCONF: cft\.runtime\_dir \|
<br>\| Full\_Hostname \| @automatic \| Host Address of the local server: FQDN \(Fully Qualified Domain Name\) or IP Address\. See **Note**\* \| UCONF: cft\.full\_hostname \|

\| multinode\_hostname \| @automatic \| When not defined\, this field is filled with the hostname of the machine where you are installing Transfer CFT\{\{< TransferCFTtest/suitevariablesTransferCFTName \>\}\}\, whether it is the first host or an additional host\.
If the hostname contains a "\." period\, the value used consists of the name of the host preceding the first period\. For example\, "myhost\.fqdn\.net" would be shortened to "myhost"\. \| UCONF: cft\.multi\_node\.hostnames \|
<br>\| multinode\_host\_address \| @automatic \| If you do not specify a value\, the machine's FQDN address is used\.
Note that if there is an error in the machine's configuration\, the value taken could be incorrect\. Be sure to check that you can ping the address\, and that it is the value for the cluster network\. \| UCONF: cft\.multi\_node\.hostnames\.\<hostname\>\.host \|
<br>\| Instance\_ID \| @default \| The maximum length is 24\. \| UCONF: cft\.instance\_id \|

\| Instance\_Group \| \| Transfer CFT instance group\.
The maximum length is 1000\. \| UCONF: cft\.instance\_group \|
<br>\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| CryptoKey\_Password \| @mandatory \| Seed password to generate the encryption key\.
The password must contains at least 8 characters, contain upper and
lower case characters as well as numeric and special characters \(\*$\!?\+\-@\)\. \| UCONF: N/A \|
<br>\| CryptoKey\_Key\_File \| @default = $CFTDIRRUNTIME/data/crypto/crypkey \| Location that stores the generated key file\. \| UCONF: crypto\.key\_fname \|

\| CryptoKey\_Salt\_File \| @default = $CFTDIRRUNTIME/data/crypto/crypsalt \| Location that stores the generated salt file\. \| UCONF: crypto\.salt\_fname \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| Key \| \| Enter the license key for the Transfer CFT product\.
The key is stored in the $CFTDIRRUNTIME/conf/cft.key.
*Without the key you can install, but not start the product.* \| \|
<br>\| Catalog\_File\_Size \| @default= 10000 \| Sets the default catalog size\. \| UCONF: cft\.cftcat\.default\_size \|

\| Communication\_File\_Size \| @default = 1000 \| Sets the default communication file size\. \| UCONF: cft\.cftcom\.default\_size \|

\| PESIT\_Port \| @default = 1761 \| The port number of the PeSiT protocol\.
\| UCONF: samples\.pesitany\_sap\.value \|
<br>\| PESIT\_SSL\_Port \| @default = 1762 \| The port number of the PeSIT protocol using SSL\. \| UCONF: samples\.pesitssl\_sap\.value \|

\| COMS\_Port \| @default = 1765 \| The port number of the COMS synchronous communication media\.
\| UCONF: samples\.coms\_port\.value \|
<br>\| Copilot\_Port \| @default = 1766 \| Sets the port number for the Transfer CFT Copilot server that listens for
incoming unsecured and secured (SSL) connections.
The same port number is used for the Graphical User Interface and Web Services
with or without SSL\. \| UCONF: copilot\.general\.serverport \|
<br>\| Copilot\_OnlySSL \| @default = Yes \| Copilot only allows SSL connection\.
This value applies to the old Transfer CFT UI, Webservices and JPI.
If you set this to Yes\, it disables the use of the HTTP server when an SSL context is defined \(HTTPS only\)\. \| UCONF: copilot\.http\.onlyssl \|
<br>\| Copilot\_SSL\_Port \| @default = 1767 \| Sets the port number for the Transfer CFT Copilot server that listens for incoming secured \(SSL with mutual authentication\) connections\. Only used by the Governance\. \| UCONF: copilot\.general\.ssl\_serverport \|

\| UI\_DefaultUser\_Username
UI\_DefaultUser\_Password \| \| *UNIX systems only*
The default Transfer CFT UI user/password\. \| UCONF: N/A \|
<br>
\| RESTAPI\_Enable

\| @default = Yes \| Setting this to Yes activates the Transfer CFT REST API Server\. \| UCONF: copilot\.restapi\.enable \|
<br>\| RESTAPI\_Port \| 1768 \| The port number used to connect to the REST API server\. \| UCONF: copilot\.restapi\.serverport \|

\| RESTAPI\_Certificate\_Path
RESTAPI\_Cert\_Pass \| \| Sets the certificate and the corresponding password to be used by the Transfer
CFT REST API Server and for HTTPS connections with Copilot (the old Transfer CFT UI, Web services, and JPI).
• When REST API is enabled, you must complete these fields.
• When Copilot\_OnlySSL is activated, you must complete these fields.
When using Central Governance\, the REST API server automatically uses the SSL business certificate generated during the registration; there is no need to pre\-define this value if you are going to register Transfer CFT with Central Governance\. \| UCONF: copilot\.ssl\.SslCertFile \|
<br>\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| Multinode\_Enable \| @default = No \| Enable the multi\-node architecture\.
To use a multi\-node architecture\, you must define the multi\-node option in the initialize\.properties file\. \| UCONF: cft\.multi\_node\.enable \|
<br>\| Multinode\_Number \| @default = 2 \| Enter the number of nodes\. \| UCONF: cft\.multi\_node\.nodes \|

\| LoadBalancer\_Host \| \| Specify the host address of the load balancer\.
When using an ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment\, you require a load balancer to connect to the Transfer CFT Copilot server\. \| UCONF: cft\.multi\_node\.load\_balancer\.host \|
<br>\| LoadBalancer\_Port \| \| Specify the load balancer port\, which is redirected to the Central Governance dedicated port of the Transfer CFT UI Server\. When using ACTIVE/ACTIVE or ACTIVE/PASSIVE deployment\, you require a load balancer to connect to the Transfer CFT Copilot server\. \| UCONF: cft\.multi\_node\.load\_balancer\.port \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| CG\_Enable \| @default = No \| Enter Yes to enable Central Governance connectivity\. \| UCONF: cg\.enable \|

\| CG\_Host \| \| The Central Governance host address\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** \| UCONF: cg\.host \|
<br>\| CG\_Port \| @default = 12553 \| The Central Governance port\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** \| UCONF: cg\.port \|
<br>\| CG\_Mutual\_Port \| @default = 12554 \| The Central Governance port for Mutual Authentication\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** \| UCONF: cg\.mutual\_auth\_port \|
<br>\| CG\_SharedSecret \| \| Specify the shared secret\, which is needed to register with the Central Governance server\.
**If you enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}, you must complete this field.** \| UCONF: cg\.shared\_secret \|
<br>\| CG\_ConfigurationPolicy \| \| Specify Central Governance configuration policy to apply to the Transfer CFT instance\. \| UCONF: cg\.configuration\_policy \|

\| CG\_Certificate\_Path \| @default = $CFTDIRRUNTIME/conf/pki/passportCA\.pem \| Specify the Custom Certificate to authenticate Central Governance\. \| UCONF: N/A \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| Sentinel\_Enable \| @default = No \| Set to Yes to enable Sentinel\.
**Do not enable this if you have enabled Central Governance{{< TransferCFTtest/suitevariablesCentralGovernanceName >}}.** \| UCONF: sentinel\.xfb\.enable \|
<br>\| Sentinel\_Host \| \| Enter the Sentinel host address\. \| UCONF: sentinel\.trkipaddr \|

\| Sentinel\_Port \| @default= 1305 \| Enter the Sentinel port\.
You do not need to define this field if you are registering Transfer CFT with Central Governance\{\{< TransferCFTtest/suitevariablesCentralGovernanceName \>\}\}\. \| UCONF: sentinel\.trkipport \|
<br>\| Sentinel\_Log\_Filter \| @default = EWF \| Sentinel Log Filter: \(I\)nformation\, \(W\)arning\, \(E\)rror\, \(F\)atal Authorized characters are only I\, W\, E\, F
You can only use each letter once\. \| UCONF: sentinel\.xfb\.log \|
<br>\| Sentinel\_Transfer\_Filter \| @default = ALL \| Sentinel Transfer Filter
Possible values are: ALL\, SUMMARY\, NO\, ERROR \| UCONF: sentinel\.xfb\.transfer \|
<br>\| Sentinel\_Use\_SSL \| @default = Yes \| Enables an SSL connection with Sentinel\. \| UCONF: sentinel\.xfb\.use\_ssl \|

\| Sentinel\_Certificate\_Path \| @default=$CFTDIRRUNTIME/conf/pki/passportCA\.pem \| Sentinel root certificate\. \| UCONF: N/A \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| CFT\_StartAsService \| @default = No \| Start Transfer CFT Server using service mode\. \| UCONF: cft\.nt\.service\_mode \|

\| CFT\_ServiceName
CFT\_ServiceDisplayName \| @default= Transfer\_CFT
@default= AMPLIFY Transfer CFT \| Transfer CFT Server Service name\.
You cannot have spaces in the CFT\_ServiceName\. \| UCONF: cft\.nt\.service\_name \|
<br>\| CFT\_ServiceSpecificUser \| @default= No \| Use a specific account to start the Transfer CFT Server Service\. \| UCONF: N/A \|

\| CFT\_ServiceUsername
CFT\_ServicePassword \| \| The Username \(Domain\User\) of the user who will start the Transfer CFT Server\. \| UCONF: N/A \|
<br>\| CFT\_StartType \| @default= auto \| Transfer CFT Server service start type: auto\, manual\, disabled \| UCONF: N/A \|

\| CFTUI\_StartAsService \| @default= No \| Start Transfer CFT UI Server using service mode\. \| UCONF: copilot\.nt\.service\_mode \|

\| CFTUI\_ServiceName CFTUI\_ServiceDisplayName \| @default= Transfer\_CFT\_UI
@default= AMPLIFY Transfer CFT UI \| Transfer CFT UI Server Service name\.
You cannot have spaces in the CFTUI\_ServiceName\. \| vcopilot\.nt\.service\_name \|
<br>\| CFTUI\_ServiceSpecificUser \| @default= No \| Use a specific account to start the Transfer CFT UI Server Service\. \| UCONF: N/A \|

\| CFTUI\_ServiceUsername CFTUI\_ServicePassword \| \| The Username \(Domain\User\) of the user who will start the Transfer CFT UI Server\. \| UCONF: N/A \|

\| CFTUI\_StartType \| @default= auto \| The Transfer CFT UI Server service start type: auto\, manual\, disabled \| UCONF: N/A \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| JAVA\_BINARY\_PATH \| \| Java binary path used to start Transfer CFT jar files\. \| UCONF: cft\.jre\.java\_binary\_path \|

\| IntegrityControl\_Enable \| @default = Yes \| Activate integrity control for the Transfer CFT databases\. \| \|

\| Parameter \| Automatic or default \| Description \| UCONF \|

\| \-\-\- \| \-\-\- \| \-\-\- \| \-\-\- \|

\| Enable SAML \| @default = No \| \| UCONF: am\.type= 'saml' \|