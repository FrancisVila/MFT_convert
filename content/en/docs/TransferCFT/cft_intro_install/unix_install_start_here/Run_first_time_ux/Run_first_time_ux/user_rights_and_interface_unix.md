{
    "title": "Defining user rights ",
    "linkTitle": "Defining user rights ",
    "weight": "240"
}Before you can start Transfer CFT from the Transfer CFT UI server, the Copilot server must be started. Additionally, you require rights to log on to this server.

## <span id="Define rights before logging on the CFT Navigator server"></span>Define rights before logging on the Transfer CFT UI server

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>copilot.misc.createprocessasuser</p>
<p>value =</p></th>
<th><p>With PassPort AM</p></th>
<th>Without PassPort AM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>yes</strong></p>
<p>Root privileges are required for CFTSU.</p></td>
<td><p>With PassPort AM</p>
<p>Check user method: operating system login</p>
<p>Create Process: Unix User
In this case, the system user must exist in PassPort AM for security rights.</p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p><strong>yes</strong></p>
<p>Root privileges are required for CFTSU.</p></td>
<td> </td>
<td><p>No PassPort AM</p>
<p>Check user method: operating system login</p>
<p>Create Process: Unix user</p></td>
</tr>
<tr class="odd">
<td><strong>no</strong> (Unix default)</td>
<td><p>With PassPort AM</p>
<p>Check user method: AM login</p>
<p>Create Process: <span>Transfer CFT</span> UI user (Copilot)</p>
<p>In this case, users must be defined in PassPort AM for login and security rights.</p></td>
<td> </td>
</tr>
<tr class="even">
<td><strong>no</strong> (Unix default)</td>
<td> </td>
<td><p>No PassPort AM</p>
<p>Users must be created in the local <span>Transfer CFT</span> internal datafile (xfbadmusr, see <a href="../../use_cft_utilities">xfbadmusr utilitiy</a>)</p></td>
</tr>
</tbody>
</table>

 

Related topics

[About PassPort AM](../../../../../internal_a_m_start_here/about_passport_am)

[UCONF parameters](../../../../../admin_intro/uconf/uconf_parameters)
