{
    "title": "Internal access management",
    "linkTitle": "Internal access management",
    "weight": "160"
}This section describes how to configure Internal AM, which is a type of access management that you can use with or without Central Governance or Flow Manager governance.

Internal access management is an out-of-the-box access management based on predefined roles and privileges, and a group internal datafile. Groups and their members are defined in this supplied database. Note however that when using this type of access management, there is no super user and the user who installed and starts the Transfer CFT Copilot server must have Administrator rights. <span id="security_base"></span>

The supplied pre-defined roles are:

-   **Administrator**: Provides full user access
-   **Helpdesk**: Enables you to view the catalog and log
-   **Partner Manager**: Allows you to manage partners
-   **Designer**: Allows you to manage application flows
-   **Application**: Allows applications to request and manage transfers, and view the catalog

Additionally you can:

-   **Custom**: Create new roles

Please refer to the [*Transfer CFT *3.9 *Security Guide*](https://docs.axway.com/bundle/TransferCFT_36_SecurityGuide_allOS_en_HTML5/page/Content/security_guide/predefined_privileges.htm) for a complete list of privileges and roles. Login is required. Additionally, the Internal AM use cases page describes three use cases and their configuration.

## Configuring internal access management

Set the specific group database parameter (see the table below for OS specifics) using CFTUTIL:

uconfset id=am.internal.group\_database,value=\[ system | safClass | file | xfbadm \]

Use the parameters and descriptions in the AM Parameters table (just below Step 3) to help you customize the internal access management roles. For example, to assign the administrator role to the "admin" group:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>AM Parameters</th>
         <th>Default</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>am.internal.group_database         </td>
         <td>            <p>file (z/OS)</p>
            <p>system (all other platforms)</p>         </td>
         <td>            <p>Group database where group members are defined.</p>
            <ul>
               <li>system (UNIX, Windows, and IBM i): the groups are defined in the OS group database (Unix, Windows, IBM i - see <a href="../cft_intro_install/about_this_document_ibmi/install_intro_ibmi/access-managment_ibmi">security base</a>)               </li>
               <li>system (z/OS only): the service 'IRRSEQ00' is used to recall the user's groups from RACF, for example:
            <ul>
               <li>            <p>USER001 ADMIN OPERATOR PARTNER DESIGNER TRANSFER</p>               </li>
               <li>            <p>USER002 DESIGNER</p>               </li>
            </ul>               </li>
               <li>            <p>safClass (z/OS only): the resources are defined in the SAF (System Authorization Facility) where Transfer CFT maps the groups to resources - see the <em><a href="../cft_intro_install/about_this_document_zos"><em>Transfer CFT z/OS Installation and Operation Guide</em></a></em> for details</p>               </li>
               <li>file (z/OS): a variable file containing a users list and a groups list               </li>
               <li>xfbadm (UNIX, HP NonStop): the groups are defined in the xfbadm database; see Transfer CFT
control utilities               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>am.internal.group_database.fname         </td>
         <td>          </td>
         <td>            <p>If you set am.internal.group_database=file, you must define this file name, which is a variable file containing the groups associated with each user.</p>
            <p>For example:</p>
            <ul>
               <li>USER001 group01 group02 group04               </li>
               <li>USER002 group04 group05               </li>
            </ul>
            <p>Where the groups are mapped as shown in the example <a href="#Mapping">mapping</a> table below.</p>         </td>
      </tr>
      <tr class="odd">
         <td>am.internal.role.admin         </td>
         <td>          </td>
         <td>            <p>Admin role and groups mapping. This role enables you to perform all administrative tasks.</p>
            <ul>
               <li>List of groups (blank separator)               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>am.internal.role.helpdesk         </td>
         <td>          </td>
         <td>            <p>Help Desk role and groups mapping. This role enables you to view the log, transfers and configuration.</p>
            <ul>
               <li>List of groups (blank separator)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td>am.internal.role.partnermanager         </td>
         <td>          </td>
         <td>            <p>Partner Manager role and groups mapping. This role enables you to create and manage partner.</p>
            <ul>
               <li>List of groups (blank separator)               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>am.internal.role.designer         </td>
         <td>          </td>
         <td>            <p>Designer role and groups mapping. This role enables you to manage flows.</p>
            <ul>
               <li>List of groups (blank separator)               </li>
            </ul>         </td>
      </tr>
      <tr class="odd">
         <td>am.internal.role.application         </td>
         <td>          </td>
         <td>            <p>Application role and groups mapping. This role enables application to send transfers.</p>
            <ul>
               <li>List of groups (blank separator)               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>am.internal.persistence_timeout         </td>
         <td>300         </td>
         <td>            <p>Delay in seconds between updating the list of group that a user belongs to.</p>         </td>
      </tr>
   </tbody>
</table>

Set the access management type:

uconfset id=am.internal.role.admin,value=admin

uconfset id=am.type,value=internal

## <span id="Mapping"></span>Mapping the group to predefined roles

To use the feature you will need to map the list of groups in the database to the Transfer CFT predefined roles. Use the following information as a basis for your mapping. You can enter these values either using command line or in the Transfer CFT UI.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Means the user in this group will have the role...</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>am.internal.role.admin=group01         </td>
         <td>The user who belongs to group “group01” has the admin role.         </td>
      </tr>
      <tr class="even">
         <td>am.internal.role.helpdesk=group02         </td>
         <td>The user who belongs to group “group02” has the “helpdesk” role.         </td>
      </tr>
      <tr class="odd">
         <td>am.internal.role.partnermanager=group03         </td>
         <td>The user who belongs to group “group03” has the “partner manager” role.         </td>
      </tr>
      <tr class="even">
         <td>am.internal.role.designer =group04         </td>
         <td>The user who belongs to group “group04” has the “designer” role.         </td>
      </tr>
      <tr class="odd">
         <td>am.internal.role.application=group05         </td>
         <td>The user who belongs to group “group05” has the “application” role.         </td>
      </tr>
   </tbody>
</table>

## Creating or modifying roles

In addition to the out-of-the box roles, you can create new roles or modify existing roles using either the Transfer CFT user interface or a Transfer CFT configuration file. You can use new or modified roles on their own or in combination with predefined roles. Please refer to Internal AM use cases for role-based use case scenarios.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When <span>Central Governance</span> is managing your <span>Transfer CFT</span>s, you should manage CFTROLE and CFTPRIVILEGE locally for each <span>Transfer CFT</span>.         </td>
      </tr>
   </tbody>
</table>

### Using the configuration file

You can add, remove, or modify roles or privileges in the role-smp.conf sample file delivered in runtime/conf/ directory. After adding or modifying a role or privilege, you must interpret the configuration file.

### Using the user interface

In the Transfer CFT UI, access the General Configuration pane and select either **Privileges** or **Roles**. Options include creating, deleting, modifying, or cloning a role or privilege.

 

### Role priority

When using a combination of predefined roles and custom roles that you created in the CFTPARM object, the new roles will override existing roles if they have the same name. For example, if you create two roles in CFTPARM with sames identifiers as predefined roles:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTROLE ID='HELPDESK', ...</p>
            <p>CFTROLE ID='APPLICATION', ...</p>         </td>
      </tr>
   </tbody>
</table>

Here, the new HELPDESK and APPLICATION roles override the predefined HELPDESK and APPLICATION roles. However, the predefined ADMIN, PARTNERMANAGER, and DESIGNER roles are still used since you did not create new roles with these same names.

## Internal access management use cases

This section describes three configuration scenarios when using [internal access management](#) with roles and privileges. Use cases include:

-   Predefined roles and privileges without the CFTPRIV and CFTROLE objects
-   Customized roles and privileges with the CFTPRIV and CFTROLE objects
-   Mixed-use of both predefined and custom CFTPRIV and CFTROLE objects

In each scenario, there is a **user1** that belongs to **group1** and a **user2** that belongs to **group2**.

Example 1: Use only predefined roles and privileges

If you configure UCONF as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>uconfset id=am.internal.group_database,value=system         NOTE: system (Unix,Windows), xfbadm (Unix,HP NonStop)</p>
            <p>uconfset id=am.internal.role.admin,value=group1</p>
            <p>uconfset id=am.internal.role.application,value=group2</p>
            <p>uconfset id=am.type,value=internal</p>         </td>
      </tr>
   </tbody>
</table>

To view the results:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>listuconf id=am.internal.role.*</p>
            <p> </p>
            <p>U am.internal.role.admin = group1</p>
            <p>D am.internal.role.helpdesk =</p>
            <p>D am.internal.role.partnermanager =</p>
            <p>D am.internal.role.designer =</p>
            <p>U am.internal.role.application = group2</p>
            <p> </p>
            <p>listparm type=role,content=brief</p>
            <p>CFTU24W LISTPARM _ Warning ( Parameters no record selected / file empty)</p>         </td>
      </tr>
   </tbody>
</table>

To check that you are using only predefined roles and privileges, enter:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>listparm type=role,content=brief</p>
            <p>CFTU24W LISTPARM _ Warning ( Parameters no record selected / file empty)</p>         </td>
      </tr>
   </tbody>
</table>

**Results**

-   User1 has the predefined Transfer CFT Administrator role
-   User2 has the predefined Transfer CFT Application role

Example 2: Custom roles and privileges using only CFTPRIV and CFTROLE objects

If you configure UCONF as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>uconfset id=am.internal.group_database,value=system     NOTE: system (Unix,Windows), xfbadm (Unix,HP NonStop)</p>
            <p>uconfset id=am.type,value=internal</p>
            <p>listuconf id=am.internal.role.*</p>
            <p> </p>
            <p>D am.internal.role.admin =</p>
            <p>D am.internal.role.helpdesk =</p>
            <p>D am.internal.role.partnermanager =</p>
            <p>D am.internal.role.designer =</p>
            <p>D am.internal.role.application =</p>         </td>
      </tr>
   </tbody>
</table>

Modify the conf/roles-smp.conf sample file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTROLE ID = 'TRANSFER CFT ADMINISTRATOR',</p>
            <p>COMMENT = 'Enables full management of Transfer CFT.',</p>
            <p>ALIASES = ( 'group1' ),</p>
            <p>PRIVS = ( 'SWITCH ACCOUNTS', ...</p>
            <p> </p>
            <p>CFTROLE ID = 'TRANSFER CFT APPLICATION',</p>
            <p>COMMENT = 'Enables applications to send transfers.',</p>
            <p>ALIASES = ( 'group2' ) ,</p>
            <p>PRIVS = ( 'FILE VIEW' ,...</p>         </td>
      </tr>
   </tbody>
</table>

Interpret the modified file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>config type=input,fname=$CFTDIRRUNTIME/conf/roles-smp.conf</p>
            <p>listparm type=role,content=brief</p>
            <p>Type ID Information</p>
            <p>-------- -------------------- ---------------------------------------</p>
            <p>ROLE TRANSFER CFT ADMINISTRATOR Enables full management of Transfer CFT.</p>
            <p>ROLE TRANSFER CFT APPLICATION Enables applications to send transfers.</p>
            <p>ROLE TRANSFER CFT DESIGNER</p>
            <p>ROLE TRANSFER CFT HELPDESK</p>
            <p>ROLE TRANSFER CFT PARTNERMANAGER</p>         </td>
      </tr>
   </tbody>
</table>

**Results**

-   User1 has the custom Transfer CFT Administrator role defined in CFTROLE id='TRANSFER CFT ADMINISTRATOR',aliases=group1
-   User2 has the custom Transfer CFT Application role defined in CFTROLE id='TRANSFER CFT APPLICATION',aliases=group2

Example 3: Uses both predefined and customized CFTPRIV and CFTROLE objects

If you configure UCONF as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>uconfset id=am.internal.role.admin, value=group1</p>
            <p>listuconf id=am.internal.role.*</p>
            <p> </p>
            <p>U am.internal.role.admin = group1</p>
            <p>D am.internal.role.helpdesk =</p>
            <p>D am.internal.role.partnermanager =</p>
            <p>D am.internal.role.designer =</p>
            <p>U am.internal.role.application =</p>
            <p>listparm type=role,content=brief</p>
            <p>Type ID Information</p>
            <p>-------- -------------------- ---------------------------------------</p>
            <p>ROLE TRANSFER CFT ADMINISTRATOR Enables full management of Transfer CFT.</p>
            <p>ROLE TRANSFER CFT APPLICATION Enables applications to send transfers.</p>
            <p>ROLE TRANSFER CFT DESIGNER</p>
            <p>ROLE TRANSFER CFT HELPDESK</p>
            <p>ROLE TRANSFER CFT PARTNERMANAGER</p>         </td>
      </tr>
   </tbody>
</table>

Modify the conf/roles-smp.conf sample file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTROLE ID = 'TRANSFER CFT APPLICATION',</p>
            <p>COMMENT = 'Enables applications to send transfers.',</p>
            <p>ALIASES = ( 'group2' ) ,</p>
            <p>PRIVS = ( 'FILE VIEW' ,...</p>         </td>
      </tr>
   </tbody>
</table>

Interpret the modified file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>config type=input,fname=$CFTDIRRUNTIME/conf/roles-smp.conf</p>
            <p>listparm type=role,content=brief</p>
            <p>Type ID Information</p>
            <p>-------- -------------------- ---------------------------------------</p>
            <p>ROLE TRANSFER CFT ADMINISTRATOR Enables full management of Transfer CFT.</p>
            <p>ROLE TRANSFER CFT APPLICATION Enables applications to send transfers.</p>
            <p>ROLE TRANSFER CFT DESIGNER</p>
            <p>ROLE TRANSFER CFT HELPDESK</p>
            <p>ROLE TRANSFER CFT PARTNERMANAGER</p>         </td>
      </tr>
   </tbody>
</table>

**Results**

-   User1 has the predefined Transfer CFT Administrator role
-   User2 has the custom Transfer CFT Application role defined in CFTROLE id='TRANSFER CFT APPLICATION',aliases=group2
