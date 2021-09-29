{
    "title": "Define internal access management",
    "linkTitle": "Define internal access management",
    "weight": "280"
}This section describes the OS specific settings required to enable internal access management. As a prerequisite, you must read and be familiar with the [Internal access management](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/internal_access_mgt/internal_a_m_start_here.htm) information in the *Transfer CFT User Guide*.

## About internal AM

There are three methods available to define internal access management when using Transfer CFT z/OS - a system service, SAF class, or a file.

The are two delivered JCLs, H81$AMIN and H81$AMSF, to use to implement internal access management.

-   H81$AMSF: This JCL activates access management for the group database for the SAF class method
-   H81$AMIN: This JCL activates access management for the group database for either the system or file method

Alternatively, you can use UCONF to define the internal access management. See the Internal access management information in the Transfer CFT 3.9 User Guide for more information.

### Using system as the internal access management

With **system** access management, you define the mapping between predefined roles and groups in UCONF, and the user groups assignment in RACF.

When the access management type is **system**, you must give the STC userID the SPECIAL attribute AUDITOR to be able to read the RACF user profiles.

Define the following facilities for the USERID owner of the STC Copilot CFTMAIN and API batches:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>UCONFSET ID=am.internal.group_database,value=system</p>
<p>SETROPTS GENERIC(FACILITY)</p>
<p>RDEFINE FACILITY IRR.RADMIN.* UACC(READ)</p>
<p>RDEFINE FACILITY IRR.RADMIN.LISTUSER UACC(READ)</p>
<p>RDEFINE FACILITY IRR.RADMIN.LISTGRP UACC(READ)</p>
<p>RDEFINE FACILITY IRR.RADMIN.RLIST UACC(READ)</p>
<p>RDEFINE FACILITY IRR.RADMIN.SETROPTS.LIST UACC(READ)</p></td>
</tr>
</tbody>
</table>

If you defined the previous facilities as UACC(NONE), you must set READ rights each Transfer CFT user.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PERMIT IRR.RADMIN.LISTUSER -CLASS(FACILITY) ACCESS(READ) ID(user)</p>
<p>PERMIT IRR.RADMIN.LISTGRP -CLASS(FACILITY) ACCESS(READ) ID(user)</p>
<p>PERMIT IRR.RADMIN.RLIST -CLASS(FACILITY) ACCESS(READ) ID(user)</p>
<p>PERMIT IRR.RADMIN.SETROPTS.LIST -CLASS(FACILITY) ACCESS(READ) ID(user)</p></td>
</tr>
</tbody>
</table>

In Transfer CFT, set the group\_database to system.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>UCONFSET ID=am.internal.group_database,value=system</td>
</tr>
</tbody>
</table>

### Using SAF class as the internal access management

With the **SAF class** method of access management, you define the mapping between predefined roles and resources in UCONF, and you define the user classes at the system level using a SAF (System Authorization Facility) class.

When the access management method is **SAF class**, each user role is associated with a security resource (RACF, TSS, ACF2). You can set the name of the resource in the corresponding UCONF variable using the user norms in the table below.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Example resource name</th>
<th>UCONF variable/role</th>
<th>Access to resource</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>CFT.ROLE.ADMIN</td>
<td>am.internal.role.admin</td>
<td>READ</td>
</tr>
<tr class="even">
<td>CFT.ROLE.OPERATOR</td>
<td>am.internal.role.helpdesk</td>
<td>READ</td>
</tr>
<tr class="odd">
<td>CFT.ROLE.PARTNER</td>
<td>am.internal.role.partnermanager</td>
<td>READ</td>
</tr>
<tr class="even">
<td>CFT.ROLE.DESIGNER</td>
<td>am.internal.role.designer</td>
<td>READ</td>
</tr>
<tr class="odd">
<td>CFT.ROLE.TRANSFER</td>
<td>am.internal.role.application</td>
<td>READ</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>UCONFSET ID=am.internal.group_database,value=<strong>safclass</strong></p>
<p>UCONFSET ID=am.internal.safclass,value='<strong>Class</strong>' (the class resource must be available)</p>
<p> </p>
<p>For each ROLE (the following are examples, replace with your own values):</p>
<div>
<blockquote>
<p>RDEFINE Class CFT.ROLE.ADMIN UACC(NONE) OWNER(...)</p>
<p>RDEFINE Class CFT.ROLE.OPERATOR UACC(NONE) OWNER(...)</p>
<p>RDEFINE Class CFT.ROLE.PARTNER UACC(NONE) OWNER(...)</p>
<p>RDEFINE Class CFT.ROLE.DESIGNER UACC(NONE) OWNER(...)</p>
<p>RDEFINE Class CFT.ROLE.TRANSFER UACC(NONE) OWNER(...)</p>
</blockquote>
</div>
<p> </p>
<p>Authorize users or groups: (RACF sample)</p>
<div>
<blockquote>
<p>PERMIT CFT.ROLE.ADMIN CLASS(Class) ACCESS(READ) ID(USER001)</p>
<p>PERMIT CFT.ROLE.TRANSFER CLASS(Class) ACCESS(READ) ID(USER002)</p>
</blockquote>
</div>
<p> </p>
<p>NOTE: ACCESS must be set to <strong>READ</strong>.</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The load libraries must be APF.</td>
</tr>
</tbody>
</table>

### Using file as the internal access management

With **file** type access management, you define the mapping between predefined roles and groups in UCONF, and assign the user groups in an external file.

When using this type of access management, the file format must be VB, where the maximum number of lrecl is 1024. Enter the character \* in column 1 to allow comments.

#### User/Group record description

Start with the UserID in column 1 using blanks as separators. For example, to assign users rights, use the format:

Format

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>USER001 OPERATOR PARTNER .....</p>
<p>USER002 ADMIN ..... </p></td>
</tr>
</tbody>
</table>

In Transfer CFT, set the group\_database to file and specify the path to the file defined above.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>UCONFSET ID=am.internal.group_database,value=file</p>
<p>UCONFSET ID=am.internal.group_database.fname,value=filename</p></td>
</tr>
</tbody>
</table>
