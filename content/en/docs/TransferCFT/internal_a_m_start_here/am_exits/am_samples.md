{
    "title": "Delivered Access Management exit samples",
    "linkTitle": "Delivered exit samples",
    "weight": "210"
}This section describes how to configure access management when not using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

Axway delivers an Access Management exit sample, examsmp1.c, in the <span class="code">&lt;CFTDIRRUNTIME>/src/exit</span> directory.

### Services provided by delivered sample

The delivered sample provides two services, authentication and permissions checking.

<table>
   <th>
      <tr>
<th>Sample         </th>
<th>Authentication         </th>
<th>Permissions checking         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>examsmp1.c         </td>
         <td>System authentication (<span class="italic_in_para">Windows only</span>)         </td>
         <td>Flat file based on flat <a href="#" class="MCTextPopup popup popupHead">RBAC<span class="MCTextPopupBody MCTextPopupBody_Closed needs-pie popupBody" aria-hidden="true"><span class="MCTextPopupArrow"> </span>Role Based Access Control</span></a> model         </td>
      </tr>
   </tbody>
</table>

### Building the dynamic library associated with the sample

To build the exit:

Change the directory to: &lt;CFTDIRRUNTIME>/src/exit

Run the following command:

-   UNIX: <span class="code">make</span>
-   Windows: <span class="code">nmake -f exit.mak</span>

The output is a library located at <span class="code">&lt;CFTDIRRUNTIME>/lib/libcftexam.(so/dll)</span>.

## Flat file based on flat RBAC 

To check users rights, Axway delivers a sample flat file based on flat <a href="#" class="MCTextPopup popup popupHead">RBAC<span class="MCTextPopupBody MCTextPopupBody_Closed needs-pie popupBody" aria-hidden="true"><span class="MCTextPopupArrow"> </span>Role Based Access Control</span></a> (Role Based Access Control) located in: <span class="code">&lt;CFTDIRRUNTME>/conf/exam.csv</span>. This file contains a set of permission and user assignments.

![Simplied diagram of relationship between users, roles and permissions](/Images/TransferCFT/am_exits_rbac.GIF)

## Assigning permission

The following line shows how to add a permission to a role:  
<span class="code">&lt;cmd\_type> &lt;role> &lt;resource> &lt;actions> &lt;policy></span>

Where:

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>&lt;cmd_type&gt;         </td>
         <td>PA for Permission Assignment         </td>
      </tr>
      <tr>
         <td>&lt;role&gt;         </td>
         <td>The role for which the permission must be assigned         </td>
      </tr>
      <tr>
         <td>&lt;resource&gt;         </td>
         <td>Name of the resource         </td>
      </tr>
      <tr>
         <td>&lt;actions&gt;         </td>
         <td>List of actions with each action separated by a comma         </td>
      </tr>
      <tr>
         <td>&lt;policy&gt;         </td>
         <td>ACCEPT: accept the actions on the resource<br />
REFUSE: refuse the actions on the resource         </td>
      </tr>
   </tbody>
</table>

Examples

All available actions on the resource “CONFIGURATION:CFTPARM”:


    PA ADMIN    CONFIGURATION:CFTPARM   CREATE,DELETE,EDIT,VIEW     ACCEPT

or


    PA ADMIN    CONFIGURATION:CFTPARM   *                       ACCEPT

All available actions on resources that start with “CONFIGURATION:” for the ADMIN role:


    PA ADMIN    CONFIGURATION:*     *                           ACCEPT

All permissions for the ADMIN role:


    PA ADMIN    *           *   ACCEPT

All permissions for the ADMIN role except for the resource “TRANSFER”:


    PA ADMIN    TRANSFER        *   REFUSE
    PA ADMIN    *           *   ACCEPT

## Assigning users

The following line shows how to add a user to a role:  
<span class="code">&lt;cmd\_type> &lt;role> &lt;users></span>

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>&lt;cmd_type&gt;         </td>
         <td>UA for User Assignment         </td>
      </tr>
      <tr>
         <td>&lt;role&gt;         </td>
         <td>The role to which users must be assigned         </td>
      </tr>
      <tr>
         <td>&lt;users&gt;         </td>
         <td>List of users with each user separated by a comma         </td>
      </tr>
   </tbody>
</table>

#### Examples



    UA ADMIN    admin,user01,user02 
    UA DESIGNER user03
    UA HELPDESK user03,user04
    UA APPLICATION  user05

## Predefined roles

You can find some roles defined in &lt;CFTDIRRUNTIME>/conf/exam.csv.

Predefined roles

<table>
   <th>
      <tr>
<th>Role         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Administrator         </td>
         <td>Provides full user access         </td>
      </tr>
      <tr>
         <td>Helpdesk         </td>
         <td>Enables you to view the Catalog and Log         </td>
      </tr>
      <tr>
         <td>Partner Manager         </td>
         <td>Allows you to manage partners         </td>
      </tr>
      <tr>
         <td>Designer         </td>
         <td>Allows you to manage application flows         </td>
      </tr>
      <tr>
         <td>Application         </td>
         <td>Allows applications to request transfers and view the Catalog         </td>
      </tr>
   </tbody>
</table>

The resources and available actions for <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> are listed in the PassPort AM CSD file.

After installing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, access the CSD file:

&lt;Transfer CFT install directory>/distrib/am/csd\_Transfer\_CFT.xml

For more information, refer to the PassPort AM CSD.

Related topics

[About Access Management exits](../)

[Configuring an Access Management exit](../configure_am_exits)
