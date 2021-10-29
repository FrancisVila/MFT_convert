{
    "title": "Manage the Transfer CFT Copilot server",
    "linkTitle": "Manage the Transfer CFT UI server",
    "weight": "200"
}The Transfer CFT Copilot server provides a number of functions that support the following services: the Transfer CFT UI, REST API services, web services, multi-host/multi-node architectures, and Central Governance.

This page describes how to start/stop and check the status of the Transfer CFT Copilot server.

## <span id="Start_/_stop_Copilot"></span>Start and stop the Copilot server

To start the Copilot server, run the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>copstart         </td>
      </tr>
   </tbody>
</table>

To stop the Copilot server, run the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>copstop         </td>
      </tr>
   </tbody>
</table>

To stop the Copilot server and force connections to close, run:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>copstop -f         </td>
      </tr>
   </tbody>
</table>

To kill all Copilot server processes, run:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>copstop -kill         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">For details on starting in your specific operating system, refer to the corresponding Transfer CFT <span>3.9</span> <em>Installation Guide</em>.         </td>
      </tr>
   </tbody>
</table>

### <span id="Check__status"></span>Check the Copilot server status

To check the Copilot status, enter:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><span>copstatus</span>         </td>
      </tr>
   </tbody>
</table>

The copstatus return code is 0 when Copilot is running, and 1 when Copilot is stopped.

Additional copstatus commands include:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>copstatus [-p] [-v] [-h|--help]
</span></p>
            <p><span> -p print copsmng pid if copilot is started
</span></p>
            <p><span> -v print status message
</span></p>
            <p><span> -</span><span>h|--help copstatus help
</span></p>         </td>
      </tr>
   </tbody>
</table>

## Windows menus

You can also use the Windows Start menu to start Axway software. From the Start menu, select Programs (or All Programs), Axway Software and then the product.

For example, to start the Copilot server click Start &gt; All Programs &gt; Axway Software &gt; Transfer CFT &gt; Start Transfer CFT UI Server.

## Operating system specific tasks

### z/OS

#### Start

COPRUN is an example of a JCL statement that starts the Transfer CFT Copilot server. The server can be started as a Start Task. The Transfer CFT Copilot server STEPLIB, and then JOBLIB should be defined as an APF. If it is not defined as an APF, no RACF check can be performed. This results in no log-on check being available and all requests are done with the user associated with the server JOB.

When the copilot.misc.CreateProcessAsUser variable is set, STEPLIB or JOBLIB can be non-APF. Only a Central Governance/PassPort user can sign on to Copilot user interface.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When the ‘cft.mvs.copilot.check_apf’ uconf variable is set to ‘Yes’, CFTCOPL must be APF authorized to start.         </td>
      </tr>
   </tbody>
</table>

LOG message: +CFTI42E Copilot must be APF-authorized.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">CFTCOPL must be APF authorized to start if the UCONF <span>cft.mvs.copilot.check_apf </span>variable is set to <span>Yes</span>. Otherwise, the Transfer CFT log displays <span>CFTI42E Copilot must be APF-authorized</span>.         </td>
      </tr>
   </tbody>
</table>

#### Stop

COPSTOP is an example of the JCL stop statement for the Transfer CFT UI server. You can also stop the Transfer CFT UI server using the operator command pause (/P jobname) for the server-associated task.

### IBM i

#### Start

Menu

1.  Access the *Transfer CFT* Main Menu.  
    In the Main Menu enter the command cft and press Enter to open the Transfer CFT menu.
2.  Enter **1** to access **Common CFT commands**.
3.  Select option 1 Start Copilot. The *Copilot server* menu is displayed.  

Command

Execute: COPSTART

#### Stop

Menu

1.  Access the *Transfer CFT* Main Menu.  
    In the Main Menu enter the command cft and press Enter to open the Transfer CFT menu.
2.  Enter **1** to access **Common CFT commands**.
3.  Select option 2 Stop Copilot.  
    Only the server waiting for a connection is stopped. Other servers that users have logged onto are shut down when the user logs off, or after a network timeout.

Command

Execute: COPSTOP

## <span id="Copilot"></span>Transfer CFT Copilot server configuration

### General Copilot server parameters

The following table lists the UCONF identifiers
and the default values for the Transfer CFT UI (Copilot) server.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>ID</th>
         <th>Default</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td>            <p>copilot.general.serverport</p>         </td>
         <td>            <p>1766 </p>         </td>
         <td>Copilot server listening port.         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td>            <p>copilot.general.serverhost  </p>         </td>
         <td>            <p>0.0.0.0 </p>         </td>
         <td>TCP Transfer CFT Copilot server address, where 0.0.0.0 indicates that you want the Transfer CFT UI to listen on all network interfaces if your machine has more than one.         </td>
      </tr>
   </tbody>
</table>

UNIX

Refer to the [UCONF parameters](uconf/uconf_directory) table for information on copilot.\*.unix parameters.

#### Alias management

You can access customized file system directories via the Transfer CFT user interface HTTP server using aliases.

To add a new alias, access the Unified Configuration and configure the following:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>ID</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>copilot.http.aliases         </td>
         <td>List of enabled alias-id         </td>
      </tr>
      <tr class="even">
         <td>copilot.http.aliases.(alias-id) alias         </td>
         <td>Name of the alias         </td>
      </tr>
      <tr class="odd">
         <td>copilot.http.aliases.(alias-id).path         </td>
         <td>Path that replaces the alias in the URL         </td>
      </tr>
   </tbody>
</table>

#### View available drives

To view available drives from the Edit a file icon in the graphical user interface, define the following:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Options</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td rowspan="3">copilot.nt.rootdrives         </td>
         <td>@REMOVABLE_DRIVES         </td>
         <td>To view removable drives such as a USB key, CD, and so on.         </td>
      </tr>
      <tr class="even">
         <td>@LOCAL_DRIVES         </td>
         <td>To view hard drives.         </td>
      </tr>
      <tr class="odd">
         <td>@NET_DRIVES         </td>
         <td>To view network drives.         </td>
      </tr>
   </tbody>
</table>

#### Client keep-alive

Use this parameter to define the keep-alive interval in seconds for a client session. By default, this occurs every 60 seconds.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Value</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>copilot.misc.client_keep_alive_delay         </td>
         <td>            <p>Enter an integer for the delay in seconds.</p>
            <p>60 = default</p>
            <p>0 = no keep-alive</p>         </td>
      </tr>
   </tbody>
</table>

#### Client timeout

Use this parameter to define the client timeout in minutes. By default, the timeout is 30 minutes.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Value</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>copilot.misc.ClientTimeout         </td>
         <td>            <p>Enter an integer for the timeout in minutes.</p>
            <ul>
               <li>30 = default timeout of 30 minutes               </li>
               <li>0 = 60 minute timeout for the Transfer CFT UI (token)               </li>
               <li>0 = no timeout for the deprecated Copilot UI               </li>
            </ul>         </td>
      </tr>
   </tbody>
</table>

#### Web services

Use these parameter to define the Transfer CFT Web Services. See also [Setting up Web Services](../app_integration_intro/using_apis/about_web_services).

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Value</th>
         <th>Former value</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>copilot.webservices.wsicomplience         </td>
         <td>(bool) No         </td>
         <td>[WEBSERVICES] WsiComplience         </td>
      </tr>
      <tr class="even">
         <td>copilot.webservices.upload_directory         </td>
         <td>(dir) $(cft.runtime_dir)/conf/ws_upload         </td>
         <td>NA         </td>
      </tr>
   </tbody>
</table>

#### REST API server

Use these parameter to configure the REST API server. See also [Transfer CFT REST API concepts](../app_integration_intro/using_apis/api_intro).

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Type</th>
         <th>Default</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>copilot.restapi.enable         </td>
         <td>bool         </td>
         <td>No         </td>
         <td>            <p>Enable/disable the REST API service:</p>
            <ul>
               <li>Yes: enable               </li>
               <li>No: disable               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>copilot.restapi.serverport         </td>
         <td>int         </td>
         <td>1768         </td>
         <td>            <p>REST API server port.</p>         </td>
      </tr>
      <tr class="odd">
         <td>copilot.restapi.authentication_method         </td>
         <td>string         </td>
         <td>            <p>system (Windows)</p>
            <p>xfbadm (UNIX)</p>         </td>
         <td>            <p>Defines authentication method.</p>
            <p> </p>
            <p>See also, <a href="../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr utilitiy.</a></p>         </td>
      </tr>
      <tr class="even">
         <td>copilot.restapi.nb_workers         </td>
         <td>int         </td>
         <td>4         </td>
         <td>Number of activated workers that process the REST API requests.         </td>
      </tr>
      <tr class="odd">
         <td>copilot.restapi.maxclient         </td>
         <td>int         </td>
         <td>256         </td>
         <td>Number of client connections handled per REST worker.         </td>
      </tr>
      <tr class="even">
         <td>copilot.restapi.coms_id         </td>
         <td>string         </td>
         <td>coms         </td>
         <td>            <p>The TCPIP CFTCOM object identifier used by the REST API server to communicate with the Transfer CFT server.</p>
            <p>Leave empty to use
the COM file instead.</p>         </td>
      </tr>
      <tr class="odd">
         <td>copilot.restapi.catalog.retry_delay         </td>
         <td>int         </td>
         <td>5         </td>
         <td>            <ul>
               <li>The delay between retries
in seconds. The Transfer CFT Copilot server checks the request status in catalog every retry_delay seconds.               </li>
               <li>The delay between retries
in seconds. The Transfer CFT Copilot server checks the request status in catalog every retry_delay seconds.               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>copilot.restapi.catalog.retry_timeout         </td>
         <td>int         </td>
         <td>30         </td>
         <td>            <p>The default value of the <a href="../app_integration_intro/using_apis/api_intro/api_commands">apiTimeout</a> parameter as defined in the request URL.</p>
            <p>Available exclusively for POST requests.</p>         </td>
      </tr>
   </tbody>
</table>

## <span id="Configur"></span>Configure Copilot with SSL security

This section describes how to install the certificates that are required to enable:

-   Transfer CFT UI (web browser-based)
-   REST API  

The basic steps are:

-   Install a certificate on the server side
-   Install a certificate on the client side
-   Connect to Copilot using an SSL connection

### Operating system specific limitations

-   For z/OS, certificates can be USS or sequential files.
-   For IBM i (OS/400), certificates must be native files if you have enabled the REST API interface. If only Copilot is enabled, IFS files are supported (as in the previous version).

### <span id="Install"></span>Install a certificate on the server side

#### When using Central Governance

The Transfer CFT Copilot server uses the certificate that was created by Central Governance during the product registration. This certificate is stored in Transfer CFT PKI database and the certificate id is the value of the UCONF cft.instance\_id parameter. This means that there is no action required to install a certificate.

However, to override the default behavior use the procedure described below in *When using Transfer CFT without governance*.

#### When using Transfer CFT without governance

The following tables describe the UCONF parameters that determine the certificates used by the Transfer CFT UI server to authenticate itself.

You can use the following certificate and private key formats, where the format of the certificate may differ from that of the key.

The certificate type is dictated by the file name extension (.p12, .pkcs12, .der, .pem, for example my\_certificate.pem).

*For native files in a z/OS or IBM i environment*, if the format cannot be determined (the file suffix used as the extension), Transfer CFT derives the value from these uconf settings:

-   copilot.ssl.sslkeyfile=&lt;not set> and copilot.ssl.sslcertpassword=&lt;set>, then the format is PKCS12
-   copilot.ssl.sslkeyfile= &lt;set> and copilot.ssl.sslcertpassword=&lt;not set>, then the format is PEM

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Supported format</th>
         <th>Type</th>
         <th>Extension</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td rowspan="3">Certificate         </td>
         <td>PKCS#12         </td>
         <td>p12, pfx, pkcs12         </td>
      </tr>
      <tr class="even">
         <td>PEM         </td>
         <td>pem         </td>
      </tr>
      <tr class="odd">
         <td>DER         </td>
         <td>der         </td>
      </tr>
      <tr class="even">
         <td rowspan="3">Private key         </td>
         <td>PEM         </td>
         <td>pem         </td>
      </tr>
      <tr class="odd">
         <td>DER         </td>
         <td>der         </td>
      </tr>
      <tr class="even">
         <td>PKCS#8         </td>
         <td>key,
pem         </td>
      </tr>
   </tbody>
</table>

How to define a PKCS#12 certificate

This example uses a single PKCS#12 certificate where you only require the file name and password.

<table data-align="center" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Parameter</p></th>
         <th>            <p>Value</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>copilot.ssl.SslCertFile</p>         </td>
         <td>            <p>conf/pki/&lt;my_certificate&gt;.p12</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>copilot.ssl.SslCertPassword</p>         </td>
         <td>            <p>Certificate password</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>copilot.ssl.SslKeyFile</p>         </td>
         <td>            <p>Not used</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>copilot.ssl.SslKeyPassword</p>         </td>
         <td>            <p>Not used</p>         </td>
      </tr>
   </tbody>
</table>

How to define a DER or PEM certificate

This example uses a DER(or PEM) certificate with the private key in a separate DER file, where you define the key as well as the certificate.

<table data-align="center" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Parameter</p></th>
         <th>            <p>Value</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>copilot.ssl.SslCertFile</p>         </td>
         <td>            <p>conf/pki /&lt;my_certificate&gt;.der <em>or</em> .pem</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>copilot.ssl.SslCertPassword</p>         </td>
         <td>            <p>Not used</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>copilot.ssl.SslKeyFile</p>         </td>
         <td>            <p>conf/pki /&lt;my_key&gt;.der <em>or</em> .pem</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>copilot.ssl.SslKeyPassword</p>         </td>
         <td>            <p>Key password, which is mandatory if the key file is encrypted PKCS#8</p>         </td>
      </tr>
   </tbody>
</table>

#### Additional HTTPS parameters

There are two additional UCONF parameters to use for HTTPS connections:

<table data-align="center" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Parameter</p></th>
         <th>            <p>Value</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>copilot.http.onlyssl</p>         </td>
         <td>            <ul>
               <li>No: Default value.               </li>
               <li>Yes: Restricts access to the Transfer CFT Copilot server to HTTPS secured connections only.               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>            <p><span id="copilot.ssl.SslCipherSuites"></span>copilot.ssl.SslCipherSuites</p>
            <p> </p>         </td>
         <td>            <p>A comma separated list of cipher suites accepted by the Transfer CFT Copilot server, for example: “47, 10, 9, 2”.</p>
            <p>See the <a href="../transport_security_start_here/manage_cipher_suites">Supported cipher suites</a> for details.</p>         </td>
      </tr>
   </tbody>
</table>

### Install a certificate on the client side

Windows

On Windows, there are two ways to install a certificate on the client side - using a Windows certificate or the Java keystore.

UNIX

On Linux, using the Java keystore is the only option.

#### Install a certificate in the Windows keystore

1.  In Windows Explorer, navigate to the certificate &lt;my\_root\_certificate>.der and right-click (for example, at &lt;CFTDIRRUNTIME>/conf/pki/&lt;my\_root\_certificate>.der).
2.  Select the Install certificate option.
3.  Follow the screen instructions. Windows automatically imports the certificate to its keystore in the Intermediate certificate authorities folder.

Alternative method

1.  In Internet Explorer, select Tools > Internet Options.
2.  In the Content tab select the Certificate button.
3.  Select Import, which starts the Certificate Import Wizard.
4.  Click Next, and Browse to the &lt;my\_root\_certificate>.der.
5.  Follow the screen instructions. Windows imports the certificate to its keystore.

#### Install a certificate in the Java keystore

The Java keystore is a file located at ~/jre/lib/security/cacerts. The default password for this keystore is “changeit”.

Use the keytool command as follows to import the &lt;my\_root\_certificate>.der certificate into the Java keystore:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>keytool </span><span>–</span><span>importcert</span></p>
            <p>   -trustcacerts</p>
            <p>   -alias AXWMFTCA</p>
            <p><span>   -file &lt;my_root_certificate&gt;</span><span>.der</span></p>
            <p>   -storepass changeit<span>-keystore </span><span>&lt;keystore&gt;</span></p>         </td>
      </tr>
   </tbody>
</table>
