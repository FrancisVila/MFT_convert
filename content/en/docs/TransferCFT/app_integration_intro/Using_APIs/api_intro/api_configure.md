{
    "title": "REST API server configuration",
    "linkTitle": "REST API server configuration",
    "weight": "310"
}Before you can start using REST API operations with Transfer CFT, you need to set a few parameters in the Transfer CFT configuration.

## Before you start

The REST server is a Copilot service. To start the REST server, use the copstart command to [start Copilot](../../../admin_intro/manage_copilot).

## Procedure

Transfer CFT requires the following configuration settings before you can use REST API.

1.  Enable the Copilot REST API if you did not do so during installation.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=copilot.restapi.enable, value=yes         </td>
          </tr>
       </tbody>
    </table>
2.  Optionally, you can change the REST API server port as follows (default 1768):  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=copilot.restapi.serverport, value=&lt;new port&gt;         </td>
          </tr>
       </tbody>
    </table>
3.  You require a secure SSL/TLS communication between the client (REST or browser) and the REST server. When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the [registration](../../../governance_services_intro/cg_register_overview); there is no need to perform this step. This certificate is stored in the internal PKI base and is identified by the Transfer CFT instance ID (uconf:cft.instance\_id).  
    Otherwise, use UCONF to set the following Copilot parameters to configure the SSL certificate.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTUTIL uconfset id=copilot.ssl.SslCertFile, value=&lt;ssl pkcs12 certificate for copilot&gt;</p>
                <p>CFTUTIL uconfset id=copilot.ssl.SslCertPassword, value=&lt;ssl pkcs12 certificate password&gt;</p>         </td>
          </tr>
       </tbody>
    </table>

      
    These parameter settings are described in [Install a certificate on the server side](../../../admin_intro/manage_copilot).  
4.  Specify the authentication method, as the client must provide credentials (user/password) to the REST server. Set the UCONF the copilot.restapi.authentication\_method parameter.  
    Example  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=copilot.restapi.authentication_method, value=system         </td>
          </tr>
       </tbody>
    </table>

The supported authentication methods are:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Authentication method</th>
         <th>copilot.restapi.authentication_method</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>Operating System         </td>
         <td>system         </td>
         <td>            <p>The user/password is checked against the operating system.</p>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">We strongly recommend that you set <span>copilot.misc.createprocessasuser=</span><span>yes </span>when using the system option.         </td>
      </tr>
   </tbody>
</table>
            <p><strong>Unix</strong></p>
            <p>You must use <span>cftsu </span>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to <a href="../UNIX/t_adding_system_user_unix.htm">Using system users - UNIX</a> for details.</p>
            <ul>
               <li>Create a group "group1": <span>groupadd group1</span>               </li>
               <li>Add user "user1" to group "group1": <span>usermod -a -G group1 user1</span>               </li>
            </ul>
            <p><strong>Windows</strong></p>
            <p>You require a superuser (administrative user account) to create a group and assign a user to a group.</p>
            <ul>
               <li>Create a group "group1": <span>net localgroup group1 /add</span>               </li>
               <li>Add user "user1" to group "group1": <span>net localgroup group1 user1 /add</span>               </li>
            </ul>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">For a user belonging to a domain, use: <span>domain\user1</span> instead of <span>user1</span>         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr class="even">
         <td>Access Management         </td>
         <td>am         </td>
         <td>            <p>This methods uses an indirection towards the Access Management system. The user/password is checked by the configured access management system: <span>Flow Manager</span>, PassPort AM, or internal AM.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>xfbadm database</p>
            <p>(UNIX and HP NonStop exclusively)</p>         </td>
         <td>xfbadm         </td>
         <td>            <p>The user/password is checked using the xfbadm base (see the <a href="../UNIX/UNIX_operations/Utilities/use_cft_utilities.htm">xfbadmusr and xfbadmgrp utilities</a>).</p>
            <p>A user that can execute xfbadmusr/xfbadmgrp utilities can create users and groups after executing the <span>profile </span>from the runtime directory.</p>
<ol>
               <li>Create a group "group1" with gid=200:<span> xfbadmgrp add -G group1 -p group1_pw -g 200</span>               </li>
               <li>From the user prompt, to add a user "user1" to group "group1"enter: <span>xfbadmusr add -l user1 -p user1_pw -u AUTO -g 200</span>               </li>
</ol>         </td>
      </tr>
   </tbody>
</table>

<span id="REST"></span>REST API server authentication method

![](/Images/TransferCFT/authentication_copilot_server.png)

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">1. If copilot.restapi.authentication_method = system, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = system.         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">2. If copilot.restapi.authentication_method = xbfadm, then your access management type must be set to either am.type= none, or both am.type=internal and am.internal.group_database = xbfadm.         </td>
      </tr>
   </tbody>
</table>

Parameter

Type

Default

Description

copilot.restapi.enable

bool

No

Enable/disable the REST API service:

-   Yes: enable
-   No: disable

copilot.restapi.serverport

int

1768

REST API server port.

copilot.restapi.authentication\_method

string

system (Windows)

xfbadm (UNIX)

Defines authentication method.

 

See also, [xfbadmusr utilitiy.](../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities)

copilot.restapi.nb\_workers

int

4

Number of activated workers that process the REST API requests.

copilot.restapi.maxclient

int

256

Number of client connections handled per REST worker.

copilot.restapi.coms\_id

string

coms

The TCPIP CFTCOM object identifier used by the REST API server to communicate with the Transfer CFT server.

Leave empty to use
the COM file instead.

copilot.restapi.catalog.retry\_delay

int

5

-   The delay between retries
    in seconds. The Copilot server checks the request status in catalog every retry\_delay seconds.
-   The delay between retries
    in seconds. The Copilot server checks the request status in catalog every retry\_delay seconds.

 

 

 

copilot.restapi.catalog.retry\_timeout

int

30

The default value of the [apiTimeout](api_commands) parameter as defined in the request URL.

Available exclusively for POST requests.
