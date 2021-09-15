{
    "title": "Configure systemd services",
    "linkTitle": "Configure systemd services",
    "weight": "210"
}This section describes the steps you must perform to start and stop, or update, Transfer CFT from Central Governance with Linux systemd services defined.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">To perform the authorization procedures described in this page, you may want to refer to the sudoers documentation that corresponds with your Linux operating system.         </td>
      </tr>
</table>

## Start the service using Central Governance or Copilot

Perform the following steps to configure the Transfer CFT systemd service to start via Central Governance or Copilot, where:

-   The Transfer CFT systemd service is called: **cft**
-   The command to start this service is: sudo systemctl start cft

1.  Authorize the Transfer CFT user to start the service without requiring a password. On Ubuntu/Debian, use the visudo command to add a file called cft to /etc/sudoers.d/:
2.  Then add the following line:
3.  Create a script in the $CFTDIRRUNTIME/conf directory, for example called copcftstart, as follows:
4.  Set the UCONF copilot.misc.cftstart parameter to conf/copcftstart.

## Update using Central Governance with systemd services defined

Configure support for the systemd service to apply updates via Central Governance, where:

-   The systemd service created for Transfer CFT is called: cft
-   The systemd service created for Copilot is called: cftcopilot

Authorize the user that operates Transfer CFT to start and stop both services without requiring a password.

On Ubuntu/Debian, use the visudo command to add a file called cft to /etc/sudoers.d/:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>sudo visudo -f /etc/sudoers.d/cft         </td>
      </tr>
   </tbody>
</table>

Add the following lines:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>&lt;USERNAME&gt; ALL=NOPASSWD:/bin/systemctl start cft         </td>
      </tr>
   </tbody>
</table>

Create a script in the $CFTDIRRUNTIME/conf directory for each command as follows:

1.  Define a copcftstart script that starts the Transfer CFT service:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>#!/bin/sh            <p>sudo systemctl start cft</p>            <p>rm $0</p>         </td>
      </tr>
   </tbody>
</table>

1.  Define a copcftstop script that stops the Transfer CFT service:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>uconfset id=copilot.misc.cftstart, value=conf/copcftstart         </td>
      </tr>
   </tbody>
</table>

1.  Define a copcopilotstart script that starts the Copilot service:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>sudo visudo -f /etc/sudoers.d/cft         </td>
      </tr>
   </tbody>
</table>

1.  Define a copcopilotstop script that stops the Copilot service:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&lt;USERNAME&gt; ALL=NOPASSWD:/bin/systemctl start cft</p>
            <p>&lt;USERNAME&gt; ALL=NOPASSWD:/bin/systemctl stop cft</p>
            <p>&lt;USERNAME&gt; ALL=NOPASSWD:/bin/systemctl start cftcopilot</p>
            <p>&lt;USERNAME&gt; ALL=NOPASSWD:/bin/systemctl stop cftcopilot</p>
         </td>
      </tr>
   </tbody>
</table>

Set the following UCONF parameters, which reference the scripts to start and stop both services.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>#!/bin/sh</p>
            <p>sudo systemctl start cft</p>
            <p>rm $0</p>
         </td>
      </tr>
   </tbody>
</table>
