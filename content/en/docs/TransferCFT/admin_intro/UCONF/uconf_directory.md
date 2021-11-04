{
    "title": "UCONF parameters",
    "linkTitle": "UCONF parameters",
    "weight": "270"
}You can download this page as a PDF [here](#).

Viewing the table

If you have trouble viewing the entire table in your browser, click the arrow icon to collapse the left pane TOC.

![](/Images/TransferCFT/collapse.png)

Parameter attributes in lower case

Some uconf values contain logical\_name parameter attributes as part of the value, for example `aws.credentials.<logical_name>.access_key_id`. When processed, the logical\_name is replaced by the parent value, and is systematically converted to lower case.

Example when <span class="code">aws.credientials=<span style="color: #b22222;">Test</span></span>

CFTUTIL listuconf id=aws.credentials.\*

aws.credentials = <span style="color: #b22222;">Test</span>

aws.credentials.<span style="color: #b22222;">test</span>.access\_key\_id =

aws.credentials.<span style="color: #b22222;">test</span>.secret\_access\_key = \*\*\*\*\*\*\*\*

Parameter list

The following table is an exhaustive list of the unified configuration (UCONF) values.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>Do not modify the UCONF dictionary located in the home directory unless specifically directed to do so by Axway.         </td>
      </tr>
   </tbody>
</table>

**UCONF flags legend**

-   EXPERT: Extra care must be taken; only advanced users should change this value.
-   RECONFIG: Can be changed dynamically with a CFTUTIL RECONFIG type=UCONF, and a notification is displayed in the LOG.
-   IRECONFIG: Can be changed dynamically with a CFTUTIL RECONFIG type=UCONF, but no notification is displayed in the LOG.
-   RUNTIME MUTABLE READ\_ONLY: Cannot be changed by a user.
-   EXPERIMENTAL: Unsupported feature.
-   OBSOLETE: No longer used.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>By default, all UCONF parameters are static and require a restart. Only parameters with the RECONFIG or IRECONFIG flags are dynamic; for these dynamic parameters only you can use the <span class="code">reconfig </span>command and no restart is required.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>Name         </td>
         <td>Description         </td>
         <td>Type         </td>
         <td>Restriction         </td>
         <td>Default         </td>
         <td>Platform         </td>
         <td>Flags         </td>
      </tr>
      <tr>
         <td><p>acceleration.enable</p>         </td>
         <td><p>Enables the acceleration.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp</p>         </td>
         <td><p>List of CFTNET objects that implement the pTCP acceleration.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp.&lt;logical_name&gt;.buffer_size</p>         </td>
         <td><p>Internal acceleration buffer size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10240000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp.&lt;logical_name&gt;.nb_connections</p>         </td>
         <td><p>Number of parallel connections.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp.&lt;logical_name&gt;.packet_size</p>         </td>
         <td><p>TCP packet size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp.&lt;logical_name&gt;.session_affinity_delay</p>         </td>
         <td><p>"Dispatches to the same node within this delay, in milliseconds (multinode only)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.ptcp.&lt;logical_name&gt;.session_init_timeout</p>         </td>
         <td><p>"Determines the timeout value, in milliseconds, for establishing pTCP session."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt</p>         </td>
         <td><p>List of CFTNET objects that implement the UDT acceleration.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.buffer_size</p>         </td>
         <td><p>Internal UDT buffer size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10240000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.fc</p>         </td>
         <td><p>Maximum window size in packets.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>25600</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.linger</p>         </td>
         <td><p>Linger time on close() call.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>180</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.max_bw</p>         </td>
         <td><p>Maximum bandwidth that one single UDT connection can use in bytes/second. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.mss</p>         </td>
         <td><p>Maximum packet size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1500</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.rcv_buf</p>         </td>
         <td><p>UDT receiver buffer size limit in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10240000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.snd_buf</p>         </td>
         <td><p>UDT sender buffer size limit in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10240000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.udp_rcv_buf</p>         </td>
         <td><p>UDP socket receiver buffer size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1024000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>acceleration.udt.&lt;logical_name&gt;.udp_snd_buf</p>         </td>
         <td><p>UDP socket sender buffer size in bytes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1024000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.cg.organization</p>         </td>
         <td><p>Default Organisation when CG is the Access Management.Access Management type used.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:35"</p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.exit.check_login</p>         </td>
         <td><p>Checks login with Access Management exit.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.exit.check_permissions</p>         </td>
         <td><p>Checks permissions with Access Management exit.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.exit.custom</p>         </td>
         <td><p>Customer configuration parameters available in customizable Access Management exit.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>tracelevel rbac_fname ldap_host ldap_port ldap_base ldap_login_dn_format ldap_get_roles_filter (not MVS) | tracelevel rbac_fname ldap_host ldap_port ldap_base ldap_login_dn_format ldap_get_roles_filter safclass instance_id (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.exit.libpath</p>         </td>
         <td><p>Location of Access Management exit library.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"none (not MVS, not VMS) | CFTDXAM (MVS) | CFT_EXE:AM_EXIT.EXE (VMS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.group_database</p>         </td>
         <td><p>Group database where group members are defined.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'system' (not MVS) | 'file' (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.group_database.fname</p>         </td>
         <td><p>The file where group members are defined. Used only when am.internal.group_database equals file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.mvs.group_fname) (MVS)</p>         </td>
         <td><p>"MVS, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.libpath</p>         </td>
         <td><p>Location of Private Access Management exit library. Do not modify this parameter!</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install_dir)/lib/libcftpexam.so (UNIX) | $(cft.install_dir)/lib/libcftpexam.a (AIX) | $(cft.install_dir)/lib/libcftpexam.sl (HPUX-PARISC) | $(cft.install_dir)/bin/cftpexam.dll (NT) | CFTDXIN (MVS) | LIBCFTPEXA (OS400) | CFT_EXE:AMTYPE_INTERNAL.EXE (VMS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.persistence_timeout</p>         </td>
         <td><p>Delay in seconds between updating the list of groups that a user belongs to.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>300</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.role.admin</p>         </td>
         <td><p>Admin role and groups mapping. This role enables you to perform all administrative tasks.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>ADMIN (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.role.application</p>         </td>
         <td><p>Application role and groups mapping. This role enables application to send transfers.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>TRANSFER (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.role.designer</p>         </td>
         <td><p>Designer role and groups mapping. This role enables you to manage flows.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>DESIGNER (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.role.helpdesk</p>         </td>
         <td><p>"Help Desk role and groups mapping. This role enables you to view the log, transfers and configuration."</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>OPERATOR (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.role.partnermanager</p>         </td>
         <td><p>Partner Manager role and groups mapping. This role enables you to create and manage partners.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>PARTNER (MVS)</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400, VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.internal.safclass</p>         </td>
         <td><p>The specified class must be defined in the class descriptor table.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.ca_cert</p>         </td>
         <td><p>List of Certification Authority (CA) public certificates to authenticate PassPort AM server.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>"$(cft.runtime.confpki_dir)passportCA.pem (not MVS, not OS400) | $(cft.runtime.confpki_dir)CERTIF(PAMCAPEM) (MVS) | *LIBL/PASSPRTPEM (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.cg.organization</p>         </td>
         <td><p>Name of the Central Governance Organization in Passport AM.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.connection_timeout</p>         </td>
         <td><p>Connection timeout to PassPort AM.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>120</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.csd_file</p>         </td>
         <td><p>Transfer CFT Component Security Descriptor file for PassPort AM.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install.extrasPS_dir)csd_Transfer_CFT_CG.xml (not MVS, not OS400) | $(cft.install.extrasPS_dir)XMLLIB(CSDCG) (MVS) | *LIBL/CSDCFTCG (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.domain</p>         </td>
         <td><p>PassPort AM domain.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'Synchrony'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.hostname</p>         </td>
         <td><p>PassPort AM server hostname or IP address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'localhost'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.instance_id</p>         </td>
         <td><p>Application instance ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'default' | '$(cft.instance_group).$(cft.instance_id)' (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.login</p>         </td>
         <td><p>Passport AM application login.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.max_connections</p>         </td>
         <td><p>Maximum number of PassPort AM connections.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.password</p>         </td>
         <td><p>PassPort AM application password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.persistency.cftsxpam.enable</p>         </td>
         <td><p>Enable execution of CFTSXPAM that updates the Passport AM cache.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.persistency.check_interval</p>         </td>
         <td><p>Interval in seconds between two checks of access management updates.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>600</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.persistency.enable</p>         </td>
         <td><p>Enables persistency support for PassPort AM.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.persistency.fname</p>         </td>
         <td><p>Persistent cache file name for PassPort AM.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/CFTAM (not MVS, not OS400, not VMS) | $(cft.runtime_dir)DATA]CFTAM (VMS) | $(cft.runtime_dir)CFTAM (MVS) | *LIBL/CFTAM (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.persistency.lock_fname</p>         </td>
         <td><p>Persistent cache lock file name for PassPort AM.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/CFTAM.lck (not VMS, not OS400) | $(cft.install_dir)data]CFTAM.lck (VMS) | *LIBL/CFTAMLCK (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.pipe_priority</p>         </td>
         <td><p>"Pipelining priority mode (1 pipeline priority, 0 new connection priority)."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.pipeline_size</p>         </td>
         <td><p>Maximum number of requests in pipe for a single PassPort AM connection.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'2'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.port</p>         </td>
         <td><p>PassPort AM server port number.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>6090</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.resource_prefix</p>         </td>
         <td><p>PassPort AM resource prefix.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'Synchrony:TransferCFT'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.srchost</p>         </td>
         <td><p>Local network interface used by the AM Passport connector for outgoing connection.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.superuser</p>         </td>
         <td><p>Users for which no PassPort AM rights check is done.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(CFT$USER) (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.trace</p>         </td>
         <td><p>Passport AM trace level (from 0 to 5).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.use_ssl</p>         </td>
         <td><p>Enable SSL cryptography when connecting to PassPort AM server.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.passport.userctrl.check_permissions_on_transfer_execution</p>         </td>
         <td><p>Check permissions for CREATE and EXECUTE actions on the TRANSFER resource when the system user control is enabled (CFTPARM USERCTRL=YES).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.persistency.fname</p>         </td>
         <td><p>"Persistent users and roles cache file name for AM with CG, Keycloak, LDAP"</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/CFTAMUR (not MVS, not OS400, not VMS) | $(cft.runtime_dir)DATA]CFTAMUR (VMS) | $(cft.runtime_dir)CFTAMUR (MVS) | *LIBL/CFTAMUR (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.saml.client_id</p>         </td>
         <td><p>Value used as issuer on SAML requests. This should match the Identity Provider configuration.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(cft.instance_id)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.saml.idp.cert_id</p>         </td>
         <td><p>Identifier of the certificate (stored in the internal PKI base) used to verify the SAML Identity Provider server's signatures.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.saml.idp.logout_service</p>         </td>
         <td><p>Endpoint for SAML requests of type LogoutRequest (HTTP-Redirect binding).\</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(am.saml.idp.sign_on_service)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.saml.idp.sign_on_service</p>         </td>
         <td><p>Endpoint for SAML requests of type AuthnRequest (HTTP-Redirect binding).\</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.superuser</p>         </td>
         <td><p>Users for which no CG AM rights check is done.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(am.passport.superuser) (not VMS) | $(CFT$USER) (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>am.type</p>         </td>
         <td><p>Access Management type used.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: none cft passport exit internal cg fc saml</p>         </td>
         <td><p>'none'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials</p>         </td>
         <td><p>List of parameters for AWS.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.access_key_id</p>         </td>
         <td><p>"Access Key ID (a 20-character, alphanumeric sequence)."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.acl</p>         </td>
         <td><p>ACL policy to apply on the created file while uploading a file to AWS.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: private public-read public-read-write authenticated-read aws-exec-read bucket-owner-read bucket-owner-full-control</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.encryption_key_id</p>         </td>
         <td><p>Key identifier to use for sse-kms encryption.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.encryption_type</p>         </td>
         <td><p>"Server side encryption type. If empty, there is no encryption."</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: none sse-s3 sse-kms</p>         </td>
         <td><p>none</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.proxy_host</p>         </td>
         <td><p>Proxy IP address or FQDN.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.proxy_password</p>         </td>
         <td><p>Proxy password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.proxy_port</p>         </td>
         <td><p>Proxy port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.proxy_scheme</p>         </td>
         <td><p>Proxy scheme to use.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: http https</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.proxy_username</p>         </td>
         <td><p>Proxy user name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.region</p>         </td>
         <td><p>"Region to use, overrides parsing result of WORKINGDIR and config/env settings."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>aws.credentials.&lt;logical_name&gt;.secret_access_key</p>         </td>
         <td><p>Secret Access Key (a 40-character sequence).</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.accnt.enable_extended_byte_fields</p>         </td>
         <td><p>Enables fields FBYTE_EXTENDED and NBYTE_EXTENDED (length=15) of the Accounting file.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.api.catalog.cache_size</p>         </td>
         <td><p>Size of the catalog cache for API calls.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>20</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.api.waitcat.scantime_scale</p>         </td>
         <td><p>Scantime scale (1/n seconds).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cft_charsets</p>         </td>
         <td><p>Adds a character set ID to the existing list of charsets.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>IRECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.afname</p>         </td>
         <td><p>Overrides the CFTACNTA logical name used for the alternate Accounting file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.accnt_dir)cftaacnt (not VMS, not MVS) | $(cft.runtime.accnt_dir)cftaccnt.loga (VMS) | $(cft.runtime.accnt_dir)ACCNT2 (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.afname.atts</p>         </td>
         <td><p>Attributes of the alternate Accounting file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'$(cft.cftaccnt.fname.atts)' (MVS, OS400)"</p>         </td>
         <td><p>"MVS, OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.fname</p>         </td>
         <td><p>Overrides the CFTACNT logical name used for the Accounting file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.accnt_dir)cftaccnt (not VMS, not MVS) | $(cft.runtime.accnt_dir)cftaccnt.log (VMS) | $(cft.runtime.accnt_dir)ACCNT1 (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftaccnt.fname.atts</p>         </td>
         <td><p>Attributes of the Accounting file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'format=v24' (OS400) | 'format=v24,fblksize=14336,fspace=3000' (MVS)"</p>         </td>
         <td><p>"MVS, OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.auto_expand_max_size</p>         </td>
         <td><p>Maximum size in record for automatic expansion.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1000000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.auto_expand_percent</p>         </td>
         <td><p>Expansion factor.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.default_size</p>         </td>
         <td><p>Default size in records used when creating a catalog with cftinit.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.enable_deprecated_blknum</p>         </td>
         <td><p>"Enables BLKNUM as a catalog management command parameter (LISTCAT, DELETE, START, etc.). Do not enable BLKNUM when using the multi-node feature."</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcat.fname</p>         </td>
         <td><p>Replaces the CFTCATA logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)cftcata (not VMS, not MVS) | $(cft.runtime.data_dir)CFTCATA.REL (VMS) | $(cft.runtime.data_dir)CATALOG (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.default_size</p>         </td>
         <td><p>Default size used when creating a COM file with cftinit.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom.fname</p>         </td>
         <td><p>Overrides the CFTCOM logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)cftcom (not VMS, not MVS) | $(cft.runtime.data_dir)cftcom.rel (VMS) | $(cft.runtime.data_dir)COM (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftcom_node.fname</p>         </td>
         <td><p>Overrides the CFTCOM by node logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)cftcom (not VMS, not MVS) | $(cft.runtime.data_dir)cftcom.rel (VMS) | $(cft.cftcom.fname) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.afname</p>         </td>
         <td><p>Replaces the CFTLOGA logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.cftlog.fname) (not MVS) | $(cft.runtime.log_dir)LOG2 (MVS)</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.afname.atts</p>         </td>
         <td><p>Attributes used to create the Log file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(cft.cftlog.fname.atts)' (MVS)</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.backup_count</p>         </td>
         <td><p>Number of backups for Transfer CFT log files.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.exec_timeout</p>         </td>
         <td><p>Timeout in seconds for executing a switchlog.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.fname</p>         </td>
         <td><p>Overrides the CFTLOG logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.log_dir)cftlog (not VMS, not MVS) | $(cft.runtime.log_dir)cftlog.log (VMS) | $(cft.runtime.log_dir)LOG1 (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.fname.atts</p>         </td>
         <td><p>Attributes used to create the Log file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'fspace=3000,fblksize=27904' (MVS)"</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.switch_on_start</p>         </td>
         <td><p>Enable/disable the LOG switch when CFT start</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.switch_on_stop</p>         </td>
         <td><p>Condition if the log files must be switched at the end of the Transfer CFT stop procedure.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftlog.time_precision</p>         </td>
         <td><p>Define time precision: 1s 10ms 100ms.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>enum: 1 10 100</p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.fname</p>         </td>
         <td><p>Overrides the CFTPARM logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)cftparm (not VMS, not MVS) | $(cft.runtime.data_dir)cftparm.inx (VMS) | $(cft.runtime.data_dir)PARM (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.habfname</p>         </td>
         <td><p>Overrides the CFTHINI logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)sec.ini (not MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.keyfname</p>         </td>
         <td><p>Transfer CFT key filename.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)cft.key (not MVS) | $(cft.runtime.conf_dir)UPARM(PRODKEY) (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.partfname</p>         </td>
         <td><p>Overrides the CFTPART logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)cftpart (not VMS, not MVS, not UNIX, not NT) | $(cft.runtime.data_dir)cftpart.inx (VMS) | $(cft.runtime.data_dir)PART (MVS) | $(cft.runtime.data_dir)cftparm (UNIX, NT)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.pkifname</p>         </td>
         <td><p>Overrides the CFTPKU logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)CFTPKU (not MVS, not UNIX, not NT) | $(cft.runtime_dir)PKIFILE (MVS) | $(cft.runtime.data_dir)cftparm (UNIX, NT)"</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.cftparm.secparm</p>         </td>
         <td><p>Overrides the CFTHPARM logical name.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.data_dir)secparm (not VMS) | $(cft.runtime.data_dir)secparm.dat (VMS)</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.char_directory_protect</p>         </td>
         <td><p>"Overrides the default character used to specify a directory. No value means the default character '+', a blank ' ' means no control. Set to another character to override the default one."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.client.cftcoms.ssl_id</p>         </td>
         <td><p>Default identifier of CFTSSL client object used by CFTUTIL to connect to CFTCOMS server if the SSL parameter of the CONFIG command is not specified.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.default_idf.enable</p>         </td>
         <td><p>Enables the default IDF to use when the transfer request IDF is not explicitly defined by a CFTRECV or CFTSEND command.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.dirdepth</p>         </td>
         <td><p>Lists subdirectory files.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.fips.enable_compliance</p>         </td>
         <td><p>Enables FIPS compliance (Yes/No).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>"not MVS, not VMS, not HPUX-PARISC-64"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.fips.libcrypto</p>         </td>
         <td><p>OpenSSL libcrypto library location.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install_dir)/lib/libcrypto.so.1.0.0 (UNIX) | $(cft.install_dir)/lib/libcrypto.a(libcrypto.so.1.0.0) (AIX) | $(cft.install_dir)/lib/libcrypto.sl.1.0.0 (HPUX-PARISC) | $(cft.install_dir)/bin/libeay32.dll (NT)</p>         </td>
         <td><p>"not MVS, not VMS, not HPUX-PARISC-64"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.full_hostname</p>         </td>
         <td><p>Full hostname.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(cftfullhostname)' (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.backup_processor</p>         </td>
         <td><p>backup processor on which CFT is started (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:15"</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.cftwrk</p>         </td>
         <td><p>Default Guardian pathname for TACL and Netbatch procedures.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:27"</p>         </td>
         <td><p> </p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.collector</p>         </td>
         <td><p>Collector</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.hometerm</p>         </td>
         <td><p>CFT Home Terminal.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:2, max length:35"</p>         </td>
         <td><p> </p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.attachment_set</p>         </td>
         <td><p>Netbatch attachmentset.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:1, max length:8"</p>         </td>
         <td><p>NBASCFTLI</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.jobname_prefix</p>         </td>
         <td><p>"Prefix for Netbatch JOB Name, Suffix composed of last carcaters of file created to contain the input TCAL statements."</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:4"</p>         </td>
         <td><p>ZBBT</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.output</p>         </td>
         <td><p>Netbatch output file (default $S.ABTZ).</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:3, max length:35"</p>         </td>
         <td><p>'$S.#ABTZ'</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.priority</p>         </td>
         <td><p>Netbatch Run priority (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:199"</p>         </td>
         <td><p>90</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.process</p>         </td>
         <td><p>Netbatch process name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:2, max length:5"</p>         </td>
         <td><p>$ZBAT</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.selpri</p>         </td>
         <td><p>Netbatch SELPRI (default 4).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:7"</p>         </td>
         <td><p>4</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.nonstop</p>         </td>
         <td><p>Enables Mode NonStop (Yes/No).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.priority</p>         </td>
         <td><p>CFT priority (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:199"</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.process_name_prefix</p>         </td>
         <td><p>Guardian Process name prefix (2 caracters maximum).</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:2"</p>         </td>
         <td><p>LA</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.processor</p>         </td>
         <td><p>processor on which CFT is started (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:15"</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.backup_processor</p>         </td>
         <td><p>backup processor on which TACL is started (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.hometerm</p>         </td>
         <td><p>TACL Home Terminal.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:2, max length:35"</p>         </td>
         <td><p>$ZHOME</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.output</p>         </td>
         <td><p>TACL output file (default $S.ABTT).</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:3, max length:35"</p>         </td>
         <td><p>'$S.#ABTT'</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.priority</p>         </td>
         <td><p>TCAL priority (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:199"</p>         </td>
         <td><p>90</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.processor</p>         </td>
         <td><p>processor on which TACL is started (default -1).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tcpip_resolver_name</p>         </td>
         <td><p>TCPIP alternate resolver file name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:35"</p>         </td>
         <td><p> </p>         </td>
         <td><p>HP_NONSTOP</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.icm.timestamp</p>         </td>
         <td><p>Add a timestamp before CFTUTIL messages.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.idparm</p>         </td>
         <td><p>Default IDPARM used by Transfer CFT.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'IDPARM0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.idt.calculation_mode</p>         </td>
         <td><p>Sets the calculation method for generating the IDT. Possible values are date (calculation based on the current date) and date_with_leapyear (calculation based on the current date considering that the current year is always a leap year).</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: date date_with_leapyear</p>         </td>
         <td><p>'date_with_leapyear'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.inner_charsets</p>         </td>
         <td><p>List of charsets compatible for BOM removal and space padding. For advanced users only.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>IRECONFIG EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.dat_dir</p>         </td>
         <td><p>Transfer CFT installation directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install_dir)/distrib/dat/ (not VMS, not MVS) | $(cft.install_dir)distrib.dat] (VMS) | $(cft.install_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.extrasps_dir</p>         </td>
         <td><p>Directory containing the samples used for PassPort.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install_dir)/extras/PassPort/ (not VMS, not MVS) | $(cft.install_dir)extras.PassPort] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.extrassent_dir</p>         </td>
         <td><p>Directory containing the samples used for Sentinel.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install_dir)/extras/sentinel/ (not VMS) | $(cft.install_dir)extras.sentinel] (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.psenglish_dir</p>         </td>
         <td><p>Directory containing the messages used for PassPort.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install_dir)/distrib/ps/english/ (not VMS) | $(cft.install_dir)distrib.ps.english] (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.tfenglish_dir</p>         </td>
         <td><p>Directory containing the messages used for TrustedFile.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install_dir)/distrib/tf/english/ (not VMS, not MVS) | $(cft.install_dir)distrib.tf.english] (VMS) | $(cft.runtime_dir)PKIMSG (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install.xsr_dir</p>         </td>
         <td><p>Transfer CFT Secure Relay installation directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install_dir)/distrib/xsr/ (not MVS, not VMS) | $(cft.install_dir)distrib.xsr] (VMS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.install_dir</p>         </td>
         <td><p>Transfer CFT installation directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(CFTDIRINSTALL)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.instance_group</p>         </td>
         <td><p>Transfer CFT instance GROUP.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'Production.VMS' (VMS) | 'Production.IBMi' (OS400)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.instance_id</p>         </td>
         <td><p>Transfer CFT instance ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'CFT_$(cft$user)' (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.instance_uid</p>         </td>
         <td><p>Transfer CFT instance unique ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ipv6.disable_connect</p>         </td>
         <td><p>Disables IPv6 connections.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ipv6.disable_listen</p>         </td>
         <td><p>Disables IPv6 for listening.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ipv6.set_ai_numerichost</p>         </td>
         <td><p>Sets AI_NUMERICHOST hint before getaddrinfo() call. Use to prevent API system getaddrinfo from performing unnecessary DNS requests for numeric hostnames.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ipv6.set_ai_numericserv</p>         </td>
         <td><p>Sets AI_NUMERICSERV hint before getaddrinfo() call. Use to prevent API system getaddrinfo from performing unnecessary DNS requests for numeric hostnames.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ipv6.use_ipv4_legacy_resolver</p>         </td>
         <td><p>"Use legacy IPv4 only host and service names resolution API, that is, gethostbyname() and getservbyname()."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.jre.java_binary_path</p>         </td>
         <td><p>Java binary path used to start Transfer CFT jar files.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.jre.loader</p>         </td>
         <td><p>Loads the JRE (Java Runtime Environment).</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install_dir)/distrib/java/CFTJRE.jar</p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.jre.pid_fname</p>         </td>
         <td><p>File containing the JRE Process ID.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)jre.pid</p>         </td>
         <td><p>"NT, UNIX, VMS"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.jre.run.pid</p>         </td>
         <td><p>JRE Process ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'1'</p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.jre.start_options</p>         </td>
         <td><p>JRE start options.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'-Xmx1024m -Dlog4j.configuration=conf/cft-log4j.properties -Dhttp.strictPostRedirect=true -Djdk.http.auth.tunneling.disabledSchemes=""""' (not NT) | '-Xmx512m -Xrs -Dstdout_fname=run/cftjre.out -Dlog4j.configuration=conf/cft-log4j.properties -Dhttp.strictPostRedirect=true -Djdk.http.auth.tunneling.disabledSchemes=""""' (NT)"</p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.listcat_compat</p>         </td>
         <td><p>Condition if the default listcat format does or doesn't include phase and phasestep.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftcom.dispatcher_policy</p>         </td>
         <td><p>Used to dispatch transfers with HOLD state.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: round_robin node_affinity</p>         </td>
         <td><p>'round_robin'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftcom.lock_fname</p>         </td>
         <td><p>Lock file for CFTCOM task in multi-node.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftcom.lck</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftcom.lock_retry_delay</p>         </td>
         <td><p>Delay in seconds for CFTMCOM (multinode master) lock retry delay.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.multi_node.lock_retry_delay)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftcron.lock_fname</p>         </td>
         <td><p>Lock file for cronjobs scheduler task in multi-node.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftcron.lck</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftcron.lock_retry_delay</p>         </td>
         <td><p>Delay in seconds for cftcron lock retry.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.multi_node.lock_retry_delay)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.cftdscan.lock_fname</p>         </td>
         <td><p>Lock file for CFTDSCAN task in multi-node.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)/run/cftdscan.lck (not OS400) | *LIBL/DSCLCK (OS400) | $(cft.runtime_dir)run]cftdscan.lck (VMS)</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.connection_retry_delay</p>         </td>
         <td><p>Delay in seconds for connection retry.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.enable</p>         </td>
         <td><p>Enables the multi-node architecture.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.enable_spurious_log_messages</p>         </td>
         <td><p>"If Yes, shows all log messages for all nodes, even if it is not relevant for each one"</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames</p>         </td>
         <td><p>List of hosts that handle the multi-node architecture.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.control_port</p>         </td>
         <td><p>Control port of (copsmng) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.copcod_local_port</p>         </td>
         <td><p>Connection dispatcher local port in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.copui_client_socket</p>         </td>
         <td><p>Windows socket passing for UI server (copui) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.copui_client_ssl_socket</p>         </td>
         <td><p>Windows ssl socket passing for UI server (copui) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.copui_notification_port</p>         </td>
         <td><p>Notification port for UI server (copui) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.copui_pid</p>         </td>
         <td><p>copui Process ID in multi-node.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.host</p>         </td>
         <td><p>Address (FQDN or IP address) of the host.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.node_manager_local_port</p>         </td>
         <td><p>Node manager local port of (copnman) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.node_manager_port</p>         </td>
         <td><p>Node manager port of (copnman) in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.pid</p>         </td>
         <td><p>Copilot Process ID (copsmng) in multi-node.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.state</p>         </td>
         <td><p>Copilot (copsmng) status in multi-node.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: INITIALIZING STARTING RUNNING STOPPING STOPPED ERROR</p>         </td>
         <td><p>STOPPED</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.&lt;logical_name&gt;.state_timestamp</p>         </td>
         <td><p>Timestamp of the last Copilot status update.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.listen_port_range</p>         </td>
         <td><p>"Defines a port range to use for listening points dedicated to inter-node communication in multi-node. The syntax is startingPort-EndingPort. For example '33000-33100'. If empty, the default Operating System port numbers range is used."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.load_balancer.host</p>         </td>
         <td><p>Load balancer address (FQDN or IP address) used by Central Governance to connect to Transfer CFT UI Server.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.load_balancer.port</p>         </td>
         <td><p>Load balancer port used by Central Governance to connect to Transfer CFT UI Server port dedicated to Central Governance (default 1767).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.lock_retry_delay</p>         </td>
         <td><p>Delay in seconds for cftcron and CFTMCOM (multinode master) lock retry.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>20</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.max</p>         </td>
         <td><p>Maximum number of nodes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>8</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.max_per_host</p>         </td>
         <td><p>Maximum number of nodes (CFTMAIN) per host.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.multi_node.max)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes</p>         </td>
         <td><p>Number of nodes (from 2 to max_nodes)</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>2</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.coms_port</p>         </td>
         <td><p>Internal listening port of COMS server for a node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.configuration_version</p>         </td>
         <td><p>Stamp of the configuration in which Transfer CFT has been started.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.disabling</p>         </td>
         <td><p>Flag set when CFT is disabling.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.host</p>         </td>
         <td><p>Host address of the server where the node is running on.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.hostname</p>         </td>
         <td><p>Hostname of the server where the node is running on.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.jre_pid</p>         </td>
         <td><p>JRE Process ID.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.msg</p>         </td>
         <td><p>Message describing the current startup or shutdown process.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.nodestate</p>         </td>
         <td><p>Node status.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: DISABLED ENABLED_STOPPED ENABLED_STARTED</p>         </td>
         <td><p>DISABLED</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.pid</p>         </td>
         <td><p>CFTMAIN Process ID in multi-node.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.progress</p>         </td>
         <td><p>Indicates the startup or shutdown progress expressed as a percentage.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.prx_port</p>         </td>
         <td><p>Internal listening port of a node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.starting</p>         </td>
         <td><p>Flag set when CFT is starting.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.state</p>         </td>
         <td><p>Transfer CFT status.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: INITIALIZING STARTING RUNNING STOPPING STOPPED ERROR</p>         </td>
         <td><p>STOPPED</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.state_timestamp</p>         </td>
         <td><p>Timestamp of the last Transfer CFT status update.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes.&lt;itemNumber&gt;.stopping</p>         </td>
         <td><p>Flag set when CFT is stopping.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.policy_fname</p>         </td>
         <td><p>"*(*) full name, *(#) node id"</p>         </td>
         <td><p>string                     </p>         </td>
         <td><p> </p>         </td>
         <td><p>'*(*).N*(#)'                              (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.registration.lock_fname</p>         </td>
         <td><p>Lock file for registration task to Central Governance in multi-node.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)regist.lck</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.shared.filesystem.type</p>         </td>
         <td><p>Used to select appropriate consistency enforcement strategy.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: unknown posix nfs cifs</p>         </td>
         <td><p>'unknown'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.sharedidt.enable</p>         </td>
         <td><p>Use global IDT calculation method.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.sharedidt.fname</p>         </td>
         <td><p>Shared file for global IDT calculation in multi-node.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.data_dir)cftsidt</p>         </td>
         <td><p>"NT, UNIX, MVS, OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.start_node.proc_fname</p>         </td>
         <td><p>Procedure to start Transfer CFT nodes.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)INSTALL(MNRMON)</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.start_node.user</p>         </td>
         <td><p>Userid used to start Transfer CFT nodes (lib APF).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.transfer_recovery_retry_delay</p>         </td>
         <td><p>Delay in seconds for transfer recovery retry.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>20</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.transfer_recovery_timeout</p>         </td>
         <td><p>Timeout in seconds for the transfer recovery process.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.check_exec</p>         </td>
         <td><p>"Control procedures submitted Yes:'/', Value:'//* EXEC CFT'."</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: no yes value</p>         </td>
         <td><p>'no'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.copilot.check_apf</p>         </td>
         <td><p>YES indicates Copilot server must be APF-authorized to start.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.monitor.check_apf</p>         </td>
         <td><p>YES indicates Transfer CFT must be APF-authorized to start.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.multi_node.monitor.arm</p>         </td>
         <td><p>Forces REGISTER to ARM in multi-node (if ARM=YES in SGINSTAL).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.allnext</p>         </td>
         <td><p>The % factor applied to the secondary allocation when creating a multi-volume file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>100</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.allone</p>         </td>
         <td><p>The % factor applied to the primary allocation computed to create a multi-volume file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>100</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.allprim</p>         </td>
         <td><p>The % factor applied to the primary allocation computed to create a single volume file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>100</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.allsec</p>         </td>
         <td><p>The % of the primary space used as the secondary allocaion when creating a single volume file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>10</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.arm</p>         </td>
         <td><p>Support of the Automatic Restart Manager.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.blkpds</p>         </td>
         <td><p>Number of blocks allocated while creating a partitioned file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:32760"</p>         </td>
         <td><p>150</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.blksize</p>         </td>
         <td><p>Default BLKSIZE.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:4100, max:32760"</p>         </td>
         <td><p>27920</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.desc</p>         </td>
         <td><p>Value of the Descriptor code field of the WTO.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0x0000'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.dsntype</p>         </td>
         <td><p>Value added to create DF/SMS managed EXTENTED or LARGE files.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: none extpref extreq large</p>         </td>
         <td><p>'none'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.emcsopt</p>         </td>
         <td><p>Option to manage MODIFY command.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: user monitor ignore</p>         </td>
         <td><p>'user'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.formatvb</p>         </td>
         <td><p>Default RECFM (VB).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.hsmasync</p>         </td>
         <td><p>Option to manage synchronously HSM recall.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tdef</p>         </td>
         <td><p>64 b memory for default task (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>16</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tfil</p>         </td>
         <td><p>64 b memory for task TFIL (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tlog</p>         </td>
         <td><p>64 b memory for TLOG task (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>64</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tmai</p>         </td>
         <td><p>64 b memory for main task (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>64</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tpro</p>         </td>
         <td><p>64 b memory for task TPRO (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>64</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64tssl</p>         </td>
         <td><p>64 b memory for task TSSL (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>64</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.m64ttrk</p>         </td>
         <td><p>64 b memory for task TTRK (in MB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>256</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.maxab</p>         </td>
         <td><p>Number of ABENDs allowed by Transfer CFT before shutting done.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>15</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.maxdump</p>         </td>
         <td><p>Number of ABENDs that are th object of a Transfer CFT requested DUMP.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:255"</p>         </td>
         <td><p>2</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.maxtrace</p>         </td>
         <td><p>Limit size for SGTRACE.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>80000</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.mcsopt</p>         </td>
         <td><p>Option to manage MODIFY command.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: check monitor</p>         </td>
         <td><p>'check'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.pdsesharing</p>         </td>
         <td><p>Yes allow simultaneous writing to a PDSE file type.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.routcde</p>         </td>
         <td><p>Value of the ROUTCODE field of the WTO.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0x0008'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.sdsfopt</p>         </td>
         <td><p>Option to manage MODIFY command.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: user monitor ignore</p>         </td>
         <td><p>'user'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.sgtrace</p>         </td>
         <td><p>Initial value of the SGTRACE trace file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:0, max:65535"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.sharecat</p>         </td>
         <td><p>Cache catalog option.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: yes no inact</p>         </td>
         <td><p>'yes'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.subopt</p>         </td>
         <td><p>Option to manage statistic lines for a job submitted.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>enum: 0 1 3</p>         </td>
         <td><p>0</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.tape</p>         </td>
         <td><p>Option to manage support tape files.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: notsup update output</p>         </td>
         <td><p>'UPDATE'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.trace</p>         </td>
         <td><p>Tranfer CFT internal trace size (in KB).</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:4, max:16383"</p>         </td>
         <td><p>128</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.tsoedit</p>         </td>
         <td><p>File support with sequence number in columns 73 to 80.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.volnum</p>         </td>
         <td><p>The maximun number of volumes in a multi-volume allocation.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:127"</p>         </td>
         <td><p>20</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.mvs.sginstal.vsamsufs</p>         </td>
         <td><p>"Suffix for the VSAM (ESDS, KSDS) DATA and INDEX components. (SHORT for .D and .I (default), LONG for .DATA and .INDEX)."</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: SHORT LONG</p>         </td>
         <td><p>'SHORT'</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.cftw_display_log_messages</p>         </td>
         <td><p>Display CFTLOG instead of CFTMAIN in CFTW.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.cftw_trcfilename</p>         </td>
         <td><p>CFTW trace.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftw.trc</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.service_mode</p>         </td>
         <td><p>Transfer CFT is installed in service mode</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.service_name</p>         </td>
         <td><p>Transfer CFT service name in Windows.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>CFTService</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.start_graphmode</p>         </td>
         <td><p>Start Transfer CFT either in graphical mode or not.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.start_timeout</p>         </td>
         <td><p>"Sets the Transfer CFT time limit to start up. If the Transfer CFT status does not change within the delay, it is assumed that the 'cft start' command failed."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.nt.stop_timeout</p>         </td>
         <td><p>"Sets the Transfer CFT time limit to stop. If the Transfer CFT status does not change within the delay, it is assumed that the stop failed."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.output.backup_count</p>         </td>
         <td><p>Number of backups for the output file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.output.backup_time</p>         </td>
         <td><p>Time at which the automatic backup is performed. The time format is HHMMSS.</p>         </td>
         <td><p>time</p>         </td>
         <td><p> </p>         </td>
         <td><p>100</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.output.fname</p>         </td>
         <td><p>Output file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cft.out (not MVS) |   (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.probes.history_size</p>         </td>
         <td><p>Number of probe items in the history for each time class.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>20</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.probes.periodicity</p>         </td>
         <td><p>Time interval between the probe samples in seconds.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.probes.time_classes</p>         </td>
         <td><p>"List of history time classes: the default is 1 second, 10 seconds, 1 minute, 10 minutes..."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>1 10 60 600 3600 21600 86400 604800</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.background_on_start</p>         </td>
         <td><p>Defines if the start-up purge is run in background mode.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.enable_on_start</p>         </td>
         <td><p>Defines if the purge must be run at start-up.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.periodicity</p>         </td>
         <td><p>"Time interval in days (x or xD), in hours (xH) or in minutes (xM) between two automatic purges of entries in the transfers catalog."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.quantity</p>         </td>
         <td><p>Number of transfers to delete in one step.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.rh</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep HOLD receiver transfers before purging. If not set to -1, overrides the RH parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.rt</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep TERMINATED receiver transfers before purging. If not set to -1, overrides the RT parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.rx</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep DONE receiver transfers before purging. If not set to -1, overrides the RX parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.ry</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep POSTPROCESSING receiver transfers before purging. If not set to -1, overrides the RY parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.sh</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep HOLD sender transfers before purging. If not set to -1, overrides the SH parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.st</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep TERMINATED sender transfers before purging. If not set to -1, overrides the ST parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.sx</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep DONE sender transfers before purging. If not set to -1, overrides the SX parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.purge.sy</p>         </td>
         <td><p>"The amount of time in days (x or xD), in hours (xH) or in minutes (xM) to keep POSTPROCESSING sender transfers before purging. If not set to -1, overrides the SY parameter of the CFTCAT object."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.enable</p>         </td>
         <td><p>Enables readline history for CFTUTIL</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.history_fname</p>         </td>
         <td><p>Readline history file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(HOME)/.cft_history (UNIX) | %APPDATA%\cft\CftutilHistory.txt (NT)</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.history_size</p>         </td>
         <td><p>Readline history size.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>500</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.readline.pkihistory_fname</p>         </td>
         <td><p>Readline pki history file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(HOME)/.cft_pkihistory (UNIX) | %APPDATA%\cft\CftPkiUtilHistory.txt (NT)</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.configuration_version</p>         </td>
         <td><p>Stamp of the configuration in which Transfer CFT has been started.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.idparm</p>         </td>
         <td><p>Last IDPARM used by Transfer CFT.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'IDPARM0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.maxtrans</p>         </td>
         <td><p>Last maxtrans used by Transfer CFT.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.msg</p>         </td>
         <td><p>Message describing the current startup or shutdown process.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.pid</p>         </td>
         <td><p>CFTMAIN Process ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.pid_fname</p>         </td>
         <td><p>File containing the CFTMAIN Process ID.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.run_dir)cft.pid (not MVS, not OS400)"</p>         </td>
         <td><p>"NT, UNIX, VMS, OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.progress</p>         </td>
         <td><p>Indicates the startup or shutdown progress expressed as a percentage.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.state</p>         </td>
         <td><p>Transfer CFT status.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: INITIALIZING STARTING RUNNING STOPPING STOPPED ERROR</p>         </td>
         <td><p>'STOPPED'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.run.state_timestamp</p>         </td>
         <td><p>Timestamp of the last Transfer CFT status update.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.accnt_dir</p>         </td>
         <td><p>Directory containing the accounting files.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/accnt/ (not VMS, not MVS) | $(cft.runtime_dir)accnt] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.conf_dir</p>         </td>
         <td><p>Directory containing the sample configuration files.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/conf/ (not VMS, not MVS) | $(cft.runtime_dir)conf] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.confpki_dir</p>         </td>
         <td><p>Directory containing the certificates.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/conf/pki/ (not VMS, not MVS) | $(cft.runtime_dir)conf.pki] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.conftf_dir</p>         </td>
         <td><p>Directory containing the sample TrustedFile configuration.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/conf/tf/ (not VMS, not MVS) | $(cft.runtime_dir)conf.tf] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.crypto_dir</p>         </td>
         <td><p>Directory containing the Transfer CFT cryptographic data.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/crypto/ (not VMS, not MVS) | $(cft.runtime_dir)data.crypto] (VMS) | $(cft.runtime_dir)CRYPTO (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.data_dir</p>         </td>
         <td><p>Directory containing the Transfer CFT databases.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/ (not VMS, not MVS) | $(cft.runtime_dir)data] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.datatf_dir</p>         </td>
         <td><p>Working directory for TrustedFile.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/data/tf/ (not VMS, not MVS) | $(cft.runtime_dir)data.tf] (VMS) | $(cft.runtime_dir)TF. (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.log_dir</p>         </td>
         <td><p>Directory containing the log files.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/log/ (not VMS, not MVS) | $(cft.runtime_dir)log] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.run_dir</p>         </td>
         <td><p>Directory containing the run-time files.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/run/ (not VMS, not MVS) | $(cft.runtime_dir)run] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.traces_dir</p>         </td>
         <td><p>Directory containing the traces files.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/traces/ (not VMS, not MVS) | $(cft.runtime_dir)traces] (VMS) | $(cft.runtime_dir) (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime.xsr_dir</p>         </td>
         <td><p>Transfer CFT Secure Relay run-time directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.runtime_dir</p>         </td>
         <td><p>Transfer CFT runtime directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(CFTDIRRUNTIME)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.sched.partner_policy</p>         </td>
         <td><p>"Defines scheduling partner policy, either round robin or FIFO."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'round_robin'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.scheduled_values</p>         </td>
         <td><p>List of scheduled aliases. Allows user to schedule a temporary value of a specified parameter.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.scheduled_values.&lt;logical_name&gt;.delay</p>         </td>
         <td><p>Delay using the format 'MM:HH'. This is the length of time during which the value can be changed.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>0:00</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.scheduled_values.&lt;logical_name&gt;.id</p>         </td>
         <td><p>The configuration entity id (uconf parameter) that you want to provide scheduling for.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.scheduled_values.&lt;logical_name&gt;.start_time</p>         </td>
         <td><p>Start time using the format 'MM:HH:DAYS_OF_THE_WEEK'. This is the begin time for when a value switches from its existing value to the temporary value</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>00:00:*</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.scheduled_values.&lt;logical_name&gt;.value</p>         </td>
         <td><p>Temporary value. This value overrides the existing configured value of the defined uconf parameter.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.secure_open_mode</p>         </td>
         <td><p>Refuse transfer in open mode when fname contains '\..\' or '/../' after substitution.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.seed.enable_internal</p>         </td>
         <td><p>Enables internal randomized for SSL SEED.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No (not OS400) | Yes (OS400)</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.authentication_method</p>         </td>
         <td><p>Server Authentication method (used by COMS and RPASSWD/SPASSWD).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'none'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos</p>         </td>
         <td><p>Number of class-of-service.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.0</p>         </td>
         <td><p>#ERROR</p>         </td>
         <td><p>#ERROR</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.comment</p>         </td>
         <td><p>User comment that describes the class-of-service.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.max_rate_in</p>         </td>
         <td><p>Maximum rate in KBytes of incoming data for that class-of-service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.max_rate_out</p>         </td>
         <td><p>Maximum rate in KBytes of outgoing data for that class-of-service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.parent</p>         </td>
         <td><p>Parent class-of-service.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.session_max_rate_in</p>         </td>
         <td><p>Maximum rate in KBytes of incoming data for sessions under that class-of-service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.session_max_rate_out</p>         </td>
         <td><p>Maximum rate in KBytes of outgoing data for sessions under that class-of-service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.weight_in</p>         </td>
         <td><p>Use to compute the nominal rate of incoming data for this class of service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos.&lt;itemNumber&gt;.weight_out</p>         </td>
         <td><p>Use to compute the nominal rate of outgoing data for this class of service. -1 means unlimited.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos_requester_default</p>         </td>
         <td><p>Default class-of-service for requester mode transfers.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.cos_server_default</p>         </td>
         <td><p>Default class-of-service for server mode transfers.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.delay</p>         </td>
         <td><p>Bandwidth control granularity (in microsecond) : the amount of time between refreshing token bucket.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1000000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.enable</p>         </td>
         <td><p>Enables the network bandwidth used for incoming and outgoing data in flows.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.enable_borrowing</p>         </td>
         <td><p>Enables bandwidth borrowing (passive borrowing).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.bandwidth.smoothing_factor</p>         </td>
         <td><p>"The bandwidth smoothing factor optimizes resources to flatten, or smooth, bandwidth usage. Values range from 1 to 10, where 1 is the smoothest and 10 may result in irregular bandwidth usage."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.catalog.cache_size</p>         </td>
         <td><p>Size of the catalog cache.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.catalog.sync.enable</p>         </td>
         <td><p>Enables sync at each catalog flush.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.cftcoms.authentication_enable</p>         </td>
         <td><p>Enables synchronous communication authentication.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.cftcoms.max_connection</p>         </td>
         <td><p>The maximum number of connections.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>256</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.com.multinode_watchperiod</p>         </td>
         <td><p>Interval in seconds between two checks of Transfer CFT nodes status.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>50</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.com.rescan.enable</p>         </td>
         <td><p>Enables file communication rescan.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.com.rescan.wscan_factor</p>         </td>
         <td><p>"If rescan is enabled, rescan the entire COM file every WSCAN times this factor."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>50</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.delayed_update</p>         </td>
         <td><p>Performance parameter where the delay is the number of seconds before next catalog flush.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.event_queue_length</p>         </td>
         <td><p>Length of the internal events queue. The maximum number of events handled in one internal iteration.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.exec_as_user</p>         </td>
         <td><p>"Execute transfer processing (pre, post, and ack processing) on the behalf of the user (CFTSEND/CFTRECV)."</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>"No (NT, UNIX) | Yes (MVS)"</p>         </td>
         <td><p>"NT, UNIX, MVS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.fil.main_loop_delay</p>         </td>
         <td><p>"If this value is not 0, add delay in main loop in microseconds."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.force_heterogeneous_mode</p>         </td>
         <td><p>Force heterogeneous mode for group file transfers. Replace the deprecated environment variable: CFTSFMCPY.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>"NT, UNIX"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.log.exclude_filters</p>         </td>
         <td><p>List of logical identifiers. Allows user to exclude messages from the CFTLOG according to matching filters.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>filter1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.log.exclude_filters.&lt;logical_name&gt;.comment</p>         </td>
         <td><p>Free comment.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.log.exclude_filters.&lt;logical_name&gt;.pattern</p>         </td>
         <td><p>Pattern of the log message to exclude. The wildcard '*' can be used for the pattern.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.max_processing_scripts</p>         </td>
         <td><p>"Set to a non-zero integer to define the maximum number of processing scripts, other than EXECE, that can be executed in parallel. Zero (0) disables the feature."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.max_session</p>         </td>
         <td><p>Maximum number of simultaneous sessions.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.maxtrans</p>         </td>
         <td><p>Overrides the maxtrans of CFTPARM object (The maximum authorized number of transfers in parallel) parameter.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0 (not UNIX) | $(cft.unix.active_trans) (UNIX)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.nrdp.conn_retry_delay_max</p>         </td>
         <td><p>Retry delay max in seconds when network resource depletion is detected.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>max:60</p>         </td>
         <td><p>30</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.nrdp.conn_retry_delay_min</p>         </td>
         <td><p>Retry delay min in seconds when network resource depletion is detected.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>min:2</p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.nrdp.enable</p>         </td>
         <td><p>Enable prevention of network resource depletion.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.parent_transfer.error_management_policy</p>         </td>
         <td><p>Error management policy for parent transfer request. IMMEDIATE: The parent transfer error occurs immediately if a child transfer is in error. PHASECOMPLETED: The parent transfer error occurs only after the current phase is completed.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: IMMEDIATE PHASECOMPLETED</p>         </td>
         <td><p>'IMMEDIATE'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.parm.cache_size</p>         </td>
         <td><p>Cache size in number of entries for the PARM and PART databases. The zero value disables the cache.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:0, max:10000"</p>         </td>
         <td><p>5000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.parm.cache_timeout</p>         </td>
         <td><p>"Timeout in seconds, that specifies the PARM/PART cache expiration. The zero value disables the expiration."</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:0, max:86400"</p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.processing_scripts_variables_blacklist</p>         </td>
         <td><p>"POSIX Regular Extended expression that defines forbidden characters. These characters should not be used in symbolic variables, \"</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'`|\$\(|;|&amp;|\|' (UNIX) | '&amp;' (NT)</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.read_buffer_size</p>         </td>
         <td><p>"Read buffer size for transferred sequential files (-1: Auto, 0: no buffer, n: buffer size)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>"NT, UNIX, OS400"</p>         </td>
         <td><p>EXPERT IRECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.send_abort_on_shut</p>         </td>
         <td><p>Sends protocol ABORT on CFT shut if set to Yes.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.tcp.max_count_to_log_incoming_silent_connections</p>         </td>
         <td><p>The maximum number of incoming silent connections to reach before displaying a message in the log. Enter 0 to disable.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.tcp.stat.log.interval</p>         </td>
         <td><p>Interval in seconds between LOG of TCP statistics and counters.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.transfer.max_files_listed</p>         </td>
         <td><p>Maximum number of files when sending a group of files in heterogeneous mode or when listing the contents of a folder. A zero value disables the limit.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>min:0</p>         </td>
         <td><p>100000</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.transfer.raise_error_when_exec_not_found</p>         </td>
         <td><p>"Raise an error when the defined procedure script is not found (i.e. the PHASESTEP is set to K, with DIAGI=155 and DIAGP=NO EXEC). This parameter is applicable to post-processing (EXEC and EXECE) and ack-processing (ACKEXEC)."</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.transfer.rrename.max_retries</p>         </td>
         <td><p>Maximum number of retries.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.transfer.rrename.retry_delay</p>         </td>
         <td><p>Delay in seconds between two retries for rename.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.transfer.tcp.listen_backlog</p>         </td>
         <td><p>Sets the TCP listen backlog size (value 0 means SO_MAXCONN).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0 (not NT) | 20 (NT)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.server.write_buffer_size</p>         </td>
         <td><p>"Write buffer size for transferred sequential files (-1: Auto, 0: no buffer, n: buffer size)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>"NT, UNIX, OS400"</p>         </td>
         <td><p>EXPERT IRECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cft.short_hostname</p>         </td>
         <td><p>Hostname.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(UCX$INET_HOST)' (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ssl.version_max</p>         </td>
         <td><p>Maximum SSL version allowed by Transfer CFT monitor for business flows.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ssl_3.0 tls_1.0 tls_1.1 tls_1.2</p>         </td>
         <td><p>'tls_1.2'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.ssl.version_min</p>         </td>
         <td><p>Minimum SSL version allowed by Transfer CFT monitor for business flows.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ssl_3.0 tls_1.0 tls_1.1 tls_1.2</p>         </td>
         <td><p>'$(ssl.version_min)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.state_compat</p>         </td>
         <td><p>"Defines if backward compatibility is enabled, with either the use of phase and phasestep or the formerly used."</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.synchrony_dir</p>         </td>
         <td><p>Synchrony installation directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.cftext</p>         </td>
         <td><p>Condition if uconf configuration is extracted using CFTUTIL CFTEXT TYPE=ALL.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.default_fname</p>         </td>
         <td><p>Path to uconf (unified configuration) default database.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install.dat_dir)cftuconf-common.dat (not MVS) | DD:DEFAULT (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.dictionary_version</p>         </td>
         <td><p>Version of the UCONF dictionary file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'[CFT_VERSION] SP[CFT_SP]'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>READ_ONLY</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.instance_fname</p>         </td>
         <td><p>Path to uconf (unified configuration) instance repository.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.data_dir)cftuconf.dat</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.instance_version</p>         </td>
         <td><p>Version of the UCONF instance file.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>READ_ONLY</p>         </td>
      </tr>
      <tr>
         <td><p>cft.uconf.runtime_fname</p>         </td>
         <td><p>Path to uconf (unified configuration) runtime instance repository.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftuconf-run.dat (not MVS) | DD:UCONFRUN (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.cftsu.afunix</p>         </td>
         <td><p>Sets the AF_UNIX file for CFTSU.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)SCFTSU</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.cftsu.fname</p>         </td>
         <td><p>Specify the absolute pathname to the cftsu to execute.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.cftsu.isservice</p>         </td>
         <td><p>Use CFTSU as a service.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.group_fname</p>         </td>
         <td><p>Group filename for xfbadmutil.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)group</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.group_temp</p>         </td>
         <td><p>Temporary group filename for xfbadmutil.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)groupXXXXXX</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.parse_file_name_suffix</p>         </td>
         <td><p>Extract the suffix from filenames (Windows behavior).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.passwd_fname</p>         </td>
         <td><p>Password filename for xfbadmutil</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)passwd</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.passwd_temp</p>         </td>
         <td><p>Temporary password filename for xfbadmutil.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conf_dir)passwdXXXXXX</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.readline.enable</p>         </td>
         <td><p>Enables readline history for CFTUTIL PKIUTIL and SECUTIL.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.readline.enable)</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.readline.history_fname</p>         </td>
         <td><p>Readline history file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.readline.history_fname)</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.readline.history_size</p>         </td>
         <td><p>Readline history size.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.readline.history_size)</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.shared_memory_size</p>         </td>
         <td><p>Size (ko) of shared memory used by Transfer CFT. Advanced users only.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>32000</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.start_timeout</p>         </td>
         <td><p>"Sets the Transfer CFT time limit to start up. If the Transfer CFT status does not change within the delay, it is assumed that the 'cft start' command failed."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.stcp.afunix</p>         </td>
         <td><p>Replaces an environment variable.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.data_dir)S_TCP</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.stop_timeout</p>         </td>
         <td><p>"Sets the Transfer CFT time limit to stop. If the Transfer CFT status does not change within the delay, it is assumed that the stop failed."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.sx25.afunix</p>         </td>
         <td><p>Replaces an environment variable.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.data_dir)S_X25</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.unix.throw_error_on_envvar_not_found</p>         </td>
         <td><p>"Throw an error if a used environment variable does not exist. However, if you use '$' in filenames, this option must be set to NO for the file to be created."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cft.working_dir</p>         </td>
         <td><p>Transfer CFT and GUI working directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.ca_cert_id</p>         </td>
         <td><p>Identifier of the CA certificate (stored in the internal PKI base) used to authenticate the Central Governance server.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.cert.subject_dn</p>         </td>
         <td><p>Subject Distinguished Name of the Central Governance certificate. It's used to verify the Central Governance identity when Central Governance connects to Transfer CFT.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.business.csr_dn</p>         </td>
         <td><p>Distinguished Name to use to build the Certificate Sign Request for business flow. Tokens must be separated by a comma.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'O=Axway,OU=MFT,CN=$(cft.full_hostname)'"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>IRECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.business.csr_id</p>         </td>
         <td><p>Internal identifier given by the Central Governance server when sending a Certificate Signing Request for business exchanges.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>READ_ONLY</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.business.key_len</p>         </td>
         <td><p>"Business certificate key length. When this parameter is changed, the \"</p>         </td>
         <td><p>int</p>         </td>
         <td><p>enum: 2048 4096</p>         </td>
         <td><p>2048</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.business.renewal_datetime</p>         </td>
         <td><p>"Datetime (GMT/UTC) used to force the renewal of the business certificate. When datetime is reached, start the renewal procedure. The datetime format is YYYYMMDDHHMMSS."</p>         </td>
         <td><p>datetime</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.governance.csr_dn</p>         </td>
         <td><p>Distinguished Name to use to build the Certificate Sign Request for governance exchanges. Tokens must be separated by a comma.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'O=Axway,OU=MFT,CN=Transfer CFT $(cft.instance_id)'"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>IRECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.governance.csr_id</p>         </td>
         <td><p>Internal identifier given by the Central Governance server when sending a Certificate Signing Request for governance exchanges.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>READ_ONLY</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.governance.key_len</p>         </td>
         <td><p>"Governance certificate key length. When this parameter is changed, the \"</p>         </td>
         <td><p>int</p>         </td>
         <td><p>enum: 2048 4096</p>         </td>
         <td><p>2048</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cg.certificate.governance.renewal_datetime</p>         </td>
         <td><p>"Datetime (GMT/UTC) used to force the renewal of the governance certificate. When datetime is reached, start the renewal procedure. The datetime format is YYYYMMDDHHMMSS."</p>         </td>
         <td><p>datetime</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.configuration_policy</p>         </td>
         <td><p>Central Governance configuration policy to apply on the Transfer CFT instance.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:100"</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.enable</p>         </td>
         <td><p>"Enables exchanges with the Central Governance server (registration, heartbeat)."</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.host</p>         </td>
         <td><p>Central Governance server host address (IP address or FQDN).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'cg-server-hostname'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.key_label</p>         </td>
         <td><p>Label used for License Key Management.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERIMENTAL</p>         </td>
      </tr>
      <tr>
         <td><p>cg.metadata</p>         </td>
         <td><p>Properties sent to Central Governance.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>agent</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.metadata.&lt;logical_name&gt;.value</p>         </td>
         <td><p>Value of the metadata.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.mutual_auth_port</p>         </td>
         <td><p>Transfer CFT's port for communication with CG</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>12554</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.periodicity</p>         </td>
         <td><p>"Interval in seconds between two notifications (registration, heartbeat, certificate renewal) sent to Central Governance. When the ""Central Governance is waiting for approval"" option is enabled, the first notification interval is \"</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>600</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.port</p>         </td>
         <td><p>Transfer CFT's port for registering with CG</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>12553</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.in.host</p>         </td>
         <td><p>Proxy host used by Central Governance to connect to Transfer CFT</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.in.login</p>         </td>
         <td><p>Proxy login used by Central Governance to connect to Transfer CFT</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.in.password</p>         </td>
         <td><p>Proxy password used by Central Governance to connect to Transfer CFT</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.in.port</p>         </td>
         <td><p>Proxy port used by Central Governance to connect to Transfer CFT</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.out.host</p>         </td>
         <td><p>Proxy host used by Transfer CFT to connect to Central Governance</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.out.login</p>         </td>
         <td><p>Proxy login used by Transfer CFT to connect to Central Governance</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.out.password</p>         </td>
         <td><p>Proxy password used by Transfer CFT to connect to Central Governance</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.proxy.out.port</p>         </td>
         <td><p>Proxy port used by Transfer CFT to connect to Central Governance</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.registration_id</p>         </td>
         <td><p>"Registration Identifier provided by Central Governance server. If set to -1, Transfer CFT tries to register to Central Governance server."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>cg.renewal_period</p>         </td>
         <td><p>Number of day before expiration the certificate renewal procedure executes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.restapi_port</p>         </td>
         <td><p>Central Governance REST API port</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>8081</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cg.shared_secret</p>         </td>
         <td><p>The shared secret needed to register to the Central Governance server.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>cg.timeout</p>         </td>
         <td><p>TCP connection timeout (in seconds)</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.batches</p>         </td>
         <td><p>List of available batches (logical names separated by a white space).</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>"wlog cftext (NT, UNIX, OS400, MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.batches.&lt;logical_name&gt;.comment</p>         </td>
         <td><p>Free comment.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.batches.&lt;logical_name&gt;.file</p>         </td>
         <td><p>Filename of the script.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.batches.&lt;logical_name&gt;.params</p>         </td>
         <td><p>List of arguments to pass when calling the script.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.batches.xmldefinition</p>         </td>
         <td><p>The URL for the XML file used to customize the GUI.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'guiextensions/plugin.xml'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.catalog.paging</p>         </td>
         <td><p>Selects paging mode.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.com</p>         </td>
         <td><p>"Communication media description for JPI (medium Type = medium Name ex ""F=$CFTCOM"")"</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.maxcatrows</p>         </td>
         <td><p>Limits the number of displayed catalog rows to this number (applies only if copilot.catalog.paging is set to No).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.maxlogrows</p>         </td>
         <td><p>Limits the number of displayed log rows to this number.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10000 (MVS) | 5000 (not MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.mediacom</p>         </td>
         <td><p>Selects the type of media to use.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: FILE TCPIP MBX</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.medianame</p>         </td>
         <td><p>Selects the name of the media to use.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.nbwaitcftcata</p>         </td>
         <td><p>Wait number for catalog file scanning.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>6</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.cft.timerwaitcftcata</p>         </td>
         <td><p>Interval of time in seconds between catalog file scanning.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.coms_proxy.recovery_delay</p>         </td>
         <td><p>Delay in seconds between two attempts to recover from a connection problem.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(copilot.node_manager.watchperiod)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.coms_proxy.watchperiod</p>         </td>
         <td><p>Interval in seconds between two checks of Transfer CFT coms configuration and status.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.control.port</p>         </td>
         <td><p>Connection dispatcher TCP control port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.enable</p>         </td>
         <td><p>Enables client registering connection dispatching.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.listen_ipv6_first</p>         </td>
         <td><p>Ensures that listening is performed first on IPv6 resolutions.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.listen_ipv6_v6only</p>         </td>
         <td><p>Ensures that listening on IPv6 resolutions only apply to IPv6 calls.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.local_port</p>         </td>
         <td><p>Local TCP port for connection dispatching.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>"NT, UNIX, VMS"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.retry_delay</p>         </td>
         <td><p>The amount of time in seconds between retries for the client to register to the connection dispatcher.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.retry_timeout</p>         </td>
         <td><p>The amount of time in seconds of the timeout when client is registering to the connection dispatcher.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>300</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.connection_dispatcher.unix.af_unix_fname</p>         </td>
         <td><p>Unix socket pathname for connection dispatching.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)/run/S_$(cft.short_hostname)DISPATCH</p>         </td>
         <td><p>"UNIX,  OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.enable</p>         </td>
         <td><p>Enables use of the Copilot server.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.localport</p>         </td>
         <td><p>Copilot notifications local listening port.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.login_failures.fname</p>         </td>
         <td><p>Path to local file used to store login failure data.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftlogin.dat (not OS400) | *LIBL/CFTLOGIN (OS400)</p>         </td>
         <td><p>"not MVS, not VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.login_failures.max</p>         </td>
         <td><p>Maximum number of login failure before locking the user for 30 seconds. Value 0 disables the feature.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>"not MVS, not VMS"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.persistencedir</p>         </td>
         <td><p>Persistent data directory.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime_dir)/persist (not MVS, not VMS) | $(cft.runtime_dir)persist] (VMS) | $(copilot.HTTP.HttpRootDir)/persist (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.serverhost</p>         </td>
         <td><p>Copilot server listening address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0.0.0.0' (not VMS) | '$(ucx$inet_host).$(ucx$inet_domain)' (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.serverport</p>         </td>
         <td><p>Copilot server listening port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1766</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.general.ssl_serverport</p>         </td>
         <td><p>Copilot (GUI) server listening port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1767</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.aliases</p>         </td>
         <td><p>"List of enabled alias IDs, used to customize access to system directories."</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>wsdl restapidocs restapiui cftui</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.cache</p>         </td>
         <td><p>Configure HTTP cache header.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>javascript</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.cache.&lt;logical_name&gt;.expires</p>         </td>
         <td><p>Cache validity.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.cache.&lt;logical_name&gt;.filter</p>         </td>
         <td><p>File pattern filter.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.httprootdir</p>         </td>
         <td><p>HTTP server root directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)/wwwroot (not VMS) | $(cft.runtime_dir)wwwroot] (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.http.onlyssl</p>         </td>
         <td><p>If set to Yes disables use of the HTTP server when a SSL context is defined (HTTPS only).</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.mftnavigator.enable</p>         </td>
         <td><p>Enables remote Transfer CFT Navigators to connect to the Transfer CFT GUI.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.backuplanguages</p>         </td>
         <td><p>Ordered list of languages to use if information is missing in the used language.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>en fr</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.cftstart</p>         </td>
         <td><p>Exec filename to start Transfer CFT.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.install_dir)/distrib/copilot/copcftstart (not NT, not MVS, not VMS) | $(cft.install_dir)/distrib/copilot/copcftstart.bat (NT) | $(cft.runtime_dir)INSTALL(CFTMON) (MVS) | COPCFTSTART (VMS) | *LIBL/COPCFTSTR (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.cftstart.enable</p>         </td>
         <td><p>Enables the Start and Stop of CFT with Copilot.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>"MVS, OS400"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.cftstop</p>         </td>
         <td><p>Script used by Copilot to stop Transfer CFT.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.childprocesstimeout</p>         </td>
         <td><p>"Inactivity timeout of child processes, in seconds."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>"20 (not MVS, not VMS, not OS400) | 3600 (MVS) | 60 (VMS) | 86400 (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.client_keep_alive_delay</p>         </td>
         <td><p>The amount of time in seconds between two sending of keep alive. The value 0 indicates no keep alive.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.clienttimeout</p>         </td>
         <td><p>"Client connection timeout, in minutes (0 means no timeout ; for CFT UI tokens, 0 means one hour timeout)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>30</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.copstart</p>         </td>
         <td><p>Script used by Copilot to start Copilot.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.copstop</p>         </td>
         <td><p>Script used by Copilot to stop Copilot.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.createprocessasuser</p>         </td>
         <td><p>Enables using system users in Copilot.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes (WIN-IA64) | Yes (WIN-X86) | No (UNIX) | Yes (OS400) | Yes (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.help_url</p>         </td>
         <td><p>The URL for the Tranfer CFT User guide.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.languages</p>         </td>
         <td><p>List of the additional languages.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.local_encoding</p>         </td>
         <td><p>"Local encoding to use, which must be relatively compatible with ASCII."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>AUTO (not VMS) | iso8859-1 (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.maxnbprocess</p>         </td>
         <td><p>Maximum number of processes in processes pool that may be ready to process a client connection.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>20</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.minnbprocessready</p>         </td>
         <td><p>"Minimum number of processes, in the processes pool, that must be ready to process a client connection."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1 (not MVS) | 2 (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.nbprocesstostart</p>         </td>
         <td><p>"Number of processes to add in processes pool, when there are not enough processes in the pool."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1 (not MVS) | 3 (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.server_inactivity_timeout</p>         </td>
         <td><p>Inactivity timeout in seconds for copilot server process servicing a client (0 means no timeout).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>7200</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.tcptimeout</p>         </td>
         <td><p>Timeout of TCP select in seconds.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>"10 (not MVS, not VMS) | 60 (VMS) | 300 (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.misc.xts_encoding</p>         </td>
         <td><p>XTS string encoding.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>UTF-8 (not OS400) | 01208 (OS400)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.node_manager.node_repair_period</p>         </td>
         <td><p>Delay in seconds used by CFT to detect and try to repair node starting issues. The value 0 means that the repair feature is disabled. It's recommended to set a value &gt;= 60 and &gt;= 4*copilot.node_manager.watchperiod.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.node_manager.watchperiod</p>         </td>
         <td><p>Interval in seconds between two checks of Transfer CFT nodes status.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.nt.coptray_trcfilename</p>         </td>
         <td><p>Coptray trace.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)coptray.trc</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.nt.rootdrives</p>         </td>
         <td><p>List of authorized root drives.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>@REMOVABLE_DRIVES @LOCAL_DRIVES @NET_DRIVES</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.nt.service_mode</p>         </td>
         <td><p>Copilot is installed in service mode</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.nt.service_name</p>         </td>
         <td><p>Copilot (GUI) service name in Windows.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>CopilotService</p>         </td>
         <td><p>NT</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.output.fname</p>         </td>
         <td><p>Copilot (Transfer CFT UI server) output filename.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)copsmng.out</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.pid_fname</p>         </td>
         <td><p>File containing the Copilot (copsmng) Process ID.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)copsmng.pid</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.api_token_validity</p>         </td>
         <td><p>"Specifies the API Token validity period, in seconds. 0 disables expiration."</p>         </td>
         <td><p>int</p>         </td>
         <td><p>min:0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.authentication_method</p>         </td>
         <td><p>REST API Server Authentication method.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'system' (not UNIX) | 'xfbadm' (UNIX)</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.catalog.retry_delay</p>         </td>
         <td><p>The amount of time in seconds between retries for the catalog surveys.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:10"</p>         </td>
         <td><p>5</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.catalog.retry_timeout</p>         </td>
         <td><p>The amount of time in seconds of the timeout to look an udpate in the catalog.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:-1, max:120"</p>         </td>
         <td><p>30</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.coms_id</p>         </td>
         <td><p>The TCP CFTCOM object identifier used by the REST API server to communicate to Transfer CFT server.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:32"</p>         </td>
         <td><p>'coms'</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.enable</p>         </td>
         <td><p>Enable or not rest API</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.maxclient</p>         </td>
         <td><p>Number of client connections handled per REST worker.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:1024"</p>         </td>
         <td><p>256</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.nb_workers</p>         </td>
         <td><p>Number of activated workers that process REST API requests.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:10"</p>         </td>
         <td><p>4</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.serverport</p>         </td>
         <td><p>The server address</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1768</p>         </td>
         <td><p>not VMS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.restapi.unix_socket_fname</p>         </td>
         <td><p>Path to socket file (internal).</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:256"</p>         </td>
         <td><p>$(cft.runtime.run_dir)S_COPRESTS</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.rootdirs</p>         </td>
         <td><p>List of authorized root directories used to limit remote file access.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>runtime</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.rootdirs.&lt;logical_name&gt;.fname</p>         </td>
         <td><p>path to allowed dir</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>##INVALID##</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.control_port</p>         </td>
         <td><p>Copilot main agent (copsmng) control port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.copcod_local_port</p>         </td>
         <td><p>Connection dispatcher local port in multi-node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.copui_client_socket</p>         </td>
         <td><p>Windows socket passing.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.copui_client_ssl_socket</p>         </td>
         <td><p>Windows ssl socket passing.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.copui_notification_port</p>         </td>
         <td><p>Notification port for copsmng (Copilot).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.copui_pid</p>         </td>
         <td><p>copui Process ID.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.pid</p>         </td>
         <td><p>Copilot (copsmng) Process ID copsmng.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.state</p>         </td>
         <td><p>Transfer UI server status (Copilot).</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: INITIALIZING STARTING RUNNING STOPPING STOPPED ERROR</p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.run.state_timestamp</p>         </td>
         <td><p>Last time copilot status changed.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslcertfile</p>         </td>
         <td><p>Filename of a PKCS12 file or X509 certificate file used to authenticate the Copilot server to clients.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslcertpassword</p>         </td>
         <td><p>SSLCertFile (SSL certificate file) password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslciphersuites</p>         </td>
         <td><p>Cipher suites to be used by Copilot server for https.</p>         </td>
         <td><p>int_list</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(ssl.ciphersuites)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslkeyfile</p>         </td>
         <td><p>Separate key file needed if SSLCertFile is an X509 certificate.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.sslkeypassword</p>         </td>
         <td><p>SSLKeyFile password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.ssl.version_min</p>         </td>
         <td><p>Minimum SSL version allowed by Copilot.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ssl_3.0 tls_1.0 tls_1.1 tls_1.2</p>         </td>
         <td><p>'$(ssl.version_min)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.startup.catalog</p>         </td>
         <td><p>Open catalog on startup.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.startup.catalog.filter</p>         </td>
         <td><p>Default startup catalog filter.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>errors</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.startup.log</p>         </td>
         <td><p>Open log on startup.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.startup.log.filter</p>         </td>
         <td><p>Default startup log filter.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace</p>         </td>
         <td><p>Specific trace level.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>TCP SSL HTTP XTS WS SYS FMK NOTF TRC CONF CFTF CFTS CFTE IUI</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.&lt;logical_name&gt;.level</p>         </td>
         <td><p>Trace level by category</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ERR WRN INF DBG</p>         </td>
         <td><p>$(copilot.trace.trclevel)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.exec</p>         </td>
         <td><p>Switchlog script. Sample script $(cft.runtime_dir)/exec/switchlog.cmd[bat].</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.exec_args</p>         </td>
         <td><p>Arguments for switchlog script.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.exec_bufsize</p>         </td>
         <td><p>Internal buffer.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.exec_time</p>         </td>
         <td><p>Hour of day to execute switchlog. If not empty (default) use the YYYYmmddHHMMSS format.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.exec_timeout</p>         </td>
         <td><p>Timeout in seconds for executing a switchlog.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trcafilename</p>         </td>
         <td><p>Alternate trace file of copui process.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)copui-a.trc</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trcfilename</p>         </td>
         <td><p>Primary trace file of copui process.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)copui.trc (not MVS) | 'dd:COTRACE' (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trclevel</p>         </td>
         <td><p>"General trace level: ERR(error), WRN(warning), INF(info), DBG(debug)"</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ERR WRN INF DBG</p>         </td>
         <td><p>'ERR'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trcmaxlen</p>         </td>
         <td><p>Maximum size (Mb) of the primary trace file (dynamic parameter).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>10</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trcshowline</p>         </td>
         <td><p>Adds source file line number when using a trace.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.trace.trctype</p>         </td>
         <td><p>Categories of events to trace (separator = SPACE).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'TCP SSL HTTP XTS WS SYS FMK NOTF TRC CONF CFTF CFTS CFTE IUI'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.unix.cftsu.afunix</p>         </td>
         <td><p>Sets the AF_UNIX file for cftsu.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)Scftsu</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.unix.cftsu.fname</p>         </td>
         <td><p>Specify the absolute pathname to the cftsu to execute.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.unix.cftsu.pid_fname</p>         </td>
         <td><p>File containing the cftsu Process ID.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)cftsu.pid</p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.unix.unix_socket_fname</p>         </td>
         <td><p>Path to socket file (internal).</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)S_COPSMNGFW</p>         </td>
         <td><p>"UNIX,  OS400"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.update_manager.working_dir</p>         </td>
         <td><p>Working directory of the Copilot Update Manager.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>UNIX</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>copilot.webservices.buffersoap</p>         </td>
         <td><p>"If set to Yes, the correct order of SOAP reply is buffered."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.webservices.enable</p>         </td>
         <td><p>Enables the use of Web services.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.webservices.ordersoap</p>         </td>
         <td><p>"If set to Yes, the SOAP reply has the order defined in the copilotcft.wsdl."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.webservices.upload_directory</p>         </td>
         <td><p>Directory where files are uploaded.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)/upload (not MVS) | $(cft.runtime_dir)UPLOAD (MVS) | $(cft.install_dir)UPLOAD] (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>copilot.webservices.wsicomplience</p>         </td>
         <td><p>"If set to Yes, client requests are checked against WS-I recommendations."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>crypto.key_fname</p>         </td>
         <td><p>Filename containing the private key to encipher data with</p>         </td>
         <td><p>fname</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>crypto.salt_fname</p>         </td>
         <td><p>Filename containing the salt used to create the private key</p>         </td>
         <td><p>fname</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>custom.install</p>         </td>
         <td><p>Custom variables used in samples.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.enable</p>         </td>
         <td><p>Enable the folder monitoring functionality.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders</p>         </td>
         <td><p>List of directory to scan attributes sets.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.control</p>         </td>
         <td><p>Meta data used to control user changes.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.enable</p>         </td>
         <td><p>Enables the scan of the folder.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.enable_subdir</p>         </td>
         <td><p>Enables sub-directory scan.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_count</p>         </td>
         <td><p>Number of file to take into account while scanning.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_exclude_filter</p>         </td>
         <td><p>Exclude file name matching this pattern.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_idle_delay</p>         </td>
         <td><p>Delay in seconds to decide that a file is ready to be submitted.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_include_filter</p>         </td>
         <td><p>Include file name matching this pattern.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_size_max</p>         </td>
         <td><p>Maximum file size in bytes - ignored if larger size.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.file_size_min</p>         </td>
         <td><p>Minimum file size in bytes - ignored if shorter size.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>-1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.filter_type</p>         </td>
         <td><p>Pattern filtering algorithm to use.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: STRJCMP WILDMAT EREGEX</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.idf</p>         </td>
         <td><p>CFT IDF either fixed string or sub-directory name level (0) or (1).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.interval</p>         </td>
         <td><p>Interval between two scans in seconds.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.method</p>         </td>
         <td><p>Monitoring method (file or move). MOVE method recommended.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: FILE MOVE</p>         </td>
         <td><p>MOVE</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.part</p>         </td>
         <td><p>CFT PART either fixed string or sub-directory name level (0) or (1).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.renaming_method</p>         </td>
         <td><p>"If TIMESTAMP, add a timestamp (GMT/UTC) to the moved file name."</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: TIMESTAMP NONE</p>         </td>
         <td><p>TIMESTAMP</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.renaming_separators</p>         </td>
         <td><p>Character before [and after] the timestamp in file name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.resubmit_changed_file</p>         </td>
         <td><p>Resubmit a file changed after previous submission (FILE method only).</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.scan_dir</p>         </td>
         <td><p>Top level directory to scan.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.use_file_system_events</p>         </td>
         <td><p>Enables use of the file system events monitoring service.</p>         </td>
         <td><p>bool No Yes</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>folder_monitoring.folders.&lt;logical_name&gt;.work_dir</p>         </td>
         <td><p>Directory specification where to move files from scan_dir.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pesit.parameters.enable_encoding</p>         </td>
         <td><p>"Defines if the PeSIT parameters should be encoded in UTF-8. This affects PI37, PI91 and PI99."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>"UNIX, NT"</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>pki.cft.port</p>         </td>
         <td><p>Transfer CFT PKI listening server port number. Value 0 means a dynamic port will choose by the Operating System at run-time. Other value will be handled as a range from port to (port + number of nodes - 1) in multinode.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.exit.libpath</p>         </td>
         <td><p>Location of CFTPKIE exit dynamic library.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>  | CFTPKIE (VMS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.ca_cert</p>         </td>
         <td><p>List of Certification Authority (CA) public certificates to authenticate PassPort PS server.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.runtime.confpki_dir)passportCA.pem (not OS400) | *LIBL/PASSPRTPEM (OS400)</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.hostname</p>         </td>
         <td><p>PassPort PKI server IP address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'localhost'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.login</p>         </td>
         <td><p>PassPort PKI login. Leave empty for an anonymous connection.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.msgpath</p>         </td>
         <td><p>PassPort msgpath (full pathname of the message-log file).</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install.psenglish_dir) (not MVS) | 'dd:PKIMSG' (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.password</p>         </td>
         <td><p>PassPort PKI password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.port</p>         </td>
         <td><p>PassPort PKI server port number.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>7000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.trace</p>         </td>
         <td><p>XPP PKI trace (0-&gt;5).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.passport.use_ssl</p>         </td>
         <td><p>Enables SSL cryptography when connecting to PassPort PS server.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>not MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.run.cft</p>         </td>
         <td><p>Number of defined Secure Relay Master Agents.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.run.cft.&lt;itemNumber&gt;.port</p>         </td>
         <td><p>Transfer CFT PKI listening server port number reserved at run-time for a specific node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>pki.run.cft.port</p>         </td>
         <td><p>Transfer CFT PKI listening server port number reserved at run-time.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>pki.type</p>         </td>
         <td><p>PKI type used.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'cft'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>samples</p>         </td>
         <td><p>Parameters used for the sample configuration file (cft-tcp.conf).</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.enable</p>         </td>
         <td><p>Enables Secure Relay.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.admin_outport_range</p>         </td>
         <td><p>Secure Relay Master Agent admin outport range.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.autostart</p>         </td>
         <td><p>Allows to automatically start the embedded Secure Relay Master Agent.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.ca_cert_fname</p>         </td>
         <td><p>Secure Relay certificate authority.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_fname</p>         </td>
         <td><p>Secure Relay Master Agent user certificate.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_password</p>         </td>
         <td><p>Secure Relay Master Agent certificate password.</p>         </td>
         <td><p>passwd</p>         </td>
         <td><p> </p>         </td>
         <td><p>test</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.cert_password_fname</p>         </td>
         <td><p>Secure Relay Master Agent certificate password file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)XsrPwd.dat (not MVS) | $(cft.runtime.xsr_dir)XsrPwd.dat (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.comm_outport_range</p>         </td>
         <td><p>Secure Relay Master Agent comm outport range.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>' '</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.comm_port</p>         </td>
         <td><p>"Secure Relay Master Agent listening communication port. In multinode, this will be handled as a range from port to (port + number of nodes - 1)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>6801</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.conf_fname</p>         </td>
         <td><p>Secure Relay Master Agent configuration file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)XsrConf.xml (not MVS) | $(cft.runtime.xsr_dir)XsrConf.xml (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.heartbeat_service.host</p>         </td>
         <td><p>Heartbeat service listening server IP address or FQDN for Secure Relay Master Agent.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>'127.0.0.1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.heartbeat_service.periodicity</p>         </td>
         <td><p>Interval in seconds between two heartbeats.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:86400"</p>         </td>
         <td><p>30</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.heartbeat_service.port</p>         </td>
         <td><p>Heartbeat service listening server port number for Secure Relay Master Agent. Value 0 means a dynamic port will choose by the Operating System at run-time. Other value will be handled as a range from port to \</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.host</p>         </td>
         <td><p>Secure Relay Master Agent listening IP address or FQDN.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'127.0.0.1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.jar_fname</p>         </td>
         <td><p>Secure Relay Master Agent jar file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install.xsr_dir)xsrMaster.jar</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.log_fname</p>         </td>
         <td><p>Secure Relay Master Agent log file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.log_dir)xsrMaster.log (not MVS) | $(cft.runtime.xsr_dir)XsrMaster.log (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.log_level</p>         </td>
         <td><p>"Secure Relay Master Agent log level : 0, 1, 2 or 3."</p>         </td>
         <td><p>int</p>         </td>
         <td><p>min:0; max:3</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.pid_fname</p>         </td>
         <td><p>File containing the Secure Relay Master Agent Process ID.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)xsrMaster.pid (not MVS) |   (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.start_options</p>         </td>
         <td><p>Secure Relay Master Agent start options.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>"'-Xmx1024m' (not NT, not MVS) | '-Xmx512m -Xrs' (NT) | '-Xms512m' (MVS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.start_proc</p>         </td>
         <td><p>Secure Relay Master Agent start procedure.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime_dir)INSTALL(XSRRUN) (MVS) | *LIBL/STRXSR (OS400)</p>         </td>
         <td><p>"MVS, OS400"</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ma.start_timeout</p>         </td>
         <td><p>Amount of time in seconds of the timeout when starting Secure Relay.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>"15 (not MVS, not OS400) | 120 (MVS, OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra</p>         </td>
         <td><p>Number of defined Secure Relay Router Agents.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.admin_port</p>         </td>
         <td><p>Router Agent administration port.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>6810</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.comm_port</p>         </td>
         <td><p>"Router Agent communication port. In multinode, this will be handled as a range from port to (port + number of nodes - 1)."</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>6811</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.data_channel_ciphering</p>         </td>
         <td><p>Enables data connections ciphering.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.dmz</p>         </td>
         <td><p>Logical name of the DMZ where the Router Agent is running (32 char max).</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>DMZ0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.enable</p>         </td>
         <td><p>Enables the Router agent.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.host</p>         </td>
         <td><p>Router Agent IP address or FQDN.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.nb_data_connections</p>         </td>
         <td><p>Number of data connections between Master Agent and Router Agent.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.ra.&lt;itemNumber&gt;.outcall_network_interface</p>         </td>
         <td><p>Address to bind for outgoing calls.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.run.ma</p>         </td>
         <td><p>Number of defined Secure Relay Master Agents.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cft.multi_node.nodes)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.run.ma.&lt;itemNumber&gt;.heartbeat_service_port</p>         </td>
         <td><p>Heartbeat service listening server port number reserved at run-time for a specific node.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>secure_relay.run.ma.heartbeat_service.port</p>         </td>
         <td><p>Heartbeat service listening server port number reserved at run-time.</p>         </td>
         <td><p>int</p>         </td>
         <td><p>"min:1, max:65535"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RUNTIME</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.heartbeat.enable</p>         </td>
         <td><p>Enables sending Heartbeats to the Sentinel Server.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.heartbeat.periodicity</p>         </td>
         <td><p>The delay in seconds between sending Heartbeats.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>300</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.heartbeat.script</p>         </td>
         <td><p>Script for executing Heartbeats.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install.extrasSENT_dir)MFTheartbeat.sh (UNIX) | $(cft.install.extrasSENT_dir)MFTheartbeat.bat (NT) | $(cft.install.extrasSENT_dir)MFTheartbeat.com (VMS) | *LIBL/HEARTBEAT       (OS400)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_max_port</p>         </td>
         <td><p>Outgoing port range upper limit.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>32000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_max_port_bkup</p>         </td>
         <td><p>Outgoing port range upper limit for the backup Server.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>32000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_min_port</p>         </td>
         <td><p>Outgoing port range lower limit.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trk_min_port_bkup</p>         </td>
         <td><p>Outgoing port range lower limit for the backup server.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>5000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkflushdurationmax</p>         </td>
         <td><p>Maximum amount of time in seconds to flush the overflow file.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkgmtdiff</p>         </td>
         <td><p>Difference between local time and GMT in minutes.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkident</p>         </td>
         <td><p>Sentinel UA Environment Variable Name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'TRKIDENT'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipaddr</p>         </td>
         <td><p>Sentinel Server IP address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'sentinel-server-hostname'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipaddr_bkup</p>         </td>
         <td><p>Sentinel backup server IP address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipport</p>         </td>
         <td><p>Sentinel Server port number.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'1305'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkipport_bkup</p>         </td>
         <td><p>Sentinel backup port number.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>1305</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trklenmsg</p>         </td>
         <td><p>Maximum length of a message in TrkUtil (default 16000).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>16000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trklocaladdr</p>         </td>
         <td><p>Universal Agent IP Address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(cft.full_hostname)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkmsgencoding</p>         </td>
         <td><p>Charset encoding of messages sent to Sentinel Server.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ISO8859-1 ISO8859-15 UTF-8</p>         </td>
         <td><p>"'ISO8859-1' (not MVS, not OS400) | 'none' (MVS, OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkproductipaddr</p>         </td>
         <td><p>Application IP Address.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'$(cft.full_hostname)'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trkproductname</p>         </td>
         <td><p>Application name.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'CFT'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trksharedfile</p>         </td>
         <td><p>MANDATORY when the Event Router and applications are sharing the logger file. Set to NO if applications are sending messages directly to the Sentinel server without going through an ER.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>MVS</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktconnretry</p>         </td>
         <td><p>Time in minutes between retries when TRKTMODE is set to RETRY.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>3</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktimeout</p>         </td>
         <td><p>Timeout in seconds.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktmode</p>         </td>
         <td><p>The mode that TrkUtil uses to send messages from TrkUtil to the Sentinel Server.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: DIFFER IMMEDIAT RETRY D I R</p>         </td>
         <td><p>'RETRY'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktname</p>         </td>
         <td><p>The path to the overflow file.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.data_dir)trkapi.buf (not MVS, not VMS) | $(cft.runtime.data_dir)TRKTAM.SEQ (VMS)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrace</p>         </td>
         <td><p>Level of trace (0=disabled).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktrcfile</p>         </td>
         <td><p>Trace filename.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>"$(cft.runtime.run_dir)sentinel.trc (not MVS, not OS400) |   (MVS) | *LIBL/TRKTRC  (OS400)"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.trktype</p>         </td>
         <td><p>Sentinel server connection type.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: TCP SOPIX</p>         </td>
         <td><p>'TCP'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.audit</p>         </td>
         <td><p>Enables configuration change logging.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.buffer_name</p>         </td>
         <td><p>Overflow filename for a configuration audit.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.run_dir)xfbtrk.buf (not MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.buffer_size</p>         </td>
         <td><p>Maximum number of messages in buffer.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>100000</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.ca_cert_id</p>         </td>
         <td><p>Identifier of the CA certificate (stored in the internal PKI base) used to authenticate the Sentinel server.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(cg.ca_cert_id)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.enable</p>         </td>
         <td><p>Enables the Sentinel connector.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.in_memory_pending_messages_max</p>         </td>
         <td><p>Maximum pending messages in memory prior to logging alerts.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.log</p>         </td>
         <td><p>Log Filter: (I)nfo (E)rror (W)arning (F)atal.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'IEWF'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.shut</p>         </td>
         <td><p>Overflow file fill level beyond which Transfer CFT shuts down (0 = no shutdown).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.testlabel</p>         </td>
         <td><p>Specific test label.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer</p>         </td>
         <td><p>Level of detail for Transfer Message content.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ALL SUMMARY NO ERROR</p>         </td>
         <td><p>'ALL'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer.send_relay_site_nidf</p>         </td>
         <td><p>Enables nidf on relay site</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.transfer_progress_period</p>         </td>
         <td><p>Frequency in seconds in which Transfer CFT notifies Sentinel that a transfer is running (0 = never).</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>60</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>sentinel.xfb.use_ssl</p>         </td>
         <td><p>Enables SSL cryptography when connecting to Sentinel Server or ER.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>No</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ssl.certificates.ca_cert_bundle</p>         </td>
         <td><p>Path to the CA cert bundle.\</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>''</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ssl.ciphersuites</p>         </td>
         <td><p>SSL cipher suites negotiated by Transfer CFT connectors.</p>         </td>
         <td><p>int_list</p>         </td>
         <td><p> </p>         </td>
         <td><p>"49200, 49199, 156, 157, 60, 61, 47, 53"</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ssl.extension.enable_sni</p>         </td>
         <td><p>Enable TLS Server Name Indication extension for Tranfser CFT connectors.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERT</p>         </td>
      </tr>
      <tr>
         <td><p>ssl.version_min</p>         </td>
         <td><p>Minimum SSL version allowed by Transfer CFT connectors.</p>         </td>
         <td><p>string</p>         </td>
         <td><p>enum: ssl_3.0 tls_1.0 tls_1.1 tls_1.2</p>         </td>
         <td><p>'tls_1.0'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.defaultlocalcharset</p>         </td>
         <td><p>Corresponds to a character set listed in the character set conversion reference table.</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'ISO-8859-1'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>tf.enablepasswordcipher</p>         </td>
         <td><p>"Indicates that entities passphrases, either in the entities definition file (entities.xml) or in the operation description file."</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.entitieslocation</p>         </td>
         <td><p>Indicates the path to the entities.xml file where Trusted File is configured in standalone mode.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conftf_dir)entities.xml (not MVS) | $(cft.runtime.conftf_dir)UPARM(XENTITI) (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.entitieslocationtype</p>         </td>
         <td><p>Trusted File configures a local or remote server (local or remote)</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'local'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>RECONFIG</p>         </td>
      </tr>
      <tr>
         <td><p>tf.messageslocation</p>         </td>
         <td><p>Transfer CFT runtime directory.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.install.tfenglish_dir)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.overwritemode</p>         </td>
         <td><p>"Defines how Axway TrustedFile behaves when it opens an existing plain file, acknowledgement or envelope in write mode."</p>         </td>
         <td><p>string</p>         </td>
         <td><p> </p>         </td>
         <td><p>'enable'</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.proofsenabled</p>         </td>
         <td><p>Enables use of proofs.</p>         </td>
         <td><p>bool Yes No</p>         </td>
         <td><p> </p>         </td>
         <td><p>Yes</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.proofslocation</p>         </td>
         <td><p>References the absolute path to the directory that the product uses to generate proofs.</p>         </td>
         <td><p>dir</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.datatf_dir)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.proofsuidfile</p>         </td>
         <td><p>"ProofsUIDFile is used, when no proof is requested"</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.datatf_dir)proofsUIDFile.cfg (not MVS) | $(cft.runtime.datatf_dir)PROOFUID (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.trace</p>         </td>
         <td><p>Specific trace level.</p>         </td>
         <td><p>string list</p>         </td>
         <td><p> </p>         </td>
         <td><p>mime pgp smime xasn xfm xpf xpki xpp xppwrap</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.trace.&lt;logical_name&gt;.level</p>         </td>
         <td><p>Trace level.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>$(tf.trace.trclevel)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.trace.trclevel</p>         </td>
         <td><p>Trace level: between 0 and 9</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>tf.transcodingtablelocation</p>         </td>
         <td><p>Absolute path to the character set conversion reference table.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.conftf_dir)transcoding.tbl (not MVS) | $(cft.runtime.conftf_dir)UPARM(XTRANSC) (MVS)</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>trace.file.level</p>         </td>
         <td><p>Use only under Axway support supervision.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERIMENTAL</p>         </td>
      </tr>
      <tr>
         <td><p>trace.net.level</p>         </td>
         <td><p>Use only under Axway support supervision.</p>         </td>
         <td><p>int</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERIMENTAL</p>         </td>
      </tr>
      <tr>
         <td><p>trace.xtrace.default_fname</p>         </td>
         <td><p>Use only under Axway support supervision.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>$(cft.runtime.traces_dir)cft.trc</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERIMENTAL</p>         </td>
      </tr>
      <tr>
         <td><p>trace.xtrace.default_level</p>         </td>
         <td><p>Use only under Axway support supervision.</p>         </td>
         <td><p>fname</p>         </td>
         <td><p>"min length:0, max length:512"</p>         </td>
         <td><p>0</p>         </td>
         <td><p>ALL</p>         </td>
         <td><p>EXPERIMENTAL</p>         </td>
      </tr>
   </tbody>
</table>
