{
    "title": "Transfer CFT user interface",
    "linkTitle": "Transfer CFT UI ",
    "weight": "110"
}Transfer CFT features a web browser user interface that you can use to configure, track and manage transfers, and consult the  log. The following sections describe the steps you must perform before you can start using this user interface.

The Transfer CFT user interface requires secure SSL/TLS communication between the browser and the REST server, and for the REST API option to be enabled. If you performed a custom installation without these options, you must perform the following steps before connecting to the user interface.

1.  [Configure the REST API server.](#Configur2)
2.  [Set the Certificate Authority on the client side.](#Connect)

## Supported browsers

The user interface requires a web browser such as:

-   Google Chrome
-   Microsoft Edge version 41
-   Firefox (without keyboard shortcuts)

If there is a specified version, it is the minimum version for that browser.

## <span id="Connect2"></span>Connect to the user interface

Start the Copilot server before connecting as the REST API server.

The user that starts the Copilot server must have write permission for the Transfer CFT CFTCOM, CFTPART, CFTPARM, and CFTPKI data files.

1.  Start the Copilot server: copstart
2.  In your web browser, enter the URL using the following format: https://&lt;UI\_server\_host>:&lt;RestApi\_port>/cft/ui/  
    Example  
    https://10.128.14.139:1768/cft/ui/
3.  Enter your username and password (depending on the authentication method set on the server) where the username is limited to 32 characters.  
    The Transfer CFT interface displays. To use shortcuts, see [Keyboard shortcuts](#Keyboard). You are now ready to [configure](../CFTUTIL/Conf/conf_intro.htm) and [create flows](../CFTUTIL/Conf/flow_def_intro.htm).

## <span id="Configur2"></span>Configure the REST API server

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
3.  You require a secure SSL/TLS communication between the client (REST or browser) and the REST server. When using Central Governance, the REST API server automatically uses the SSL business certificate generated during the [registration](../central_governance/cg_register_overview.htm); there is no need to perform this step. This certificate is stored in the internal PKI base and is identified by the Transfer CFT instance ID (uconf:cft.instance\_id).  
    Otherwise, use UCONF to set the following Copilot parameters to configure the SSL certificate.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTUTIL uconfset id=copilot.ssl.SslCertFile, value=&lt;ssl pkcs12 certificate for copilot&gt;</p>
                <p>CFTUTIL uconfset id=copilot.ssl.SslCertPassword, value=&lt;ssl pkcs12 certificate password&gt;</p>         </td>
          </tr>
       </tbody>
    </table>

      
    These parameter settings are described in [Install a certificate on the server side](../admin_intro/manage_copilot).  
4.  Specify the authentication method, as the client must provide credentials (user/password) to the REST server. Set the UCONF the copilot.restapi.authentication\_method parameter.  
    Example  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>CFTUTIL uconfset id=copilot.restapi.authentication_method, value=system         </td>
          </tr>
       </tbody>
    </table>

<span id="Authentication_methods"></span>Authentication methods

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

 

## <span id="Connect"></span>Set the Certificate Authority on the client side

For security purposes, you must import the CA that corresponds with the server side certificate.

When using Central Governance

The REST API server automatically uses the SSL business certificate generated during the registration. This certificate is stored in the internal PKI base and is identified by the Transfer CFT instance ID (UCONF cft.instance\_id parameter). You must import the matching Certificate Authority to your web browser certificate store.

When you are not using Central Governance

You must import the Certificate Authority that corresponds with the certificate that you defined previously (Step 3) to your web browser certificate store.

You are now ready to [connect to the user interface](#Connect2). If you encounter errors, please see the [Troubleshooting](#Troubles) section.

## Limit the number of failed login attempts

Transfer CFT provides brute force protection for logging on the Transfer CFT UI, REST API, or Web Services when using either the *system* mode or *xfbadm* mode (UNIX and HP NonStop only) authentication. That is, it limits the number of login failure attempts, where both the user and the password are checked to avoid brute force attacks.

For other authentication methods, such as PassPort and LDAP, no check is made. You must manage that in the Password Policy of those external tools.

You can use the following UCONF parameters to manage this option:

-   `copilot.general.login_failures_fname`: A file that stores data shared between Transfer CFT and Copilot.
-   `copilot.general.max_login_failures`: An integer that sets the maximum number of login failures for a user (default is 3, and 0 disables this option).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In a multi-host environment, an attacker may have up to the <span>copilot.general.max_login_failures * &lt;number of host&gt;</span> tries before the user is locked if the file is not in a directory shared by all hosts.         </td>
      </tr>
   </tbody>
</table>

When the maximum number of login failures is reached, the user account is locked for 30 seconds.

Platform specifics

-   On IBM i systems, there is no action if the password is incorrect as the system offers methods that you can rely on to avoid brute force attacks (the system value is [QMAXSIGN](https://www.ibm.com/support/knowledgecenter/ssw_ibm_i_74/rzarl/rzarlmaxsgn.htm)).
-   On z/OS systems, only the inherent system protection is available (refer to the RACF suboperand [REVOKE](https://www.ibm.com/support/knowledgecenter/SSLTBW_2.3.0/com.ibm.zos.v2r3.icha700/setrpw.htm) for the PASSWORD option).

<span id="Troubles"></span>If you encounter issues when trying to connect to the user interface, please refer to [Troubleshooting the user interface](../Troubleshooting/troubleshoot_ui.htm).

## <span id="Keyboard"></span>Keyboard shortcuts

Keyboard shortcuts provide a way to navigate the user interface from the keyboard. Begin by using **ALT + H** to display the shortcuts. You can then move through the UI, using ALT + the object abbreviation key (e.g. **Alt + T** for transfers) as displayed in the UI.

![](/Images/TransferCFT/new_ui_shortcuts.png)

-   **ALT** + **H**: Displays available shortcuts
-   From the **New** \[Transfer\] page, for example, press Enter to begin a new request.
-   To navigate across the page using keyboard shortcuts, use Tab to move to the next field, or Shift + Tab to go back.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Keyboard shortcuts on Firefox are largely nonfunctional.         </td>
      </tr>
   </tbody>
</table>

## Limitations

### Keyboard shortcut limitation

When tabbing through the UI using keyboard shortcuts, if you tab to a field in a collapsed section that has a drop-down box and you use the space bar, the field's drop-down menu displays even though the section remains collapsed.

![](/Images/TransferCFT/UI_LIMITATION.png)
