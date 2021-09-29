{
    "title": "Start, stop, and administration scripts",
    "linkTitle": "Start, stop, and administration scripts",
    "weight": "210"
}## Server command overview

This section refers only to non multi-node architecture.

You can use Central Governance to stop, start, check status, and restart a Transfer CFT, or alternatively use the administration commands and scripts provided in this section to manage the application.

When opening a new session to manage your Transfer CFT, you must first set the environmental parameters. See [Set the Transfer CFT profile](#set).

-   [Start Transfer CFT server](#start)
    -   Standard start
    -   Force a start after an abnormal stop
    -   Start and suspend interactive mode
-   [Stop Transfer CFT server](#stop__server)
    -   Standard shutdown
    -   Quick stop
    -   Forced shutdown
-   [Restart Transfer CFT](#restart_server)
-   [Check Transfer CFT status](#check)
-   [Purge on Transfer CFT start](#purge%20on%20transfer%20cft%c2%a0start)

### OS specific tasks and menus

-   Windows
    -   [Service mode](#service)
    -   [Windows menus](#windows)
-   z/OS
    -   [Start/stop](../../c_intro_userinterfaces/command_summary/parameter_intro/st)
    -   [Check status](#perform)

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The commands listed in this section apply generally to all supported platforms for this version, except for <span>Transfer CFT</span> z/OS. For more information, please refer to the OS-specific <span>Installation Guide</span>.</td>
</tr>
</tbody>
</table>

### Autocomplete command

UNIX only

To simplify the use of cft commands, you can use the autocomplete feature when working in interactive mode. See [Autocomplete](../../c_intro_userinterfaces/about_cftutil/autocomplete).

## <span id="Start"></span>Start the Transfer CFT server

### <span id="Set"></span>Set the Transfer CFT profile

From your runtime directory prompt type:

**UNIX**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td> . ./profile</td>
</tr>
</tbody>
</table>

**Windows**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>profile.bat</p></td>
</tr>
</tbody>
</table>

**IBM i**

To change the user profile:

1.  In the system Objects menu, type 8 and press Enter to validate.
2.  Modify the user profile to take into account the selections that you made in previous customization steps.
3.  Indicate the name of the job description that you created for the

Transfer CFT working environment.

Change profile (CHGPRF)

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>Type choices, press Enter.</p>
<p> </p>
<p>Assistance level . . . . . . . . *SYSVAL *SAME, *SYSVAL, *BASIC...</p>
<p>Current library . . . . . . . . *CRTDFT Name, *SAME, *CRTDFT</p>
<p>Initial program to call . . . . CFGINLPGM Name, *SAME, *NONE</p>
<p>Library . . . . . . . . . . . DOICONFIG Name, *LIBL, *CURLIB</p>
<p>Initial menu . . . . . . . . . . MAIN Name, *SAME, *SIGNOFF</p>
<p>Library . . . . . . . . . . . QSYS Name, *LIBL, *CURLIB</p>
<p>Text 'description' . . . . . . . &gt; '&lt;TRANSFER CFT USER PROFILE&gt;'</p>
<p> </p>
<p>Additional Parameters</p>
<p> </p>
<p>Job description . . . . . . . . &gt; CFTJOBD Name, *SAME</p>
<p>Library . . . . . . . . . . . &gt; CFTPROD Name, *LIBL, *CURLIB</p>
<p> </p>
<p>Additional Parameters</p>
<p> </p>
<p>Job description . . . . . . . . &gt; CFTJOBD Name, *SAME</p>
<p>Library . . . . . . . . . . . &gt; CFTPROD Name, *LIBL, *CURLIB</p></td>
</tr>
</tbody>
</table>

### Start Transfer CFT

#### Standard start

Use the following command to start Transfer CFTafter installation or stopping the server.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><span> cft start</span></td>
</tr>
</tbody>
</table>

In Windows only you can also use the Start menu or automatically start the server in Service Mode. See [Windows tasks](#windows2).

#### Start and suspend interactive mode

This mode launches the server, but freezes the session where you executed this start command. Closing this session automatically stops the Transfer CFT, and if the server is stopped the initiating session is unfrozen.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cft start-and-wait</p></td>
</tr>
</tbody>
</table>

#### Force a start after an abnormal stop

If Transfer CFT was stopped abnormally, you can force a start using the following command. Notice though that this kills any Transfer CFT processes that were not previously stopped.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cft force-start</p></td>
</tr>
</tbody>
</table>

## <span id="Stop__server"></span>Stop the Transfer CFT server

This program shuts down
Transfer CFT, using either an immediate or delayed shutdown.

#### Standard shutdown

Transfer CFT completes all the transfers
in process and shuts down. No new transfer is initialized.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL shut fast=no</p></td>
</tr>
</tbody>
</table>

#### Quick stop

This method of stopping interrupts transfers in progress and changes
them to D state (available). No pending transfers are activated.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>cft stop</p></td>
</tr>
</tbody>
</table>

-or-

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL shut fast=yes</p></td>
</tr>
</tbody>
</table>

#### Forced  shutdown

Immediate Transfer CFT shutdown occurs,
but without updating the transfer states. No pending transfers are activated.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL shut fast=kill</p></td>
</tr>
</tbody>
</table>

## <span id="Restart_server"></span>Restart the server

To restart the Transfer CFT server use the following command. The behavior for in progress transfers depends on the setting defined for the FAST parameter (default=NO).

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL shut restart=yes</td>
</tr>
</tbody>
</table>

## <span id="Check"></span>Check the system

#### Check the Transfer CFT status

To check the state of the Transfer CFT sever, enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cft status</td>
</tr>
</tbody>
</table>

## <span id="Purge on Transfer CFT start"></span>Purge on Transfer CFT start

To configure the Transfer CFT start-up PURGE option, set the uconf values for:

-   cft.purge.enable\_on\_start: Defines if purge should run when starting Transfer CFT
-   cft.purge.background\_on\_start: Defines if purging on start-up occurs in the background
-   cft.purge.quantity: Defines the number of transfers to delete in a step (only applicable for background purging)

## <span id="Windows2"></span>Windows tasks

#### <span id="Windows"></span>Windows menus

From the desktop Start menu, select All Programs &gt; Axway Software &gt;Axway &gt; &lt;product> &gt; Stop &lt;product>

#### <span id="Service"></span>Service mode

During installation you can elect to run most Axway products as a Windows service, which causes the server to start and stop with the computer. When running a product as a Windows service, the only visual clues of the server status outside of the user interface are the application log files and the Windows computer management window.

If you installed the products in Windows service mode, you can start and stop most products with Windows already running as follows:

1.  From the desktop, select Start > Settings > Control Panel > Administrative Tools > Services.
2.  Scroll down the Services list and right-click the product.
3.  From the menu, select Start.

#### <span id="Multi-node_specific"></span>Multi-node specific commands

To view all commands for multi-node architecture, go to the topic [Multi-node commands](../../about_multinode/multi_node_commands).

## z/OS tasks

#### <span id="Start/st"></span>Start

Start the CFTMAIN JCL in the target.INSTALL library.

#### Stop

The following are commands that you can use to stop Transfer CFT outside of a customized JCL (such as the delivered sample JCL, **CFTSTOP**, in the target.INSTALL library).

**Normal stop**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;Jobname&gt;,SHUT FAST=NO <em>or</em> SHUT FAST=YES</td>
</tr>
</tbody>
</table>

**Quick stop**

Enter the operator command:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/P &lt;<span>Transfer CFT</span> Jobname&gt;</td>
</tr>
</tbody>
</table>

\- or -

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=YES</td>
</tr>
</tbody>
</table>

**Force** Transfer CFT **shut down**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=KILL</td>
</tr>
</tbody>
</table>

#### Restart

The following command restarts Transfer CFT outside of a customized JCL. Enter the operator command:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/F Jobname,SHUT RESTART=YES</td>
</tr>
</tbody>
</table>

#### <span id="Perform"></span>Perform a ping

Use the CFTPING in the target.INSTALL library to ping your Transfer CFT.

#### Check the Transfer CFT Copilot server status

You can use COPSTATU, for example, as the JCL statement to display the Copilot server status in the current LPAR.

 
