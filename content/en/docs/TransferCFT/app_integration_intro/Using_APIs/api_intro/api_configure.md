{
    "title": "REST\u00a0API server configuration",
    "linkTitle": "REST\u00a0API server configuration",
    "weight": "310"
}Before you can start using REST API operations with Transfer CFT, you need to set a few parameters in the Transfer CFT configuration.

## Before you start

The REST server is a Copilot service. To start the REST server, use the copstart command to [start Copilot](../../../../admin_intro/manage_copilot).

## Procedure

Transfer CFT requires the following configuration settings before you can use REST API.

1.  Enable the Copilot REST API if you did not do so during installation.  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL uconfset id=copilot.restapi.enable, value=yes         </td>
      </tr>
   </tbody>
</table>

2.  Optionally, you can change the REST API server port as follows (default 1768):  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL uconfset id=copilot.restapi.serverport, value=&lt;new port&gt;         </td>
      </tr>
   </tbody>
</table>

3.  You require a secure SSL/TLS communication between the client (REST or browser) and the REST server. When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the [registration](../../../../governance_services_intro/cg_register_overview); there is no need to perform this step. This certificate is stored in the internal PKI base and is identified by the Transfer CFT instance ID (uconf:cft.instance\_id).  
    Otherwise, use UCONF to set the following Copilot parameters to configure the SSL certificate.   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL uconfset id=copilot.ssl.SslCertFile, value=&lt;ssl pkcs12 certificate for copilot&gt;</p>
            <p>CFTUTIL uconfset id=copilot.ssl.SslCertPassword, value=&lt;ssl pkcs12 certificate password&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

      
    These parameter settings are described in [Install a certificate on the server side](../../../../admin_intro/manage_copilot).  

4.  Specify the authentication method, as the client must provide credentials (user/password) to the REST server. Set the UCONF the copilot.restapi.authentication\_method parameter.   
    Example  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL uconfset id=copilot.restapi.authentication_method, value=system         </td>
      </tr>
   </tbody>
</table>

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
            <p>You must use <span>cftsu </span>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to  <a href="../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/run_first_time_ux/t_adding_system_user_unix">Using system users - UNIX</a> for details.</p>
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
            <p>The user/password is checked using the xfbadm base (see the <a href="../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities">xfbadmusr and xfbadmgrp utilities</a>).</p>
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
