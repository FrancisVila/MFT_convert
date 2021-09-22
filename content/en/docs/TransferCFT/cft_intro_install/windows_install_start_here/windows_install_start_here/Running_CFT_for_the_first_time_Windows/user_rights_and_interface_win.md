{
    "title": "Defining user rights ",
    "linkTitle": "Defining user rights ",
    "weight": "240"
}Before you can start Transfer CFT from the Transfer CFT Copilot server, the Copilot server must be started. Additionally you will need rights to log on to this server. The overall process requires that you:

-   [Define rights before starting the Transfer CFT UI server (Copilot)](#define%20rights%20before%20starting%20the%20cft%c2%a0navigator%20server)
-   [Define rights before logging on the Transfer CFT UI server (Copilot)](#define%20rights%20before%20logging%20on%20the%20cft%c2%a0navigator%20server)
-   [Define rights before starting Transfer CFT](#define_rights_before_starting_transfer_cft)
-   [Define a domain user](#define%20domain%20user)
-   [Define folder rights](#define)
-   [Define system user access](#define2)

To start the Transfer CFT Copilot server you must give each Windows user read/write rights for the Transfer CFT installation folder.

You can opt to control the file-access permissions and the batch execution environment by setting the UCONF copilot.misc.createprocessasuser identifier as follows:

-   no: Any user who logs on the Transfer CFT UI server will have their processes identified as the user who started the Transfer CFT Copilot server.

<!-- -->

-   yes: Any user who logs on the Transfer CFT UI server will have their processes identified as their own.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>copilot.misc.createprocessasuser</th>
         <th>
            <p>PassPort AM </p>
            <p>status</p>
</th>
         <th>Rights to define</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p> </p>
            <p>no </p>
         </td>
         <td>Not activated         </td>
         <td>No need to set rights. All Windows users can log on to the  <span>Transfer CFT</span> UI server.         </td>
      </tr>
      <tr>
         <td>
            <p>no </p>
         </td>
         <td>Activated         </td>
         <td>
            <p>If PassPort AM is activated, you must use a PassPort AM user to log on. Check if the AM user has the rights to manage  <span>Transfer CFT</span>.</p>
         </td>
      </tr>
      <tr>
         <td>yes                   </td>
         <td>Not activated         </td>
         <td>
            <p><a name="Define user rights in Windows"></a>The Windows user who is going to log on the  <span>Transfer CFT</span> UI server, must have read and write rights for  <span>Transfer CFT</span> install folder.</p>
            <p>Some user rights must be assigned to the user who launched the  <span>Transfer CFT</span> UI server to permit other Windows users to log on. This is true except if it is the local system account when working in the service mode. The user rights to assign are:</p>
            <ul>
               <li>Adjust memory quotas for a process               </li>
               <li>Impersonate a client after authentication (only on Windows 2008)               </li>
               <li>Replace a process level token               </li>
               <li>Create a token object               </li>
            </ul>
            <p>To define user rights:</p>
<ol>
               <li value="1">In a dos command window, enter <span>lusrmgr.msc</span> to open the system users list. Check available users.               </li>
               <li value="2">In a dos command window, enter <span>secpol.msc</span> to open the Local Security Policy window.               </li>
               <li value="3">Select <span>Security Settings &gt; Local Policies &gt; User Rights Assignment</span>.               </li>
               <li value="4">Double-click the required right.               </li>
               <li value="5">Click <span>Add user or group</span> and define.               </li>
               <li value="6">Close and re-open the Windows session to take into account the modifications.               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>yes          </td>
         <td>Activated         </td>
         <td>
            <p>Some user rights must be assigned to the user who starts the  <span>Transfer CFT</span> UI server to allow other Windows users to log on, unless it is the local system account working in service mode. The user rights are:</p>
            <ul>
               <li>Adjust memory quotas for a process               </li>
               <li>Impersonate a client after authentication (only on Windows 2008)               </li>
               <li>Replace a process level token               </li>
               <li>Create a token object               </li>
            </ul>
<ol>
               <li value="1">In a dos command window, type <span>lusrmgr.msc</span> to open the system users list. Check available users.               </li>
               <li value="2">In a dos command window, type <span>secpol.msc</span> to open the Local Security Policy window.               </li>
               <li value="3">Select <span>Security Settings &gt; Local Policies &gt; User Rights Assignment</span>.               </li>
               <li value="4">Double-click the required right.               </li>
               <li value="5">Click Add user or group and define.               </li>
               <li value="6">Close and re-open the Windows session to take into account the modifications.               </li>
</ol>
            <p>Additionally, the user who wants to log on the  <span>Transfer CFT</span> UI server must exist both in the Windows system and PassPort AM. The Windows system performs the user authentication, and PassPort AM checks the other rights.</p>
            <p><table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">The PassPort user name is case-sensitive.         </td>
      </tr>
</table></p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Define_rights_before_starting_Transfer_CFT"></span>Define folder rights before starting Transfer CFT

The Windows user who is going to start the Transfer CFT server requires read/write rights on the Transfer CFT installation folder and read/write/modify rights on the runtime folder.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you are using either <span>Central Governance</span> or <span>Flow Manager</span>, the user name must exist in PassPort AM and have rights to manage  <span>Transfer CFT</span>. Remember that the PassPort user name is case-sensitive.         </td>
      </tr>
</table>

## <span id="Define domain user"></span>Define domain user

Transfer CFT supports domain user accounts, which allows a service to use Windows service security features.

### File action executed for applicative users

To enable for file actions, check that the USERID user has access to the transfer destination directory. To do this, copy the rights from the user's rights table and create a token object.

### Post-transfer procedure executed for applicative users

To enable for post-transfer procedures, check that the USERID user has rights to execute end-of-transfer procedures. To do this, copy the rights from the user's rights table and create a token object.

## <span id="Define"></span>Define folder rights

To be able to start the Transfer CFT server and the Transfer CFT UI, you must give each user read and write rights for Transfer CFT.

### Service mode login

If you are working in service mode, you must have Log on as a service authority.

1.  In a dos command window, type secpol.msc to open the Local Security Policy window.
2.  Select Security Settings > Local Policies > User Rights Assignment.
3.  Double-click Log on as a service.
4.  Click Add user or group and define.

## <span id="Define2"></span>Define system user access

### System user enabled

If copilot.misc.createprocessasuser=yes in UCONF , or Createprocessasuser=yes in \[MISC\], the user starting the Transfer CFT Copilot server must do the following tasks to allow other users to log on. Additionally, those users must exist in the Windows system users list.

-   Adjust memory quotas for a process
-   Simulate a client after authentication (only on Windows 2008)
-   Replace a process level token

### Procedure

1.  In a dos command window, type lusrmgr.msc to open the system users list. Check available users.
2.  In a dos command window, type secpol.msc to open the Local Security Policy window.
3.  Select Security Settings > Local Policies > User Rights Assignment.
4.  Double-click the required right.
5.  Click Add user or group and define.

PassPort AM is activated

If PassPort AM is active (am.type=PassPort in UCONF), the user must exist both in the Windows system users list and PassPort AM users list. The Windows system user performs the authentication, and PassPort AM performs the other rights checks.

> <table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The PassPort user name is case-sensitive.         </td>
      </tr>
</table>

### System user deactivated with PassPort AM management

If copilot.misc.createprocessasuser=no in UCONF, all system users have the right to log on.

-   PassPort AM is activated
-   If PassPort AM is active (am.type=PassPort in [UCONF](../../../../../admin_intro/uconf/uconf_parameters)), you must be a defined PassPort AM user to log on.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The PassPort user name is case-sensitive.         </td>
      </tr>
</table>

Related topics

[About PassPort AM](../../../../../internal_a_m_start_here/about_passport_am)

[UCONF parameters](../../../../../admin_intro/uconf/uconf_parameters)
