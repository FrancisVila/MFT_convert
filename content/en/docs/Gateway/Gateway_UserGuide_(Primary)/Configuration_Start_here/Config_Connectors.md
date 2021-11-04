{
    "title": "Configuring connectors",
    "linkTitle": "Configuring connectors",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

Set up the <span style="font-weight: bold;">Axway Connectivity</span> parameters to enable Gateway to communicate using different connectors.

<span id="Configuring"></span>

## Configuring connectors

To configure a connector, select the desired connector in the left (tree view) pane, then complete the parameter fields (if any) in the right pane.

### Prerequisites for all connectors

-   The required software (for example Integrator) must be installed on your system.
-   All parameter values must correspond to those defined for that software (for example Integrator).

### Activating/deactivating connectors

In the configuration menu:

-   To enable a connector in Gateway, click <span style="font-weight: bold;">Activate</span>.
-   If you no longer want to use a connector, click <span style="font-weight: bold;">Deactivate</span> to disable it.

<span style="font-weight: bold;">Note:</span> For PassPort there is no <span style="font-weight: bold;">Activate</span> or <span style="font-weight: bold;">Deactivate</span> button. After completing the configuration parameters, the connector is activated.

This topic documents parameters for connection with the following environments:

-   [Integrator](#olh_connectivity_xib)
-   [PassPort](#olh_connectivity_passport)
-   [Sentinel](#olh_connectivity_sentinel)
-   [Messaging](#olh_connectivity_xms)
-   [JMS](#olh_connectivity_jms)
-   [MFT Navigator](#olh_connectivity_iui)
-   [SWIFTNet](#olh_connectivity_swiftnet)
-   [X.400](#olh_connectivity_x400)

<span id="olh_connectivity_xib"></span>

## Connectivity &gt; Axway Connectivity &gt; Integrator

Use the following parameters to configure Gateway for use with the Integrator (formerly XIB) connector.

If the payload integrity check is enabled for transfers received from Integrator, Gateway makes a signature validation before routing the incoming payload. The signature is received from Integrator, that is why Integrator’s public key is required for signature validation

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Gateway to Integrator connection</p>         </td>
      </tr>
      <tr>
         <td><p>Address</p>         </td>
         <td><p>Enter the IP address in dotted format, or the DNS host name of the Integrator connector.</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the port number assigned to the Integrator connector. This value must be in decimal format and unique on the operating system.</p>         </td>
      </tr>
      <tr>
         <td><p>Shared directory</p>         </td>
         <td><p>Enter a file directory name. Gateway must have read-write access to this directory.</p>
<p>Click the browse button to help you locate and select the directory.</p>         </td>
      </tr>
      <tr>
         <td><strong>RSA public key</strong>         </td>
         <td>Path to Integrator public key in PEM format         </td>
      </tr>
      <tr>
         <td><p><strong><span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> to <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span> - secured by <span id="TLS"></span>TLS</strong></p>         </td>
      </tr>
      <tr>
         <td>Tls active         </td>
         <td>Optionally secure the connection with <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span> using TLS         </td>
      </tr>
      <tr>
         <td>CA file         </td>
         <td>The path to the file containing the certificate authority that validates the certificate of <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span>         </td>
      </tr>
      <tr>
         <td>Certificate file         </td>
         <td>The path to the file containing the certificate Gateway can use to authenticate itself as TLS client to <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span>         </td>
      </tr>
      <tr>
         <td>Key file         </td>
         <td>The path to the private key of the client certificate of <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span>         </td>
      </tr>
      <tr>
         <td>Password file         </td>
         <td>The path to the file containing the enciphered password <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses to access the private key of its client certificate. To generate this file, use the <code>pelencpass </code>utility.         </td>
      </tr>
      <tr>
         <td>Password key file         </td>
         <td>The path to the file containing the key used to decipher the password file containing the enciphered password <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses to access the private key of its client certificate. To generate this file, use the <code>pelencpass </code>utility.         </td>
      </tr>
   </tbody>
</table>

Click <span style="font-weight: bold;">Activate</span> to enable the connector.

### Setting TLS parameters with the command line

The parameters related to securing the connection between <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> and <span class="mc-variable suite_variables.IntegratorName variable">Integrator</span> can also be configured using the <span class="code">peluconf </span>utility, in the `amtrix `section. Please use the utility to inspect the section for more information:

`peluconf get -s amtrix`

<span id="olh_connectivity_passport"></span>

## Connectivity &gt; Axway Connectivity &gt; PassPort

Use the following parameters to configure Gateway for use with:

-   PassPort PS (PKI Services)
-   PassPort PM (Partner Management)
-   PassPort AM (Access Management)

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>am_cache_privileges yes/no</strong>         </td>
         <td><p>Enables or disables the batch caching of user privileges.</p>
<p>The default behavior of the PassPort AM connector is to cache each privilege individually, as it is checked. You can optimize this behavior with <code>am_cache_privileges yes</code>: at the first privilege check, the connector retrieves and caches <em>all</em> the privileges of <em>all</em> the users in <em>all</em> the domains that are assigned to the Gateway component. This cache is refreshed with the frequency configured by the <span class="code">am_cache_duration</span> parameter. Once the cache expires, a new request is sent to the server to retrieve all privileges.</p>         </td>
      </tr>
      <tr>
         <td><strong>am_cache_duration nbMinutes</strong>         </td>
         <td>If <span class="code">am_cache_privileges </span>is set to <code>yes, </code>controls the number of minutes the authentication status and/or privileges of a user are cached. <code>am_cache_duration 0 </code>means the cache is disabled.         </td>
      </tr>
      <tr>
         <td><strong>retry_min</strong>         </td>
         <td><p>Back off mechanism parameters, in seconds. </p>
<p>retry_min and retry_max work together to determine the length of time Gateway waits between two attempts to reestablish the connection with PassportAM. The first attempt times out after retry_min seconds. Delays for subsequent attempts double each time, until the value reaches retry_max.</p>         </td>
      </tr>
      <tr>
         <td><strong>retry_max</strong>         </td>
      </tr>
      <tr>
         <td><strong>PassPort Version</strong>         </td>
         <td><p>Select the version of PassPort you are using with Gateway.
Possible values:</p>
<ul>
<li><span class="mc-variable suite_variables.PassPortName variable">PassPort</span> 3.3</li>
<li><span class="mc-variable suite_variables.PassPortName variable">PassPort</span> 3.4</li>
<li><span class="mc-variable suite_variables.PassPortName variable">PassPort</span> 4.0 - Select this value for any version of PassPort from 4.0 onwards</li>
</ul>
<p>Depending on the PassPort version, different configuration options will be available.</p>         </td>
      </tr>
      <tr>
         <td><strong>Use access management</strong>         </td>
         <td>Select this option if you use PassPort’s access management (AM) service with Gateway.
This option is enabled if the selected PassPort version is <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> v4.         </td>
      </tr>
      <tr>
         <td><strong>Use PKI Services</strong>         </td>
         <td>Select this option if you use <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s PKI services (PS) with Gateway.         </td>
      </tr>
      <tr>
         <td><strong>Use partner management</strong>         </td>
         <td>Select this option if you use <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s partner management service (PM) with <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>.         </td>
      </tr>
      <tr>
         <td><strong>PassPort Host</strong>         </td>
         <td>Enter the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> host name or IP address.         </td>
      </tr>
      <tr>
         <td><strong>PassPort Ports</strong>         </td>
      </tr>
      <tr>
         <td><strong>PKI</strong>         </td>
         <td>Enter <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s port for PKI service.         </td>
      </tr>
      <tr>
         <td><strong>HTTP</strong>         </td>
         <td>Enter <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s port for access management (AM) and partner management (PM) services.         </td>
      </tr>
      <tr>
         <td><strong>Component Id</strong>         </td>
         <td><p><em>Optional</em></p>
<p>Enter a name to identify Gateway in PassPort PM.
If you leave this blank, the default Local Site alias is used.
This field is enabled only if the selected PassPort version is <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> v4.</p>         </td>
      </tr>
      <tr>
         <td><strong>Component login</strong>         </td>
         <td><p>Enter the user name for PassPort PM server login.
This field is enabled only if the selected PassPort version is <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> version 4.0.</p>
<p>The corresponding password must be specified by using the <code>pelencpass </code>command executed locally on the Gateway server machine.
See the <em>Security Guide &gt; <a href="#"><em>Password management</em></a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><strong>Secure connection</strong>         </td>
      </tr>
      <tr>
         <td><strong>Use TLS</strong>         </td>
         <td>Select this option to use TLS/SSL and then complete the proceeding parameters.         </td>
      </tr>
      <tr>
         <td><strong>PassPort Secure Ports</strong>         </td>
      </tr>
      <tr>
         <td>PKI SSL         </td>
         <td>Enter <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s secure port for PKI services (PS).         </td>
      </tr>
      <tr>
         <td><strong>HTTPS</strong>         </td>
         <td><p>Enter <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>’s secure port for access management (AM) and partner management (PM) services.</p>
<p>This field is enabled only if the selected PassPort version is <strong>PassPort v4</strong> and <strong>Use TLS</strong> option is selected.</p>         </td>
      </tr>
      <tr>
         <td><strong>PassPort CA location</strong>         </td>
         <td><p>Enter the location (absolute path) where the PassPort CA certificate is located.</p>
<p>Click the <strong>browse</strong> button to help you locate and select the directory.</p>
<p>This value is first set at installation time.
The default value for this location is <code>$p_home_dir/extras/PassPort/PassportCA.crt</code>.</p>
<p>This field is enabled only if the selected PassPort version is <strong>PassPort v4</strong> and <strong>Use TLS</strong> option is selected.</p>         </td>
      </tr>
      <tr>
         <td><strong>Client certificate location</strong>         </td>
         <td><p>Enter the location (absolute path) where Gateway’s certificate for Passport AM is stored.</p>
<p>Click the <strong>browse</strong> button to help you locate and select the directory.</p>
<p>This certificate is required because the secured connection between Gateway and PassPort uses mutual authentication.
If you don’t have a certificate, a new one will be generated automatically the first time Gateway connects to Passport AM. This automatically generated certificate will be stored at the client certificate location you specified.</p>
<p>The name of the automatically generated certificate is Gateway.p12.</p>
<p>This value is first set at installation time.
The default value for this location is <code>%p_home_dir%/extras/PassPort</code>.
The password of this certificate must be specified by using the <code>pelencpass </code>command executed locally on the Gateway server machine.
See the <a href="#">Security Guide</a> for further information
This field is enabled only if the selected PassPort version is <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> v4 and <strong>Use access management</strong> and <strong>Use TLS</strong> options are both selected.</p>         </td>
      </tr>
      <tr>
         <td><strong>PassPort PM v3</strong> – this section is enabled only if the selected PassPort version is <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> v3.3 or <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> v3.4         </td>
      </tr>
      <tr>
         <td><strong>Home directory</strong>         </td>
         <td>Enter the path and name of the directory where PassPort PM is installed. The location of this directory can be local or remote.
Click the <strong>browse</strong> button to help you locate and select the directory.         </td>
      </tr>
      <tr>
         <td><strong>Parameters file</strong>         </td>
         <td>Enter the path and file name of the <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> PM parameters file.
Click the <strong>browse</strong> button to help you locate and select the file.         </td>
      </tr>
   </tbody>
</table>

<span style="font-weight: bold;">Note:</span>

-   After completing the PassPort configuration parameters, the connector is activated.

#### Configuring PassPort connector in command line

From <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> 6.16 onwards, the `[passport]` parameter section is added to the `dconfsave.ini `file for unified PassPort configuration. This section is used by the GUI, and <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> uses the parameters in this section by default when communicating with <span class="mc-variable suite_variables.PassPortName variable">PassPort</span>.

The old sections (`[am]` and `[tpm]`) have been preserved for backwards compatibility reasons. In case of legacy <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> instances, the existing settings are also preserved. Although the new <span class="code">\[passport\]</span> section is active by default, it is still possible to continue to use the old parameters by executing the following command:

`peluconf set -s [passport] use_legacy_settings`

The old parameters can be modified only via command line.

<span id="olh_connectivity_sentinel"></span>

## Connectivity &gt; Axway Connectivity &gt; Sentinel

Use the following parameters to configure Gateway for use with Sentinel.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Host name</p>         </td>
         <td><p>Enter the IP address or the host name of the Sentinel server or Event Router.<br />
Maximum: 64 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the TCP port number of the Sentinel server or Event Router.<br />
Maximum: 32 numeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Backup host</p>         </td>
         <td><p>Enter the IP address or the host name of the backup Sentinel server.<br />
Maximum: 64 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Backup port</p>         </td>
         <td><p>Enter the TCP port number of the backup Sentinel server.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer filter</p>         </td>
         <td><p>Specify the level of information to send to Sentinel regarding Transfer state changes.</p>
<p>Select one of the following values:</p>
<ul>
<li><strong>All</strong>: complete trace for all Transfer state changes</li>
<li><strong>Summary</strong>: creation and end of Transfer only</li>
<li><strong>None</strong>: no trace</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Log filter</p>         </td>
         <td><p>Specify the level of log information to send to Sentinel or the Event Router.</p>
<p>Select one, or more, or none, of the following options:</p>
<ul>
<li><strong>Success</strong></li>
<li><strong>Information</strong></li>
<li><strong>Warning</strong></li>
<li><strong>Error</strong></li>
<li><strong>Failure</strong></li>
</ul>
<p><span style="font-weight: bold;">Note:</span> You can also set this parameter in the Remote Site, the Application and the Transfer Request objects.</p>         </td>
      </tr>
      <tr>
         <td><strong>sentinel_use_tls</strong>         </td>
         <td>Toggles the use of TLS for securing connection to Sentinel         </td>
      </tr>
      <tr>
         <td><strong>sentinel_ca_file</strong>         </td>
         <td>Configures the certificate authority file of the sentinel server Gateway is configured to connect to         </td>
      </tr>
   </tbody>
</table>

Click <span style="font-weight: bold;">Activate</span> to enable the connector.

<span id="olh_connectivity_xms"></span>

## Connectivity &gt; Axway Connectivity &gt; Messaging

You do not need to set any parameters for Axway Messaging (formerly XMS). Just click <span style="font-weight: bold;">Activate</span> to enable the connector.

<span id="olh_connectivity_jms"></span>

## Connectivity &gt; Axway Connectivity &gt; JMS

You do not need to set any parameters for JMS. Just click <span style="font-weight: bold;">Activate</span> to enable the connector.

<span id="olh_connectivity_iui"></span>

## Connectivity &gt; Axway Connectivity &gt; MFT Navigator

Use the following parameters to configure Gateway to use an Axway MFT Navigator (formerly IUI) server to support remote Internet or Intranet clients.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Listening port</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the TCP port number assigned to the MFT Navigator Server. The port number must be in decimal format and unique on the Operating System.</p>
<p>Default = 6300.</p>         </td>
      </tr>
      <tr>
         <td><p>Network interface</p>
<p>(<span style="font-style: italic;">mandatory</span>)</p>         </td>
         <td><p>Enter the local IP address in dotted format, or the local host name as defined in the HOST file.</p>         </td>
      </tr>
      <tr>
         <td><p>The following fields are optional. You can activate the MFT Navigator server without using the TLS option.</p>         </td>
      </tr>
      <tr>
         <td><p>Use TLS</p>         </td>
         <td><p>Select this option to use TLS/SSL and then complete the following parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>X509 certificate</p>         </td>
         <td><p>Enter the file name that contains the X.509 certificate to be used by the MFT Navigator server. Typically, this is a file in PKCS 12 format.</p>         </td>
      </tr>
      <tr>
         <td><p>Password file</p>         </td>
         <td><p>Enter the file name that contains the password used to access the X.509 certificate.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_connectivity_iui_adv_options"></span>If you want to modify the cipher suites, click <span style="font-weight: bold;">Advanced...</span> to access <span style="font-style: italic;">MFT Navigator advanced options</span>.

From the list, select one or more of the encryption algorithms supported by Gateway, then click <span style="font-weight: bold;">OK</span>.

Click <span style="font-weight: bold;">Activate</span> to enable the connector.

<span id="olh_connectivity_swiftnet"></span>

## Connectivity &gt; Axway Connectivity &gt; SWIFTNet

Use the following parameters to configure <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> for use with SWIFTNet.

### General tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Default RA installation pathname</p>         </td>
         <td><p> </p>
<p>Enter the default directory path name for SWIFTNet RA.</p>
<p>Example: <span class="code">C:\SWIFTAlliance\RA</span></p>
<p>Click the browse button to help you locate and select the directory.</p>         </td>
      </tr>
      <tr>
         <td><p>Accept possible duplicate transfers</p>         </td>
         <td><p>FileAct only</p>
<p>Check this option to accept incoming SWIFTNet <a href="../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_possible_duplicate">Possible Duplicate transfers</a>.</p>         </td>
      </tr>
      <tr>
         <td><span id="Limit"></span>Limit the number of initiated transfers         </td>
         <td><p><em>FileAct only</em></p>
<p>Enable the limitation of the number of transfers in Initiator mode for FileAct only (delivery notifications excluded). The value of the maximum number of transfers is set on a SWIFTNet remote site. By default, this option is disabled.</p>         </td>
      </tr>
      <tr>
         <td>Global maximum number of initiated transfers         </td>
         <td>The global value of the maximum number of transfers in Initiator mode, FileAct only. By default, this parameter is set to <em>0</em>, meaning unlimited. The maximum value allowed is <em>999999</em>.
The number of initiated transfers is counted as the sum of FileAct transfers initiated for all remote sites.         </td>
      </tr>
      <tr>
         <td><span id="Subscribe_all_file_events"></span>Subscribe to all file events         </td>
         <td><p>FileAct only</p>
<p>By default this option is enabled, allowing Gateway to subscribe to all file events. To improve performance, you can deactivate this option and disable the subscription to the ongoing (intermediary) events. Note that when this option is deactivated, the statistics for the number of bytes transferred is not updated.</p>
<p>If this option is enabled, you must update the transfer status polling mechanism delay to a higher value (over 300) to avoid unwanted or unnecessary transfer state queries when intermediary file events are disabled, especially for large FileAct transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Proof keeping</p>         </td>
         <td><p>Check this option to activate <a href="../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_proof_keeping">SWIFTNet proof keeping</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Default proof directory</p>         </td>
         <td><p>Specify the destination folder for SWIFTNet proof keeping.</p>
<p>Either browse or manually set the folder.</p>
<p>You can use Gateway environment variables:</p>
<ul>
<li>%VAR% and \ separator for Windows</li>
<li>$VAR and / separator for UNIX</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Customize file info parser</p>         </td>
         <td><p>Select whether or not to customize the SWIFT grammar rules for the Sw:FileInfo field. This is a global setting for all partners.</p>
<p><strong>Warning:</strong> In normal circumstances you should <strong>not</strong> override the default values provided in Gateway:</p>
<ul>
<li><strong>Separator</strong>: <span class="code" style="font-weight: bold;">;</span> [semi-colon]</li>
<li><strong>Equals</strong>: <span class="code" style="font-weight: bold;">=</span> [equals sign]</li>
<li><strong>Quotes</strong>: <span class="code" style="font-weight: bold;">"</span> [quote mark]</li>
</ul>
<p>These default values correspond to the grammar for the Sw:FileInfo field as defined in the SWIFT documentation.</p>
<p>In some specific cases, for example for backward compatibility with older applications that are not SWIFT compliant, you may need to modify one or more of these three special characters.</p>
<p>You can override these global settings in each individual Trading Partner. This global setting enables you to easily change the values for all partners without having to modify each Trading Partner.</p>
<p>If you modify the global values you must restart Gateway for the new values to be taken into account.</p>         </td>
      </tr>
      <tr>
         <td><p>[Transfer status polling mechanism]</p>
<p>Use the parameters <strong>Transfer status polling interval</strong> and <strong>Transfer status polling delay</strong> in combination with each other.</p>
<p>By default the polling mechanism is disabled (Transfer status polling interval = 0).</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer status polling interval</p>         </td>
         <td><p>Specify the polling interval in seconds.</p>
<p>Occasionally events from SWIFT concerning the transfer status (such as completed) can get "lost". This could result in an incorrect transfer status in Gateway.</p>
<p>To ensure that the transfer status in Gateway is always up to date, Gateway can send a GetFileStatus primitive to SWIFT at regular intervals. This only happens if the <strong>Transfer status polling delay</strong> has been reached. After checking the received status, Gateway can update its transfer status to match the status at the SWIFT side.</p>
<p>You can use this mechanism for incoming or outgoing FileAct messages.</p>
<p>If you set the value to 0, this mechanism is disabled.<br />
If you use any other value, the polling mechanism is activated.</p>
<p>Possible values: 0 – 7200.<br />
Default = 0.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer status polling delay</p>         </td>
         <td><p>Specify the polling delay (in seconds).</p>
<p>The polling delay is the time passed from the last transfer update (request sent to or received from SWIFT, or a File Event) after which the transfer can be selected for a GetFileStatus operation.</p>
<p>Possible values: 10 – 7200.<br />
Default = 60.</p>         </td>
      </tr>
      <tr>
         <td><p>Number of compression/ decompression processes</p>         </td>
         <td><p>Specify the number of helper processes to handle the compression/ decompression operations.</p>
<p>Possible values: 1 – 100.<br />
Default = 1.</p>
<p>All processes are started at Gateway startup. Therefore, if you modify this setting you must restart Gateway for the new value to be taken into account.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_connectivity_swiftnet_userexit"></span>

### UserExit tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Activate user exit</p>         </td>
         <td><p>Check this option to use the <a href="../../connectors_about/swiftnet_about/swiftnet_sig_list/swiftnet_user_exits">user exit process</a> to control incoming and outgoing Transfer Requests and to recover some transfer parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Address</p>         </td>
         <td><p>Enter the TCP IP address/host address for the internal user exit process listen interface.</p>
<p>Default = 127.0.0.1</p>         </td>
      </tr>
      <tr>
         <td><p>Port</p>         </td>
         <td><p>Enter the listening port for internal user exit process connections.</p>
<p>Default = 6666.</p>         </td>
      </tr>
      <tr>
         <td><p>Timeout</p>         </td>
         <td><p>Specify the incoming request maximum duration (timeout) in seconds.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_connectivity_swiftnet_snf"></span>

### Store and Forward tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="snf_check_timer"></span>SnF check timer</p>         </td>
         <td><p>Specify the time interval (in seconds) during which Gateway checks the status of the acquired SnF session in case no activity has been noticed on that queue in that time interval.</p>
<p>The most suitable time interval for your environment depends on the SnF traffic volume and time constraints. When the timer expires, Gateway initiates an SnFStatusRequest and reports the returned status.</p>
<p>Gateway uses this configuration parameter to monitor the status of acquired SnF sessions. For several reasons, in a time interval, it is possible that there is no activity (no pushed message request) on a given acquired queue. For example, if someone else reacquired the queue with the force option, thus the session became invalid; SWIFT has released the SnF session due to some internal technical issues; simply there is no message in our queue, and so on.</p>
<p>Note that if a message request has been pushed on an SnF session that means the session is Active, and there is no reason to check the status of the acquired SnF session, the SnF check timer is reset for that SnF session (the one on which a message has been pushed).</p>
<p>Possible values: 0 – 7200 (2 hours).<br />
Default = 120 (2 minutes).</p>         </td>
      </tr>
      <tr>
         <td><p><span id="reacquire_snf"></span>Reacquire SnF session automatically</p>         </td>
         <td><p>Select whether or not an SnF session should be reacquired automatically if it is lost.</p>
<p>By default this option is enabled, so that the SnF session is reacquired when it is no longer valid. You can deactivate this option if required (for example if the same queue is used in more than one environment, or any other reason).</p>
<p>For example, if the same queue is acquired on another system, the current SnF session will become invalid. Gateway detects this and reacquires the queue automatically.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_connectivity_swiftnet_asp_rma"></span>

### ASP/RMA tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ASP/RMA Check</p>         </td>
         <td><p>Activates the ASP check and RMA filtering.</p>
<p>Values:</p>
<ul>
<li>ASP &amp; RMA enabled</li>
<li>ASP enabled, RMA disabled</li>
<li>ASP &amp; RMA disabled:(default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ASP helpers</p>         </td>
         <td><p>Number of processes started for handling the ASP check operations.</p>         </td>
      </tr>
      <tr>
         <td><p>ASP</p>
<p>Do not change default values unless absolutely necessary (for example, SWIFT changes file names).</p>         </td>
      </tr>
      <tr>
         <td><p>ASP Profiles Directory</p>         </td>
         <td><p>Select the directory containing the ASP files <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> loads at startup or reloads during runtime if requested</p>         </td>
      </tr>
      <tr>
         <td><p>ASP Profile Schema</p>         </td>
         <td><p>XML schema for ASP profiles.</p>         </td>
      </tr>
      <tr>
         <td><p>ASP Profile Extension</p>         </td>
         <td><p>File extension of the ASP profiles.</p>         </td>
      </tr>
      <tr>
         <td><p>ASP Digest File</p>         </td>
         <td><p>Name of the XML file from the ASP package containing the digests for all ASP profiles in the package.</p>         </td>
      </tr>
      <tr>
         <td><p>ASP Digest Schema</p>         </td>
         <td><p>XML schema for the digest file.</p>         </td>
      </tr>
      <tr>
         <td><p>RMA</p>         </td>
      </tr>
      <tr>
         <td><p>RMA User Exit Library</p>         </td>
         <td><p>If the RMA authorization check is enabled, enter or select the full path of the RMA user exit library, <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> loads the library at startup.</p>         </td>
      </tr>
      <tr>
         <td><p>RMA Configuration</p>         </td>
         <td><p>If the RMA authorization check is enabled, enter or select the full path of the RMA configuration file that is passed to the RMA user exit library.</p>         </td>
      </tr>
      <tr>
         <td><p>Stop unauthorized transfers in Trial Period</p>         </td>
         <td><p>Specifies whether to stop unauthorized transfers in trial period.</p>
<ul>
<li>Enable to stop. The behavior is the same as mandatory period.</li>
<li>Disable to allow unauthorized transfers in trial period. This is the default.</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Click <span style="font-weight: bold;">Activate</span> to enable the connector.

### HA (High Availability) tab

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>High Availability Exit         </td>
         <td><p>Activates and set the High Availability operation mode.
Possible values:</p>
<ul>
<li>HA operation disabled</li>
<li>Use correlation exit</li>
<li>Use external correlation</li>
</ul>         </td>
      </tr>
      <tr>
         <td>HA Correlation Exit         </td>
         <td>Do not change the default value unless absolutely necessary (for example the name of the HA library has changed).
Enter the path to the High Availability Exit Library.
Click the browse button to help you locate and select the file.         </td>
      </tr>
      <tr>
         <td>Database Type         </td>
         <td>Select the database type (MYSQL or ORACLE).         </td>
      </tr>
      <tr>
         <td>DB Data Source Name         </td>
         <td>Select the database DSN name.         </td>
      </tr>
      <tr>
         <td>DB Connection User         </td>
         <td>Select the database DSN user.         </td>
      </tr>
      <tr>
         <td>DB Connection Password         </td>
         <td><p>Not editable.</p>
<p>The DB connection password must be encrypted using the <span class="code">pelencpass</span> command, and the <span class="code">swnet_ack_userexit_db_salt_file</span>, <span class="code">swnet_ack_userexit_db_dk_file</span> and <span class="code">swnet_ack_userexit_db_password_file</span> configuration parameters must be set accordingly.
See <em>Security Guide &gt; <a href="#">Secure Password Storage</a></em> for further information.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Parameters related to the HA Correlation Exit (HA Correlation Exit, Database Type, DB Data Source Name, DB Connection User, DB Connection Password) are only required if High Availability Exit is set to Use correlation exit.

> **Note:**
>
> The PeSIT Duplicate Checking mechanism uses the HA Correlation Exit, thus requiring that all parameters be set.

See the [SWIFTNet High Availability User Exit Configuration](../../connectors_about/swiftnet_about/swiftnet_ha_overview/swiftnet_ha_user_exit_config) and the <a href="../../connectors_about/swiftnet_about/swiftnet_ha_overview/swiftnet_ha_externalcorrelation" class="MCXref xref">SWIFTNet High Availability with External Correlation</a> sections for more details about configuring the SWIFTNet High Availability feature.

<span id="olh_connectivity_x400"></span>

## Connectivity &gt; Axway Connectivity &gt; X.400

Use the following parameters to configure Gateway for use with X.400.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Local MTA</p>         </td>
      </tr>
      <tr>
         <td><p>Name *</p>         </td>
         <td><p>Enter a name (public name) for the local Message Transfer Agent (MTA).</p>         </td>
      </tr>
      <tr>
         <td><p>TSAP *</p>         </td>
         <td><p>Enter the TSAP (Transport Service Access Point). Maximum 20 characters.</p>
<p>To specify a hexadecimal value, enter the value between apostrophes ( ' ), for example, <span class="code">'7C,A2'</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>O/R address *</p>         </td>
         <td><p>Specify the O/R address attributes that are common to all local users.</p>         </td>
      </tr>
      <tr>
         <td><p>Edit</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Edit...</span> to configure the <a href="../config_protocols_about/x400_or_address">O/R address</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>Clear</p>         </td>
         <td><p>Click <span style="font-weight: bold;">Clear</span> to delete the displayed O/R address.</p>         </td>
      </tr>
      <tr>
         <td><p>Advanced settings</p>
<p>Use the following buttons to access advanced parameters.</p>         </td>
      </tr>
      <tr>
         <td><p>Server ports...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_server_ports">Advanced server ports settings</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>OSITP...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_ositp">Advanced OSITP settings</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>MTA...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_mta">Advanced MTA settings</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>MTC...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_mtc">Advanced MTC settings</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>MS...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_ms">Advanced MS settings</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>UA...</p>         </td>
         <td><p>Refer to <a href="../config_protocols_about/config_x400_advanced#olh_advanced_ua">Advanced UA settings</a>.</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Mandatory parameter

<span style="font-weight: bold;">Important:</span> For X.400, make sure that you complete all configuration parameters and check that the entered information is coherent <span style="font-weight: bold;">before</span> activating the connector. Failing to observe this rule could result in unpredictable behavior.

Click <span style="font-weight: bold;">Activate</span> to enable the connector.

Related topics

[Configuration: Procedure](../config_procedure)

[About <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> connectors](../../connectors_about)

[SWIFTNet-specific user exits](../../connectors_about/swiftnet_about/swiftnet_sig_list/swiftnet_user_exits)

[SWIFTNet Proof keeping](../../connectors_about/swiftnet_about/swiftnet_backup_sites/swiftnet_proof_keeping)

[Configuring protocols: X.400 advanced parameters](../config_protocols_about/config_x400_advanced)

[X.400 connector](../../connectors_about/x400_about/x400_connector)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
