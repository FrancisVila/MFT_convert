{
    "title": "Password management",
    "linkTitle": "Password management",
    "weight": "260"
}This section describes how to implement three different types of password management. For each of these methods, an example is provided that shows the server side configuration and an example user command from the client side. These management types are:

-   [Static passwords](#static)
-   [External flat files](#external)
-   [System level authentication](#system)

## About RPASSWD and SPASSWD<span id="kanchor30"></span><span id="kanchor31"></span>

In addition to RUSER or SUSER, you can provide a password in the RPASSWD/SPASSWD fields to have user authentication, the same as users had if previously using FTP/SSH.

RPASSWD and SPASSWD can be provided directly as mypassw123, through an external flat file such as @fname,or using another system. Other system types include:

-   Operating System User Management
-   Transfer CFT UI User Access Base ([xfbadm](../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities))
-   Access Management System ([PassPort AM](../../internal_a_m_start_here/about_passport_am), [AM exit](../../internal_a_m_start_here/am_exits))

To use one of these other systems, set the rpasswd/spasswd to the keyword \_AUTH\_ value and the cft.server.authentication\_method parameter to the appropriate authentication method. See also, [UCONF parameters](../../admin_intro/uconf/uconf_directory).

## <span id="Static"></span>Static passwords

### Sending a file to the server

#### Server: static configuration

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTRECV</p>
            <p>id=idf01,</p>
            <p>ruser=username01,</p>
            <p>rpasswd=password01</p>
         </td>
      </tr>
   </tbody>
</table>

#### Client: user command

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SEND part=server, idf=idf0, ruser=username01, rpasswd=password01</p>
         </td>
      </tr>
   </tbody>
</table>

### Receiving a file from the server

#### Server: static configuration

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTSEND</p>
            <p>id=idf01,</p>
            <p>imply=yes,</p>
            <p>fname=file01,</p>
            <p>suser=username01,</p>
            <p>spasswd=password01</p>
         </td>
      </tr>
   </tbody>
</table>

#### Client: user command  

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RECV part=server, idf=idf01, suser=username01, spasswd=password01         </td>
      </tr>
   </tbody>
</table>

## <span id="External"></span>External flat files

The file containing the passwords must have the format:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>partner01 username01 password01</p>
            <p>partner01 username02 password02</p>
            <p>*         username01 password03</p>
            <p>*         *          password04</p>
         </td>
      </tr>
   </tbody>
</table>

### Sending a file to the server

#### Server: static configuration

##### Unix

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTRECV</p>
            <p>id=idf01,</p>
            <p>rpasswd=@passwfile</p>
         </td>
      </tr>
   </tbody>
</table>

##### Windows

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>Windows</p>
            <p>CFTRECV</p>
            <p>id=idf01,</p>
            <p>rpasswd=#passwfile</p>
         </td>
      </tr>
   </tbody>
</table>

#### Client: user command

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>SEND part=server, idf=idf01, ruser=username01, rpasswd=password01</p>
         </td>
      </tr>
   </tbody>
</table>

### Receiving a file from the server

#### Server: static configuration

##### Unix

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTSEND</p>
            <p>id=idf01,</p>
            <p>imply=yes,</p>
            <p>fname=file01,</p>
            <p>spasswd=@passwfile</p>
         </td>
      </tr>
   </tbody>
</table>

##### Windows

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTSEND</p>
            <p>id=idf01,</p>
            <p>imply=yes,</p>
            <p>fname=file01,</p>
            <p>spasswd=#passwfile</p>
         </td>
      </tr>
   </tbody>
</table>

#### Client: user command

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>RECV part=server, idf=idf01, suser=username01, spasswd=password01         </td>
      </tr>
   </tbody>
</table>

## <span id="System"></span>System level authentication

In addition to RPASSWD and SPASSWD you must specified the authentication method (uconf:cft.server.authentication\_method) to use.

The supported authentication methods are:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Authentication method</th>
         <th>copilot.restapi.authentication_method</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Operating System         </td>
         <td>system         </td>
         <td>
            <p>The user/password is  checked against the operating system. </p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
            <p><b>Unix </b>
</p>
            <p>You must use <span>cftsu </span>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to  <a href="../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix">Using system users - UNIX</a> for details.</p>
            <ul>
               <li>Create a group "group1": <span>groupadd group1</span>               </li>
               <li>Add user "user1" to group "group1": <span>usermod -a -G group1 user1</span>               </li>
            </ul>
            <p><b>Windows </b>
</p>
            <p>You require a superuser (administrative user account) to create a group and assign a user to a group.</p>
            <ul>
               <li>Create a group "group1": <span>net localgroup group1 /add</span>               </li>
               <li>Add user "user1" to group "group1": <span>net localgroup group1 user1 /add</span>               </li>
            </ul>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>Access Management         </td>
         <td>am         </td>
         <td>
            <p>This methods uses an indirection towards the Access Management system. The user/password is checked by the configured access management system: <span>Flow Manager</span>, PassPort AM, or internal AM.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>xfbadm database  </p>
            <p>(UNIX and HP NonStop exclusively)</p>
         </td>
         <td>xfbadm          </td>
         <td>
            <p>The user/password is checked using the xfbadm base (see the <a href="../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr and xfbadmgrp utilities</a>).</p>
            <p>A user that can execute xfbadmusr/xfbadmgrp utilities can create users and groups after executing the <span>profile </span>from the runtime directory.</p>
<ol>
               <li value="1">Create a group "group1" with gid=200:<span> xfbadmgrp add -G group1 -p group1_pw -g 200</span>               </li>
               <li value="2">From the user prompt, to add a user "user1" to group "group1"enter: <span>xfbadmusr add -l user1 -p user1_pw -u AUTO -g 200</span>               </li>
</ol>
         </td>
      </tr>
   </tbody>
</table>

<span id="REST"></span>REST API server authentication method

![](authentication_copilot_server.png)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">We strongly recommend that you set <span>copilot.misc.createprocessasuser=</span><span>yes </span>when using the system option.         </td>
      </tr>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For a user belonging to a domain, use: <span>domain\user1</span> instead of <span>user1</span>         </td>
      </tr>
</table>

### Sending a file to the server

#### Server: static configuration

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">1. If copilot.restapi.authentication_method = system, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = system.         </td>
      </tr>
</table>

#### Client: user command

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">2.  If copilot.restapi.authentication_method = xbfadm, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = xbfadm.          </td>
      </tr>
</table>

In this case, username01/password01 is compared with what is defined in uconf: cft.server.authentication\_method.

### Receiving a file from the server

#### Server: static configuration

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTRECV</p>
            <p>id=idf01,</p>
            <p>rpasswd=_AUTH_</p>
            <p>uconfset id=cft.server.authentication_method, value=system</p>
         </td>
      </tr>
   </tbody>
</table>

#### Client: user command

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>SEND part=server, idf= idf01, ruser=username01, rpasswd=password01         </td>
      </tr>
   </tbody>
</table>

In this case, username01/password01 is compared with what is defined in uconf: cft.server.authentication\_method.
