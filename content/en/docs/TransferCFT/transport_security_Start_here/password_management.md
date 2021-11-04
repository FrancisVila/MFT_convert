{
    "title": "Password management (SPASSWD)",
    "linkTitle": "Password management",
    "weight": "240"
}This section describes how to implement three different types of password management. For each of these methods, an example is provided that shows the server side configuration and an example user command from the client side. These management types are:

-   [Static passwords](#Static)
-   [External flat files](#External)
-   [System level authentication](#System)

<span id="kanchor29"></span><span id="kanchor30"></span>

## About RPASSWD and SPASSWD

In addition to RUSER or SUSER, you can provide a password in the RPASSWD/SPASSWD fields to have user authentication, the same as users had if previously using FTP/SSH.

RPASSWD and SPASSWD can be provided directly as <span class="bold_in_para">mypassw123</span>, through an external flat file such as <span class="bold_in_para">@fname</span>,or using another system. Other system types include:

-   Operating System User Management
-   Transfer CFT UI User Access Base ([xfbadm](../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities#xfbadmusr1))
-   Access Management System ([PassPort AM](../../internal_a_m_start_here/about_passport_am), [AM exit](../../internal_a_m_start_here/am_exits))

To use one of these other systems, set the <span class="code">rpasswd/spasswd </span>to the<span class="code"> keyword \_AUTH\_</span> value and the <span class="code">cft.server.authentication\_method</span> parameter to the appropriate authentication method. See also, <a href="../../admin_intro/uconf/uconf_directory" class="MCXref xref">UCONF parameters</a>.

<span id="Static"></span>

## Static passwords

### Sending a file to the server

#### Server: static configuration



    CFTRECV
    id=idf01,
    ruser=username01,
    rpasswd=password01

#### Client: user command



    SEND part=server, idf=idf0, ruser=username01, rpasswd=password01

### Receiving a file from the server

#### Server: static configuration



    CFTSEND
    id=idf01,
    imply=yes,
    fname=file01,
    suser=username01,
    spasswd=password01

#### Client: user command  


    RECV part=server, idf=idf01, suser=username01, spasswd=password01

<span id="External"></span>

## External flat files

The file containing the passwords must have the format:



    partner01 username01 password01
    partner01 username02 password02
    *         username01 password03
    *         *          password04

### Sending a file to the server

#### Server: static configuration

##### Unix



    CFTRECV
    id=idf01,
    rpasswd=@passwfile

##### Windows



    Windows
    CFTRECV
    id=idf01,
    rpasswd=#passwfile

#### Client: user command



    SEND part=server, idf=idf01, ruser=username01, rpasswd=password01

### Receiving a file from the server

#### Server: static configuration

##### Unix



    CFTSEND
    id=idf01,
    imply=yes,
    fname=file01,
    spasswd=@passwfile

##### Windows



    CFTSEND
    id=idf01,
    imply=yes,
    fname=file01,
    spasswd=#passwfile

#### Client: user command


    RECV part=server, idf=idf01, suser=username01, spasswd=password01

<span id="System"></span>

## System level authentication

In addition to RPASSWD and SPASSWD you must specified the authentication method (uconf:cft.server.authentication\_method) to use.

The supported authentication methods are:

<table>
   <th>
      <tr>
<th>Authentication method         </th>
<th>copilot.restapi.authentication_method         </th>
<th>Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Operating System         </td>
         <td>system         </td>
         <td><p>The user/password is checked against the operating system.</p>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>We strongly recommend that you set <span class="code">copilot.misc.createprocessasuser=</span><span class="code" style="font-weight: bold;">yes </span>when using the system option.         </td>
      </tr>
   </tbody>
</table>
<p><strong>Unix</strong></p>
<p>You must use <span class="code">cftsu </span>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to <a href="#" class="MCXref xref">Using system users - UNIX</a> for details.</p>
<ul>
<li>Create a group "group1": <span style="font-family: &#39;Courier New&#39;;">groupadd group1</span></li>
<li>Add user "user1" to group "group1": <span style="font-family: &#39;Courier New&#39;;">usermod -a -G group1 user1</span></li>
</ul>
<p><strong>Windows</strong></p>
<p>You require a superuser (administrative user account) to create a group and assign a user to a group.</p>
<ul>
<li>Create a group "group1": <span style="font-family: &#39;Courier New&#39;;">net localgroup group1 /add</span></li>
<li>Add user "user1" to group "group1": <span style="font-family: &#39;Courier New&#39;;">net localgroup group1 user1 /add</span></li>
</ul>
<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>For a user belonging to a domain, use: <span style="font-family: &#39;Courier New&#39;;">domain\user1</span> instead of <span style="font-family: &#39;Courier New&#39;;">user1</span>         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr>
         <td>Access Management         </td>
         <td>am         </td>
         <td><p>This methods uses an indirection towards the Access Management system. The user/password is checked by the configured access management system: <span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span>, PassPort AM, or internal AM.</p>         </td>
      </tr>
      <tr>
         <td><p>xfbadm database</p>
<p>(UNIX and HP NonStop exclusively)</p>         </td>
         <td>xfbadm         </td>
         <td><p>The user/password is checked using the xfbadm base (see the <a href="../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr and xfbadmgrp utilities</a>).</p>
<p>A user that can execute xfbadmusr/xfbadmgrp utilities can create users and groups after executing the <span class="code">profile </span>from the runtime directory.</p>
<ol>
<li>Create a group "group1" with gid=200:<span style="font-family: &#39;Courier New&#39;;"> xfbadmgrp add -G group1 -p group1_pw -g 200</span></li>
<li>From the user prompt, to add a user "user1" to group "group1"enter: <span style="font-family: &#39;Courier New&#39;;">xfbadmusr add -l user1 -p user1_pw -u AUTO -g 200</span></li>
</ol>         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span><span id="REST"></span>REST API server authentication method

<span class="autonumber"></span>
<img src="/Images/TransferCFT/authentication_copilot_server.png" class="maxWidth" />

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>1. If copilot.restapi.authentication_method = system, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = system.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>2. If copilot.restapi.authentication_method = xbfadm, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = xbfadm.         </td>
      </tr>
   </tbody>
</table>

### Sending a file to the server

#### Server: static configuration



    CFTRECV
    id=idf01,
    rpasswd=_AUTH_
    uconfset id=cft.server.authentication_method, value=system

#### Client: user command


    SEND part=server, idf= idf01, ruser=username01, rpasswd=password01

In this case, username01/password01 is compared with what is defined in <span class="code">uconf: cft.server.authentication\_method</span>.

### Receiving a file from the server

#### Server: static configuration



    CFTSEND
    id=idf01,
    imply=yes,
    fname=file01,
    spasswd=_AUTH_
    uconfset id=cft.server.authentication_method, value=system

#### Client: user command


    RECV part=server, idf= idf01, suser=username01, spasswd=password01

In this case, username01/password01 is compared with what is defined in <span class="code">uconf: cft.server.authentication\_method</span>.
