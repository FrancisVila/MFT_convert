{
    "title": "UCONF parameters for SecureRelay",
    "linkTitle": "UCONF parameters for Secure Relay",
    "weight": "270"
}While some of the Transfer CFT UCONF parameters for Secure Relay are quite technical, most have default values that should be suitable for common usage.

The MA and RA parameters are described in the following separate tables, and are all prefixed by <span class="bold_in_para">secure\_relay</span>.

<span id="_Toc362510690"></span>

## Master agent parameters

Parameters that appear in Master agent configuration file are in bold.

<table>
   <th>
      <tr>
<th><p>Parameter</p>         </th>
<th><p>Type</p>         </th>
<th><p>Default</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>secure_relay.enable</p>         </td>
         <td><p>Bool</p>         </td>
         <td><p>No</p>         </td>
         <td><p>General flag to access Transfer CFT through Secure Relay if set to Yes.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.autostart</p>         </td>
         <td><p>Bool</p>         </td>
         <td><p>Yes</p>         </td>
         <td>Allows an automatic start of the embedded Secure Relay Master Agent.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.jar_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>$(cft.install.xsr_dir)/xsrMaster.jar</p>         </td>
         <td>Secure Relay Master Agent jar file.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.pid_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>$(cft.runtime.run_dir)/xsrMaster.pid</p>         </td>
         <td>File containing the Secure Relay Master Agent Process ID.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.start_timeout</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>30 sec</p>         </td>
         <td>Amount of time, in seconds, in which Secure Relay can start before a timeout.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.start_options</p>         </td>
         <td><p>String</p>         </td>
         <td><p>-Xmx512m -Xrs</p>         </td>
         <td>Secure Relay Master Agent start options.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.conf_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>$(cft.runtime.run_dir)XsrConf.xml</p>         </td>
         <td>Secure Relay Master Agent configuration file.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma. ca_cert_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
         <td><p>Secure Relay certificate authority.</p>
<p>This is a mandatory field, however certificates are not delivered with Transfer CFT.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p> </p>         </td>
         <td><p>Secure Relay Master Agent user certificate.</p>
<p>This is a mandatory field, however certificates are not delivered with Transfer CFT.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_password_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>$(cft.runtime.run_dir)/XsrPwd.dat</p>         </td>
         <td>Secure Relay Master Agent certificate password file.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_password</p>         </td>
         <td><p>String</p>         </td>
         <td><p>test</p>         </td>
         <td>Secure Relay Master Agent certificate password.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.host</p>         </td>
         <td><p>String</p>         </td>
         <td><p>127.0.0.1</p>         </td>
         <td>Secure Relay Master Agent listening IP address or FQDN.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.comm_port</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>6801</p>         </td>
         <td>Secure Relay Master Agent listening communication port.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.log_level</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0=NONE, 1=SHORT, 2=FULL, 3=DEBUG</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.log_fname</p>         </td>
         <td><p>String</p>         </td>
         <td><p>$(cft.runtime.log_dir)/xsrMaster.log</p>         </td>
         <td>Secure Relay Master Agent log file.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.admin_outport_range</p>         </td>
         <td><p>String</p>         </td>
         <td><p>None</p>         </td>
         <td>Secure Relay Master Agent admin outport range.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.comm_outport_range</p>         </td>
         <td><p>String</p>         </td>
         <td><p>None</p>         </td>
         <td>Secure Relay Master Agent comm outport range.         </td>
      </tr>
   </tbody>
</table>

## Router Agent parameters

As you can have several Router Agents working with a Master Agent, the UCONF Router Agent definitions are arrays. Note however that Transfer CFT supports only one Router Agent.

In the Secure Relay parameters table below:

-   The letter N is used in parameter names.
-   Parameters that appear in Master Agent configuration file are displayed in bold.
-   For an array, use the notation format<span class="bold_in_para"> secure\_relay.ra.N.parameter</span>, where <span class="italic_in_para">N </span>is between <span class="italic_in_para">0</span> and <span class="italic_in_para">number of routers – 1</span>.

<table>
   <th>
      <tr>
<th><p>Parameter</p>         </th>
<th><p>Type</p>         </th>
<th><p>Default</p>         </th>
<th><p>Comment</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>secure_relay.ra.N.enable</p>         </td>
         <td><p>Bool</p>         </td>
         <td><p>Yes</p>         </td>
         <td>Enables the Router agent.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N.dmz</p>         </td>
         <td><p>String</p>         </td>
         <td><p>DMZ0</p>         </td>
         <td>Logical name of the DMZ where the Router Agent is running, with a maximum of 32 characters.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N.host</p>         </td>
         <td><p>String</p>         </td>
         <td><p>None</p>         </td>
         <td><p>Router Agent IP address or FQDN.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N.admin_port</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>6810</p>         </td>
         <td><p>Router Agent administration port.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N.comm_port</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>6811</p>         </td>
         <td><p>Router Agent communication port.</p>
This parameter is specific to each <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> using the Router Agent.
<p>If more than one <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses the same Router Agent, each <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> must have a unique value.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N. nb_data_connections</p>         </td>
         <td><p>Int</p>         </td>
         <td><p>5</p>         </td>
         <td>Number of data connections between the Master Agent and the Router Agent.         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N. data_channel_ciphering</p>         </td>
         <td><p>Bool</p>         </td>
         <td><p>No</p>         </td>
         <td><p>Activates data connections ciphering.</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.N. outcall_network_interface</p>         </td>
         <td><p>String</p>         </td>
         <td><p>None</p>         </td>
         <td><p>Address to bind for outgoing calls.</p>         </td>
      </tr>
   </tbody>
</table>

### Define the Router Agent to use  

The <span class="code">srdmz</span> parameter in the CFTPART command allows you to specify a dedicated DMZ for outgoing connections.



    secure_relay.ra      =  n  (number of Router Agents)
    secure_relay.ra.<i>.dmz = DMZ<i>   (for each Router Agent, i = 0 to n-1)
    secure_relay.ra.<i>.host = @hostSR<i> (for each Router Agent, i = 0 to n-1)
     
    CFTPART id=part,nspart=myself,srdmz=DMZ<i>   (where i is the Router Agents to be used for the outgoing connection)
