{
    "title": "Configuring an AM exit",
    "linkTitle": "Configuring an AM exit",
    "weight": "380"
}# Configuring an Access Management exit



This section describes how to configure access management when not using <span>Central Governance</span>.



To enable an Access Management exit, set the <span>uconf </span>parameters described in this page.



From the Administration pane in the graphical user interface, select<span> Unified Configuration</span>. The <span>Unified Configuration</span> window is displayed.



Double-click in a <span>Unified Configuration</span> window field to begin editing parameters.



Configure the AM exit using the parameters in the following table.



<table data-cellspacing="0">
<thead>
<tr>
<th>Access Management exit parameters</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>am.exit.libpath</td>
<td> </td>
<td>The absolute path of the dynamic library.</td>
</tr>
<tr>
<td>am.exit.check_login</td>
<td>Yes/No</td>
<td>Indicate if the login must be checked through the AM exit.</td>
</tr>
<tr>
<td>am.exit.check_permissions</td>
<td>Yes/No</td>
<td>Indicate if permissions must be checked though the AM exit.</td>
</tr>
<tr>
<td>am.exit.custom.tracelevel.value</td>
<td>Default: 1</td>
<td><p>Trace level where:</p>
<ul>
<li>1=ERR</li>
<li>2=WRN</li>
<li>3=INF</li>
</ul></td>
</tr>
<tr>
<td>am.exit.custom.rbac_fname.value</td>
<td> </td>
<td>Path to the RBAC flat file used by the Access Management exit sample.</td>
</tr>
<tr>
<td>am.exit.custom.ldap_host.value</td>
<td> </td>
<td>LDAP server hostname/IP address that is used by the Access Management exit sample.</td>
</tr>
<tr>
<td>am.exit.custom.ldap_port.value</td>
<td> </td>
<td>LDAP server port that is used by the Access Management exit sample.</td>
</tr>
</tbody>
</table>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When the AM exit is enabled these conditions apply:</td>
</tr>
</tbody>
</table>



-   uconf:am.exit.check\_login=No: the native authentication procedure is still performed

-   uconf:am.exit.check\_permissions=No: all privileges are granted for the current user



Set the type parameter: <span>am.type = exit</span>



1.  **Important**: Remember that the<span> am.type</span> is the last parameter to set when activating an AM exit and the first to unset when deactivating it.

2.  Restart the <span>Transfer CFT</span> server and <span>Transfer CFT</span> UI (Copilot) server.



Example Access Management exit configuration



1.  Using command line set the am.type to <span>none.</span>

2.  **CFTUTIL UCONFSET ID=am.type, VALUE=none**

3.  Configure the library location and the Access Management exit usage.

4.  CFTUTIL UCONFSET ID=am.exit.libpath, VALUE=&lt;location\_of\_dynamic\_library&gt;

5.  CFTUTIL UCONFSET ID=am.exit.check\_login, VALUE=Yes

6.  CFTUTIL UCONFSET ID=am.exit.check\_permissions, VALUE=Yes

7.  Enable the Access Management exit.

8.  **CFTUTIL UCONFSET ID=am.type, VALUE=exit**



### Using the custom AM exit sample



This section presents parameters that you may need to set if you are creating an EXIT based on the <span> examldap.c</span> sample. The <span>examldap.c</span> sample is built with the OpenLDAP library, which Axway does not deliver. To use, compile this library and add it to the LD\_LIBRARY\_PATH.



-   am.exit.custom.ldap\_base: The top level of the LDAP directory tree is the base, referred to as the "base DN". Enter the base (DN) to authenticate on the connected LDAP server, which defines which LDAP tree node to use as the root node. Example: <span>dc=example,dc=com</span>

-   am.exit.custom.ldap\_login\_dn\_format: The user DN format used to search for a user DN on the LDAP server.

-   For example, if a user is identified by cn=theUser,ou=people,dc=example,dc=com, set <span>am.exit.custom.ldap\_login\_dn\_format</span> to <span>"cn=%s,ou=people,dc=example,dc=com"</span>

-   am.exit.custom.ldap\_get\_roles\_filter: The filter used to retrieve the groups that a given user belongs to.

-   For example, if the filter <span>"(&amp;(objectClass=group)(member=cn=theuser,ou=people,dc=example,dc=com))"</span> returns the list of groups for the user "theUser", set <span>am.exit.custom.ldap\_get\_roles\_filter</span> to <span>"(&amp;(objectClass=group)(member=cn=%s,ou=people,dc=example,dc=com))"</span>



Related topics



[About Access Management exits](../../../internal_access_mgt/am_exits.htm)

