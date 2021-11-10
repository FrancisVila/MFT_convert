{
    "title": "Configuring PassPort AM ",
    "linkTitle": "Configuring PassPort AM",
    "weight": "200"
}This section describes how to configure access management when not using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

<span id="Procedure PassPort parameters"></span>

## Procedure

To configure the PassPort AM connection, set the UCONF parameters described
in this section. From
the <span style="font-weight: bold;">Administration</span> screen in the
graphical user interface, access the *Unified Configuration* window. Double-click in the <span style="font-weight: normal; font-style: italic;">Unified
Configuration</span> window to begin editing parameters.

1.  Define the connection to the PassPort AM server using the UCONF parameters in the following tables. You must define the parameters in the order listed.

PassPort AM connector parameters

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><div class="indentTable">
am.passport.hostname
</div>         </td>
         <td><div class="indentTable">
PassPort AM server hostname/IP address.
</div>         </td>
      </tr>
      <tr>
         <td><div class="indentTable">
am.passport.port
</div>         </td>
         <td><div class="indentTable">
PassPort AM server port.
</div>         </td>
      </tr>
      <tr>
         <td>am.passport.srchost         </td>
         <td><p>The PassPort AM local network interface for outgoing connections.</p>         </td>
      </tr>
      <tr>
         <td><div class="indentTable">
am.passport.instance_id
</div>         </td>
         <td><p>Transfer CFT instance ID for PassPort AM  </p>
<ul>
<li>You must determine your Transfer CFT's PassPort instance name. If it does not match the instance name of <strong>default</strong>, you must add an instance with the correct name.</li>
<li>The passport.instance_id corresponds to the
instance (An instance name is a unique identifier of the installed instance of the component. Check that PassPort and your Transfer CFT have the SAME instance name) of the CSD that is available in PassPort.</li>
<li>In PassPort, you can view this by selecting <strong>Access</strong> &gt; <strong>Components</strong> &gt; <strong>Transfer CFT</strong> and checking the screen display (default value: default (when you import a component, PassPort assigns it the instance name <strong>default</strong> )).</li>
</ul>         </td>
      </tr>
      <tr>
         <td><div class="indentTable">
am.passport.login
</div>         </td>
         <td><div class="indentTable">
Transfer CFT login for PassPort AM. This user must exist in PassPort and have an Administrator role. This user represents an application user with which Transfer CFT makes requests.
</div>         </td>
      </tr>
      <tr>
         <td><div class="indentTable">
am.passport.password
</div>         </td>
         <td><div class="indentTable">
Transfer CFT Instance ID Password for PassPort AM, see above.
</div>         </td>
      </tr>
      <tr>
         <td><div class="indentTable">
am.passport.superuser
</div>         </td>
         <td><p>Enables users to perform any type of action without PassPort AM permission checks.</p>
<p>You <em>must</em> set up at least one superuser. Doing so enables you to deactivate or change the PassPort AM connector configuration if the server is not responding.</p>
<p>If the user's name for a session contains a space in the name, you must insert the backslash <strong>\</strong> character where the space occurs.</p>
<p>Example</p>
<p>If you are defining the users "firstname lastname" and "johndoe" as superusers, you would set the am.passport.superuser parameter value to "firstname<strong>\</strong> lastname johndoe".</p>
<p>So for this example, the command is:</p>
<p>CFTUTIL uconfset id = am.passport.superuser, value = "'firstname\ lastname johndoe'"</p>         </td>
      </tr>
      <tr>
         <td>am.passport.use_ssl         </td>
         <td><p>Enables SSL with PassPort AM.</p>
<p>The server port is <em>not</em> the same as the default port when using SSL.</p>         </td>
      </tr>
      <tr>
         <td>am.passport.ca_cert         </td>
         <td>Certification Authority (CA) public certificate to authenticate the PassPort AM server.         </td>
      </tr>
      <tr>
         <td>am.passport.csd_file         </td>
         <td>Transfer CFT Component Security descriptor file for PassPort AM.
The default value is $(cft.install_dir)/extras/PassPort/csd_Transfer_CFT.xml.         </td>
      </tr>
   </tbody>
</table>

1.  Set the access management type parameter to PassPort: <span style="font-family: 'Courier New'; font-size: 11pt;">am.type = passport</span>

> **Note:**
>
> The am.type is the last parameter to set when activating PassPort AM and the first to unset when deactivating it.

1.  Restart the Transfer CFT and Copilot servers.

## Example PassPort AM configuration with SSL 

1.  Configure the Access Management type:

CFTUTIL UCONFSET ID=am.type, VALUE=none

1.  Configure the connection using your CFTPARM PART name as the instance\_id value.

CFTUTIL UCONFSET ID=am.passport.hostname, VALUE=pam.company.com

CFTUTIL UCONFSET ID=am.passport.port, VALUE=6666  
CFTUTIL UCONFSET ID=am.passport.use\_ssl, VALUE=YES

CFTUTIL UCONFSET ID=am.passport.ca\_cert, VALUE=conf/pki/&lt;your\_passport\_CA>

CFTUTIL UCONFSET ID=am.passport.instance\_id, VALUE=CFT23412  
CFTUTIL UCONFSET ID=am.passport.login, VALUE=PASSPORT\_ADMIN\_USER

CFTUTIL UCONFSET ID=am.passport.password, VALUE=PASSPORT\_ADMIN\_PASSWORD

1.  Activate the PassPort Access Management:

CFTUTIL UCONFSET ID=am.type, VALUE=passport

## Optional PassPort AM

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Definition         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>am.passport.userctrl.check_permissions_on_transfer_execution         </td>
         <td><p><span id="Check"></span>Check the permissions for the execute action on the transfer resource when the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> user control is enabled (<a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/userctrl">USERCTRL</a>=YES). To disable the permission check, set the following parameter to No. The default is Yes.</p>         </td>
      </tr>
      <tr>
         <td>am.passport.domain         </td>
         <td>PassPort AM domain.         </td>
      </tr>
      <tr>
         <td>am.passport.max_connections         </td>
         <td>Maximum number of connections with PassPort.         </td>
      </tr>
      <tr>
         <td>am.passport.pipe_priority         </td>
         <td>Pipelining priority mode.         </td>
      </tr>
      <tr>
         <td>am.passport.pipeline_size         </td>
         <td>Maximum number of requests in the pipe for one PassPort.         </td>
      </tr>
      <tr>
         <td>am.passport.resource_prefix         </td>
         <td>Only EXPERTS may use the resource prefix.         </td>
      </tr>
   </tbody>
</table>

## References

A complete set of PassPort documentation is available at [support.axway.com](http://support.axway.com/).

For more information about starting the Transfer CFT UI (Copilot), refer to Starting and Stopping the Copilot UI.

Related topics

[About PassPort AM](../)

[PassPort AM CSD](../passport_am_csd)

[Defining user rights Windows]()

[Defining user rights Unix]()
