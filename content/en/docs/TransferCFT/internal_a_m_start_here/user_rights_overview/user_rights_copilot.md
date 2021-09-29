{
    "title": "3. Define client user rights",
    "linkTitle": "3. Define client user rights",
    "weight": "240"
}This section describes the copilot.misc.createprocessasuser parameter.

When using Central Governance

By default this parameter is set to NO and user authentication is controlled by Central Governance. Setting this to YES allows system user authentication via a client, such as web services, if there were a Central Governance failure. This setup requires that users be known on both the system and on Central Governance, meaning an LDAP directory.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Configuration changes should be managed by <span>Central Governance</span>.</td>
</tr>
</tbody>
</table>

When using standalone Transfer CFT

When set to YES, user authentication is controlled by the system where Transfer CFT is installed and the Transfer CFT Copilot server starts a process under the connected user. Note that the default value is platform specific. When set to NO, actions made on the configuration are done with the user that **started** the Transfer CFT Copilot server.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>OS</th>
<th>Default</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Unix</p></td>
<td>NO</td>
</tr>
<tr class="even">
<td><p>Windows</p></td>
<td>YES</td>
</tr>
<tr class="odd">
<td>IBM i</td>
<td>YES</td>
</tr>
<tr class="even">
<td>z/OS</td>
<td><p>This functionality was modified in Transfer CFT 3.2.4 SP1:</p>
<ul>
<li>Post-SP1: The default value for <span>createprocessasuser </span>is YES.</li>
<li>Pre-SP1: There is no definable value. The equivalent of <code>createprocessasuser </code>depends on the use of APF. If JOBLIB is not defined as an APF, it is the equivalent of NO. If defined, this is the equivalent of YES.</li>
</ul></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Using <span>Central Governance</span> you must set appropriate user privileges. Otherwise, a user with extensive <span>Central Governance</span> privileges could modify the Transfer CFT configuration by connecting via the client, <em>even</em> if this user has restricted access to the runtime environment.</td>
</tr>
</tbody>
</table>

When createprocessasuser is set to YES, you must perform the OS specific tasks as described in the appropriate Installation Guide.

-   Refer to the Transfer CFT 3.9 *Installation Guide Unix> Unix operations > Using system users* for detailed instructions.
-   Refer to the Transfer CFT3.9 *Installation Guide Windows > Windows operations > Using system users* for detailed instructions.

Related topics

-   [About system users](..//transfercft/internal_a_m_start_here/user_rights_overview)
-   [User rights use case scenarios](../user_rights_security_scenarios)
-   [Recommendations and troubleshooting](../user_rights_tips)
