{
    "title": "Using system users ",
    "linkTitle": "Using system users ",
    "weight": "250"
}This section describes two optional Windows-specific tasks that you can perform to enable system user authentication and file system rights, and which are not mutually exclusive.

-   [Enable the file user rights (USERCTRL)](#enable3)
-   [How to enable system users - Windows](#enable)

You can only use the **user authentication for Copilot** when implementing the deprecated Java based Copilot UI or Web Services. This sort of authentication does not apply to the current Transfer CFT UI or to REST API usage.

## <span id="Enable3"></span>Enable the file user rights (USERCTRL)

When implementing file user rights with [USERCTRL](../../../../../c_intro_userinterfaces/command_summary/parameter_intro/userctrl), you must run Transfer CFT as a service or start Transfer CFT with administrator privileges.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top"> When USERCTRL=YES, access to UNC or mapped file drives (as opposed to local files) are performed by the user who started Transfer CFT and not the owner of the transfer.          </td>
      </tr>
</table>

The Windows user who is going to perform transfers must have read and write rights for the files to be transferred.

Some user rights must be assigned to the user who launched the Transfer CFT server to permit other Windows users to perform transfers.

To assign user rights:

-   Adjust memory quotas for a process
-   Impersonate a client after authentication (only on Windows 2008)
-   Replace a process level token
-   Create a token object

To define user rights:

1.  In a dos command window, enter lusrmgr.msc to open the system users list. Check available users.
2.  In a dos command window, enter secpol.msc to open the Local Security Policy window.
3.  Select Security Settings > Local Policies > User Rights Assignment.
4.  Double-click the required right.
5.  Click Add user or group and define.
6.  Close and re-open the Windows session to take into account the modifications.

## How to use system user authentication for the user interfaces

There are two ways to enable the system user authentication:

-   For the current web-based Transfer CFT UI: set `copilot.restapi.authentication_method=system`
-   For the deprecated Transfer CFT UI (Copilot): set `copilot.misc.createprocessasuser=yes`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Note that the <code>copilot.misc.createprocessasuser</code> parameter is  set to <code>Yes </code>for Windows systems by default.          </td>
      </tr>
</table>

When enabling user authentication for Copilot, you must run the Transfer Copilot server as a service. The following information applies except if you are using the local system account when working in service mode.

### Prerequisites

The user rights to assign are:

-   Adjust memory quotas for a process
-   Impersonate a client after authentication (only on Windows 2008)
-   Replace a process level token
-   Create a token object

### Define user rights

1.  In a dos command window, enter lusrmgr.msc to open the system users list. Check available users.
2.  In a dos command window, enter secpol.msc to open the Local Security Policy window.
3.  Select Security Settings > Local Policies > User Rights Assignment.
4.  Double-click the required right.
5.  Click Add user or group and define.
6.  Close and re-open the Windows session to take into account the modifications.

Additionally, the user who wants to log on the Transfer CFT UI server must exist both in the Windows system and Central Governance (or PassPort AM). The Windows system performs the user authentication, and Central Governance (or PassPort AM) checks the other rights.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If using <span>Central Governance</span>, the user name is case-sensitive.         </td>
      </tr>
</table>