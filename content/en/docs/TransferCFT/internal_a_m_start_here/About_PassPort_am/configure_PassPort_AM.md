{
    "title": "Configuring PassPort AM",
    "linkTitle": "Configuring PassPort AM",
    "weight": "200"
}This section describes how to configure access management when not using Central Governance.

## <span id="Procedure PassPort parameters"></span>Procedure

To configure the PassPort AM connection, set the UCONF parameters described
in this section. From
the Administration screen in the
graphical user interface, access the *Unified Configuration* window. Double-click in the Unified
Configuration window to begin editing parameters.

1.  Define the connection to the PassPort AM server using the UCONF parameters in the following tables. You must define the parameters in the order listed.

PassPort AM connector parameters

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
<div>am.passport.hostname</div>
         </td>
         <td>
<div>PassPort AM server hostname/IP address.</div>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
<div>am.passport.port </div>
         </td>
         <td colspan="1" rowspan="1">
<div>	PassPort AM server port.</div>
         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.srchost         </td>
         <td>
            <p>The PassPort AM local network interface for outgoing  connections.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
<div>am.passport.instance_id</div>
         </td>
         <td colspan="1" rowspan="1">
<p colspan="1" rowspan="1">Transfer CFT instance ID for PassPort AM  </p>
            <ul>
               <li colspan="1" rowspan="1">You must determine your Transfer CFT's PassPort instance name. If it does not match the instance name of <b>default</b>, you must add an instance with the correct name.               </li>
               <li colspan="1" rowspan="1">The passport.instance_id corresponds to the 
						instance (An instance name is a unique identifier of the installed instance of the component. Check that PassPort and your Transfer CFT have the SAME instance name) of the CSD that is available in PassPort.                </li>
               <li colspan="1" rowspan="1">In PassPort, you can view this by selecting          <b>Access</b> &gt; <b>Components</b> &gt; <b>Transfer CFT</b> and checking the screen display (default value: default (when you import a component, PassPort assigns it the instance name  <b>default</b> )).               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
<div>am.passport.login </div>
         </td>
         <td colspan="1" rowspan="1">
<div>Transfer CFT login for PassPort AM. This user must exist in PassPort and have an Administrator role. This user represents an application user with which Transfer CFT makes requests.</div>
         </td>
      </tr>
      <tr valign="top">
         <td>
<div>am.passport.password</div>
         </td>
         <td>
<div>Transfer CFT Instance ID Password for PassPort AM, see above. </div>
         </td>
      </tr>
      <tr valign="top">
         <td>
<div>am.passport.superuser</div>
         </td>
         <td>
<p width="81.772%">Enables users to perform any type of action without PassPort AM permission checks. </p>
<p width="81.772%">You <i>must</i> set up at least one superuser. Doing so enables you to deactivate or change the PassPort AM connector configuration if the server is not responding.</p>
            <p>If the  user's name for a session contains a space in the name, you must  insert the backslash <b>\</b> character where the space occurs. </p>
            <p>Example </p>
            <p>If you are defining the users "firstname lastname" and "johndoe" as superusers, you would set the am.passport.superuser parameter value to "firstname<b>\</b> lastname johndoe". </p>
            <p>So for this example, the command is:</p>
            <p>CFTUTIL uconfset id = am.passport.superuser, value = "'firstname\ lastname johndoe'"</p>
         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.use_ssl	         </td>
         <td>
            <p>Enables SSL with PassPort AM. </p>
            <p>The server port is <i>not</i> the same as the default port when using SSL.</p>
         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.ca_cert	         </td>
         <td>Certification Authority (CA) public certificate to authenticate the PassPort AM server.         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.csd_file         </td>
         <td>Transfer CFT Component Security descriptor file for PassPort AM.
The default value is $(cft.install_dir)/extras/PassPort/csd_Transfer_CFT.xml.          </td>
      </tr>
   </tbody>
</table>

1.  Set the access management type parameter to PassPort: am.type = passport

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <span>am.type </span>is the last parameter to set when activating PassPort AM and the first to unset when deactivating it.         </td>
      </tr>
</table>

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

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Definition</th>
      </tr>
   </thead>
      <tr valign="top">
         <td>am.passport.userctrl.check_permissions_on_transfer_execution         </td>
         <td width="81.772%">
            <p><a name="Check"></a>Check the permissions for the execute action on the transfer resource when the  <span>Transfer CFT</span> user control is enabled (<a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/userctrl">USERCTRL</a>=YES). To disable the permission check, set the following parameter to No. The default is Yes.</p>
         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.domain         </td>
         <td width="81.772%">PassPort AM domain.         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.max_connections         </td>
         <td width="81.772%">Maximum number of connections with PassPort.         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.pipe_priority         </td>
         <td width="81.772%">Pipelining priority mode.         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.pipeline_size         </td>
         <td width="81.772%">Maximum number of requests in the pipe for one PassPort.         </td>
      </tr>
      <tr valign="top">
         <td>am.passport.resource_prefix         </td>
         <td width="81.772%">Only EXPERTS may use the resource prefix.         </td>
      </tr>
</table>

## References

A complete set of PassPort documentation is available at [support.axway.com](http://support.axway.com/).

For more information about starting the Transfer CFT UI (Copilot), refer to Starting and Stopping the Copilot UI.

Related topics

[About PassPort AM](..//transfercft/internal_a_m_start_here/about_passport_am)

[PassPort AM CSD](../passport_am_csd)

[Defining user rights Windows](../../../cft_intro_install/windows_install_start_here/windows_install_start_here/running_cft_for_the_first_time_windows/user_rights_and_interface_win)

[Defining user rights Unix](../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/user_rights_and_interface_unix)
