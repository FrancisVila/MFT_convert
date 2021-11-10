{
    "title": "Configuring Secure Relay advanced options",
    "linkTitle": "Configuring Secure Relay - advanced options",
    "weight": "170"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Configuration

This topic lists the Secure Relay parameters that you can modify in the <span style="font-style: italic;">Secure Relay advanced options</span> window. Gateway opens this window if you click the <span style="font-weight: bold;">Advanced...</span> button when configuring Secure Relay.

## Options in the Secure Relay advanced options window

To set the options below:

1.  Complete the fields of the <span style="font-style: italic;">Secure Relay advanced options</span> window as follows:

2.  Click <span style="font-weight: bold;">OK</span> to confirm the <span style="font-style: italic;">Secure Relay advanced options</span>.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Startup</strong>         </td>
         <td><ul>
<li><em>Starting/stopping of SecureRelay Master Agent is controlled by Gateway</em>.<br />
Select this option if you want Gateway to control starting and stopping of the Master Agent.<br />
Default = <em>selected </em></li>
<li><em>Startup delay max (in seconds) when SecureRelay is started by Gateway</em><br />
In this field, enter the maximum limit in seconds during which Gateway will accept Secure Relay connection attempts during startup. After the limit has expired, Gateway generates a Secure Relay connection failure message.<br />
Default = <strong>30</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>Master Agent settings</strong>         </td>
         <td>This section includes the following fields:
<ul>
<li><strong>Address</strong>: Specify the Master Agent address for communication with Gateway.<br />
Default = <span style="font-weight: bold;">127.0.0.1</span> (localhost)</li>
<li><strong>Comm port</strong><br />
Specify the local port you want to use for data links between Gateway and the Master Agent. The port you use must be unique for the machine.<br />
Default = <span style="font-weight: bold;">6801</span><br />
If the local machine already uses port 6801, select another unused port</li>
<li><strong>Outgoing admin port set</strong><br />
<em>Optional</em><br />
Specify one or more ports for outgoing administrative messages towards the Router Agent.<br />
If you do not define this parameter, the Master Agent automatically assigns an available port.</li>
<li><strong>Outgoing data port set</strong><br />
<em>Optional</em><br />
Specify one or more ports for outgoing data transfer towards the Router Agent.<br />
If you specify outgoing ports, you must specify at least as many ports as the number of connections specified in the <span style="font-weight: bold;"><a href="../config_secure_relay_ra_paras#Number_of_mux_connections">Number of multiplexed connections between Master and Router</a></span> field.<br />
If you do not define these ports, the Master Agent automatically assigns available ports.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>PKI Server</strong>         </td>
         <td><p>This section refers to the connection between SecureRelay and PassPort.</p>
<ul>
<li><strong>Use PassPort PKI server</strong><br />
Use this option to enable SecureRelay to use PassPort as PKI server.</li>
<li><strong>Connect using TLS</strong><br />
Use this option to enable TLS connection between XSR MA and Passport.Default is <em>enabled</em>.</li>
<li><strong>User Login</strong><br />
Username used for connecting to PassPort.</li>
<li><strong>Address</strong><br />
PassPort server address.</li>
<li><strong>Port</strong><br />
PassPort listening port. Default = <span class="code">7101 </span></li>
<li><strong>Server CA file</strong><br />
PassPort's CA certificate. This option is needed only when enabling TLS.</li>
<li><strong>Password salt</strong><br />
Location of the password salt file.</li>
<li><strong>Password dk</strong><br />
Location of the password derived key file.</li>
<li><strong>Password data</strong><br />
Location of the file containing the encrypted key.</li>
</ul>
<p>See <em>Security Guide &gt; <a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/Managing_Security/Password_management.htm">Password management</a></em> for further information.</p>         </td>
      </tr>
      <tr>
         <td><strong>Protocol login server</strong>         </td>
         <td><p>This section includes the following fields:</p>
<ul>
<li><strong>Address</strong><br />
The address of the protocol login server used when protocol login in DMZ is enabled (usually the address of the machine hosting Gateway).<br />
</li>
<li><strong>Port</strong><br />
The port to use for listening to login requests when protocol login in DMZ is enabled</li>
</ul>         </td>
      </tr>
      <tr>
         <td><strong>IP filtering in Secure Relay</strong>         </td>
         <td><p>This section includes the following field:</p>
<ul>
<li><strong>IP filtering in Secure Relay enable IP filtering in SecureRelay based on</strong>:<br />
Select this option to enable IP filtering in <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span>.
This is a global setting which applies for all <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> Router Agents and all service access points. The IP filtering can be disabled individually per service access point (Sap) – [<a href="../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_sap_parameters">Configuring protocols</a>: <a href="../../../gateway_userguide_(primary)/configuration_start_here/config_protocols_about/config_sap_parameters">SAP parameters</a>]. The following filtering methods are available:
<ul>
<li><em>White list</em>: Select this option and provide the location (absolute path) and file name of the static white list that <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> will use to filter the incoming connections.<sup>*</sup></li>
<li><em>Black list</em>: Select this option and provide the location (absolute path) and file name of the static black list that <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> will use to filter the incoming connections.<sup>* **<br />
</sup></li>
<li><em>Dynamic white list</em>: Select this option to enable <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> to build and use dynamic white lists</li>
<li>Note: When the <em>dynamic white list</em> is enabled, if in Black list mode, <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> populates the dynamic white list (builds the list) with the accepted IP addresses. Then, when switching to White list mode, <span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span> uses the dynamic list in addition to the static white list</li>
</ul></li>
</ul>
<p><sup>*</sup> The white list or the black list will be provided in files. The lists must comply with the following rules:</p>
<ul>
<li>the list separator is <code>";"</code></li>
<li>wildcards are supported for the IP address</li>
<li>specifying an IP range is allowed</li>
<li>IPv4 / IPv6 standards are supported</li>
<li>FQDN format for host names is allowed</li>
</ul>
<p>** It is possible to reload the blacklist without restarting <span class="mc-variable suite_variables.GatewayName variable">Gateway</span>, using the <span class="code"></span>command <span class="code">pelctl reload_xsr_ipfilter_file</span><br />
</p>         </td>
      </tr>
   </tbody>
</table>

## Options in Secure Relay relating to Gateway

The Secure Relay options below are not directly set in Gateway, but they have an effect on the working of Gateway. The table below provides a short introduction, with a link to the relevant documentation for Secure Relay.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>Connection Limiter</strong>         </td>
         <td><p>Connection Limiter is a feature in Secure Relay that can limit the number of concurrent connections, and the number of incoming connections from an IP address or from a group of IP addresses. By default, the connections that exceed the configured limits are dropped; but it is also possible to create a temporary blacklist to reject further incoming connections for a configurable period of time.</p>
<p>Connection Limiter security feature was added in Secure Relay 2.7.4 (available September 2021).</p>
<p>To activate Connection Limiter with Gateway there are 2 possibilities:</p>
<ul>
<li><p>using the <code>p_xsr_connlimit_conf </code>environment variable, which must be set to the full path to a file containing connection limits configuration, or
:</p></li>
<li><p>by placing the configuration file in the <code>run_time/</code> directory with the filename <code>connlimit.properties</code>.
A sample for Connection Limiter is available in the <code>run_time/xsr/samples/</code> directory.</p></li>
</ul>
<p>For more information about Secure Relay's Connection Limiter configuration file option:<br />
<a href="https://docs.axway.com/bundle/SecureRelay_274_AdministratorsGuide_allOS_en_HTML5/page/Content/sr_router_agent/sr_ra_conn_limit.htm">Connection Limiter configuration file .</a></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Configuration: Connectivity parameters](../../../gateway_userguide_(primary)/configuration_start_here/config_connectivity_paras#olh_connectivity_Secure_Relay)

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
