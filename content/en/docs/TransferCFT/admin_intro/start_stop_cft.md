{
    "title": "Start, stop, and administration scripts",
    "linkTitle": "Start, stop, and administration scripts",
    "weight": "210"
}# Manage the <span>Transfer CFT</span> server



## Server command overview



This section refers only to non multi-node architecture.



You can use Central Governance to stop, start, check status, and restart a Transfer CFT, or alternatively use the administration commands and scripts provided in this section to manage the application.



When opening a new session to manage your <span>Transfer CFT</span>, you must first set the environmental parameters. See <a href="#set">Set the Transfer CFT profile</a>.



-   [Start <span>Transfer CFT</span> server](#Start)

    -   Standard start

    -   Force a start after an abnormal stop

    -   Start and suspend interactive mode

-   [Stop <span>Transfer CFT</span> server](#Stop__server)

    -   Standard shutdown

    -   Quick stop

    -   Forced shutdown

-   [Restart <span>Transfer CFT</span>](#Restart_server)

-   [Check Transfer CFT status](#Check)

-   [Purge on Transfer CFT start](#Purge%20on%20Transfer%20CFT%C2%A0start)



### OS specific tasks and menus



-   Windows

    -   [Service mode](#Service)

    -   [Windows menus](#Windows)

-   z/OS

    -   [Start/stop](#Start/st)

    -   [Check status](#Perform)



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The commands listed in this section apply generally to all supported platforms for this version, except for <span>Transfer CFT</span> z/OS. For more information, please refer to the OS-specific <span>Installation Guide</span>.</td>
</tr>
</tbody>
</table>



### Autocomplete command



UNIX only



To simplify the use of <span>cft </span>commands, you can use the autocomplete feature when working in interactive mode. See [Autocomplete](../CFTUTIL/Autocomplete.htm).



## <span id="Start"></span>Start the <span>Transfer CFT</span> server



### <span id="Set"></span>Set the <span>Transfer CFT</span> profile



From your runtime directory prompt type:



**UNIX**



<table data-cellspacing="0">
<tbody>
<tr>
<td> . ./profile</td>
</tr>
</tbody>
</table>



**Windows**



<table data-cellspacing="0">
<tbody>
<tr>
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
<tr>
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



### Start <span>Transfer CFT</span>



#### Standard start



Use the following command to start <span>Transfer CFT</span>after installation or stopping the server.



<table data-cellspacing="0">
<tbody>
<tr>
<td><span> cft start</span></td>
</tr>
</tbody>
</table>



In Windows only you can also use the Start menu or automatically start the server in Service Mode. See <a href="#windows2">Windows tasks</a>.



#### Start and suspend interactive mode



This mode launches the server, but freezes the session where you executed this start command. Closing this session automatically stops the <span>Transfer CFT</span>, and if the server is stopped the initiating session is unfrozen.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>cft start-and-wait</p></td>
</tr>
</tbody>
</table>



#### Force a start after an abnormal stop



If <span>Transfer CFT</span> was stopped abnormally, you can force a start using the following command. Notice though that this kills any <span>Transfer CFT</span> processes that were not previously stopped.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>cft force-start</p></td>
</tr>
</tbody>
</table>



## <span id="Stop__server"></span>Stop the <span>Transfer CFT</span> server



This program shuts down

Transfer CFT, using either an immediate or delayed shutdown.



#### Standard shutdown



<span>Transfer CFT</span> completes all the transfers

in process and shuts down. No new transfer is initialized.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUTIL shut fast=no</p></td>
</tr>
</tbody>
</table>



#### Quick stop



This method of stopping interrupts transfers in progress and changes

them to D state (available). No pending transfers are activated.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>cft stop</p></td>
</tr>
</tbody>
</table>



-or-



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUTIL shut fast=yes</p></td>
</tr>
</tbody>
</table>



#### Forced  shutdown



Immediate <span>Transfer CFT</span> shutdown occurs,

but without updating the transfer states. No pending transfers are activated.



<table data-cellspacing="0">
<tbody>
<tr>
<td><p>CFTUTIL shut fast=kill</p></td>
</tr>
</tbody>
</table>



## <span id="Restart_server"></span>Restart the server



To restart the <span>Transfer CFT</span> server use the following command. The behavior for in progress transfers depends on the setting defined for the FAST parameter (default=NO).



<table data-cellspacing="0">
<tbody>
<tr>
<td>CFTUTIL shut restart=yes</td>
</tr>
</tbody>
</table>



## <span id="Check"></span>Check the system



#### Check the <span>Transfer CFT</span> status



To check the state of the <span>Transfer CFT</span> sever, enter:



<table data-cellspacing="0">
<tbody>
<tr>
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



From the desktop <span>Start</span> menu, select<span> All Programs &gt; Axway Software &gt;Axway &gt; &lt;product&gt; &gt; Stop &lt;product&gt;</span>



#### <span id="Service"></span>Service mode



During installation you can elect to run most <span>Axway</span> products as a Windows service, which causes the server to start and stop with the computer. When running a product as a Windows service, the only visual clues of the server status outside of the user interface are the application log files and the Windows computer management window.



If you installed the products in Windows service mode, you can start and stop most products with Windows already running as follows:



1.  From the desktop, select <span>Start &gt; Settings &gt; Control Panel &gt; Administrative Tools &gt; Services</span>.

2.  Scroll down the Services list and right-click the product.

3.  From the menu, select <span>Start</span>.



#### <span id="Multi-node_specific"></span>Multi-node specific commands



To view all commands for multi-node architecture, go to the topic [Multi-node commands](../multi_node/multi_node_commands.htm).



## z/OS tasks



#### <span id="Start/st"></span>Start



Start the CFTMAIN JCL in the target.INSTALL library.



#### Stop



The following are commands that you can use to stop Transfer CFT outside of a customized JCL (such as the delivered sample JCL, **CFTSTOP**, in the target.INSTALL library).



**Normal stop**



<table data-cellspacing="0">
<tbody>
<tr>
<td>/F &lt;Jobname&gt;,SHUT FAST=NO <em>or</em> SHUT FAST=YES</td>
</tr>
</tbody>
</table>



**Quick stop**



Enter the operator command:



<table data-cellspacing="0">
<tbody>
<tr>
<td>/P &lt;<span>Transfer CFT</span> Jobname&gt;</td>
</tr>
</tbody>
</table>



\- or -



<table data-cellspacing="0">
<tbody>
<tr>
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=YES</td>
</tr>
</tbody>
</table>



**Force** <span>Transfer CFT</span> **shut down**



<table data-cellspacing="0">
<tbody>
<tr>
<td>/F &lt;<span>Transfer CFT</span> Jobname&gt;,SHUT FAST=KILL</td>
</tr>
</tbody>
</table>



#### Restart



The following command restarts Transfer CFT outside of a customized JCL. Enter the operator command:



<table data-cellspacing="0">
<tbody>
<tr>
<td>/F Jobname,SHUT RESTART=YES</td>
</tr>
</tbody>
</table>



#### <span id="Perform"></span>Perform a ping



Use the CFTPING in the target.INSTALL library to ping your <span>Transfer CFT</span>.



#### Check the Transfer CFT Copilot server status



You can use COPSTATU, for example, as the JCL statement to display the Copilot server status in the current LPAR.



 

