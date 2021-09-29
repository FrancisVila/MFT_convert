{
    "title": "Delivered exit samples",
    "linkTitle": "Delivered exit samples",
    "weight": "390"
}This section describes how to configure access management when not using Central Governance.

Axway delivers an Access Management exit sample, examsmp1.c, in the &lt;CFTDIRRUNTIME>/src/exit directory.

### Services provided by delivered sample

The delivered sample provides two services, authentication and permissions checking.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Sample</th>
<th>Authentication</th>
<th>Permissions checking</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>examsmp1.c</td>
<td>System authentication (<span>Windows only</span>)</td>
<td>Flat file based on flat <a href="javascript:void(0)">RBAC<span aria-hidden="true"><span> </span>Role Based Access Control</span></a> model</td>
</tr>
</tbody>
</table>

### Building the dynamic library associated with the sample

To build the exit:

Change the directory to: &lt;CFTDIRRUNTIME>/src/exit

Run the following command:

-   UNIX: make
-   Windows: nmake -f exit.mak

The output is a library located at &lt;CFTDIRRUNTIME>/lib/libcftexam.(so/dll).

## Flat file based on flat RBAC 

To check users rights, Axway delivers a sample flat file based on flat [RBAC<span aria-hidden="true"> Role Based Access Control</span>](javascript:void(0)) (Role Based Access Control) located in: &lt;CFTDIRRUNTME>/conf/exam.csv. This file contains a set of permission and user assignments.

![Simplied diagram of relationship between users, roles and permissions](am_exits_rbac.GIF)

## Assigning permission

The following line shows how to add a permission to a role:  
&lt;cmd\_type> &lt;role> &lt;resource> &lt;actions> &lt;policy>

Where:

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;cmd_type&gt;</td>
<td>PA for Permission Assignment</td>
</tr>
<tr class="even">
<td>&lt;role&gt;</td>
<td>The role for which the permission must be assigned</td>
</tr>
<tr class="odd">
<td>&lt;resource&gt;</td>
<td>Name of the resource</td>
</tr>
<tr class="even">
<td>&lt;actions&gt;</td>
<td>List of actions with each action separated by a comma</td>
</tr>
<tr class="odd">
<td>&lt;policy&gt;</td>
<td>ACCEPT: accept the actions on the resource<br />
REFUSE: refuse the actions on the resource</td>
</tr>
</tbody>
</table>

Examples

All available actions on the resource “CONFIGURATION:CFTPARM”:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PA ADMIN CONFIGURATION:CFTPARM CREATE,DELETE,EDIT,VIEW ACCEPT</td>
</tr>
</tbody>
</table>

or

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PA ADMIN CONFIGURATION:CFTPARM * ACCEPT</td>
</tr>
</tbody>
</table>

All available actions on resources that start with “CONFIGURATION:” for the ADMIN role:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PA ADMIN CONFIGURATION:* * ACCEPT</td>
</tr>
</tbody>
</table>

All permissions for the ADMIN role:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PA ADMIN * * ACCEPT</td>
</tr>
</tbody>
</table>

All permissions for the ADMIN role except for the resource “TRANSFER”:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>PA ADMIN TRANSFER * REFUSE<br />
PA ADMIN * * ACCEPT</td>
</tr>
</tbody>
</table>

## Assigning users

The following line shows how to add a user to a role:  
&lt;cmd\_type> &lt;role> &lt;users>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>&lt;cmd_type&gt;</td>
<td>UA for User Assignment</td>
</tr>
<tr class="even">
<td>&lt;role&gt;</td>
<td>The role to which users must be assigned</td>
</tr>
<tr class="odd">
<td>&lt;users&gt;</td>
<td>List of users with each user separated by a comma</td>
</tr>
</tbody>
</table>

#### Examples

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>UA ADMIN admin,user01,user02</p>
<p>UA DESIGNER user03</p>
<p>UA HELPDESK user03,user04</p>
<p>UA APPLICATION user05</p></td>
</tr>
</tbody>
</table>

## Predefined roles

You can find some roles defined in &lt;CFTDIRRUNTIME>/conf/exam.csv.

Predefined roles

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Role</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Administrator</td>
<td>Provides full user access</td>
</tr>
<tr class="even">
<td>Helpdesk</td>
<td>Enables you to view the Catalog and Log</td>
</tr>
<tr class="odd">
<td>Partner Manager</td>
<td>Allows you to manage partners</td>
</tr>
<tr class="even">
<td>Designer</td>
<td>Allows you to manage application flows</td>
</tr>
<tr class="odd">
<td>Application</td>
<td>Allows applications to request transfers and view the Catalog</td>
</tr>
</tbody>
</table>

The resources and available actions for Transfer CFT are listed in the PassPort AM CSD file.

After installing Transfer CFT, access the CSD file:

&lt;Transfer CFT install directory>/distrib/am/csd\_Transfer\_CFT.xml

For more information, refer to the PassPort AM CSD.

Related topics

[About Access Management exits](../../../../internal_a_m_start_here/am_exits)

[Configuring an Access Management exit](../../../../internal_a_m_start_here/am_exits/configure_am_exits)
