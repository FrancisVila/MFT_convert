{
    "title": "Automatic Transfer CFT start on system start up",
    "linkTitle": "Automatic start on operating system start up",
    "weight": "200"
}This section describes automatic Transfer CFT start procedures.
However, the method used to run Transfer CFT when the system starts can vary
according to the operating system. For more information on the various parameters' syntax, refer to your operating system documentation.

Because the time it takes to shut Transfer CFT down depends on the current
workload, an automatic Transfer CFT shut down may cause the system shut down
procedure to be temporarily suspended.

The examples in this section assume the following:

-   Transfer CFT is
    installed in the cft user account
-   Transfer CFT is
    installed as standard in the Axway/Transfer\_CFT directory for this account
-   In a multi-node environment, the Transfer CFT runtime is located in /mnt/axway/cft/runtime
-   The home directory
    for this user is /home/cft
-   Transfer CFT is
    correctly installed, configured, and manually tested before attempting any automatic
    activation procedure

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The following sections refer to using a standard editor, for example, vi.         </td>
      </tr>
   </tbody>
</table>

## Using Systemd (Linux)

Systemd is a system and service manager for Linux operating systems.

### Define the Transfer CFT Copilot service (non multi-node)

Use a standard editor to create the cftcopilot.service file in the /etc/systemd/system directory for a standalone installation as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>[Unit]</p>
            <p>Description=Axway Transfer CFT Copilot</p>
            <p>After=syslog.target network.target</p>
            <p> </p>
            <p>[Service]</p>
            <p>Type=forking</p>
            <p>WorkingDirectory=/home/cft/Axway/Transfer_CFT/runtime</p>
            <p>ExecStart=/bin/sh -c '. ./profile &amp;&amp; copstart'</p>
            <p>ExecStop=/bin/sh -c '. ./profile &amp;&amp; copstop'</p>
            <p>Group=cft</p>
            <p>User=cft</p>
            <p>KillMode=process</p>
            <p> </p>
            <p>[Install]</p>
            <p>WantedBy=multi-user.target</p>         </td>
      </tr>
   </tbody>
</table>

#### Define the Transfer CFT service (non multi-node)

Use a standard editor to create the cft.service file in the /etc/systemd/system directory for a standalone installation as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>[Unit]</p>
            <p>Description=Axway Transfer CFT</p>
            <p>After=syslog.target network.target</p>
            <p> </p>
            <p>[Service]</p>
            <p>Type=forking</p>
            <p>WorkingDirectory=/home/cft/Axway/Transfer_CFT/runtime</p>
            <p>ExecStart=/bin/sh -c '. ./profile &amp;&amp; cft start'</p>
            <p>ExecStop=/bin/sh -c '. ./profile &amp;&amp; cft stop'</p>
            <p>Group=cft</p>
            <p>User=cft</p>
            <p> </p>
            <p>[Install]</p>
            <p>WantedBy=multi-user.target</p>         </td>
      </tr>
   </tbody>
</table>

#### Define the Transfer CFT Copilot service (multi-node)

In a multi-node environment, you only need to define the Transfer CFT Copilot as a service. Copilot automatically starts the nodes. Use a standard editor to create the cftcopilot.service file in the /etc/systemd/system directory as follows:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>[Unit]</p>
            <p>Description=Axway Transfer CFT Copilot</p>
            <p>After=syslog.target network.target</p>
            <p> </p>
            <p>[Service]</p>
            <p>Type=forking</p>
            <p>WorkingDirectory=/mnt/axway/cft/runtime</p>
            <p>ExecStart=/bin/sh -c '. ./profile &amp;&amp; copstart &amp;&amp; cft start'</p>
            <p>ExecStop=/bin/sh -c '. ./profile &amp;&amp; copstop -w'</p>
            <p>Group=cft</p>
            <p>User=cft</p>
            <p>KillMode=process</p>
            <p> </p>
            <p>[Install]</p>
            <p>WantedBy=multi-user.target</p>         </td>
      </tr>
   </tbody>
</table>

Once you have validated that the service starts and stops correctly, you can enable it for automatic starts.

Start a service

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>systemctl start &lt;service_name&gt;         </td>
      </tr>
   </tbody>
</table>

Stop a service

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>systemctl stop &lt;service_name&gt;         </td>
      </tr>
   </tbody>
</table>

Enable a service for automatic start

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>systemctl enable &lt;service_name&gt;         </td>
      </tr>
   </tbody>
</table>

Disable a service

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>systemctl disable &lt;service_name&gt;         </td>
      </tr>
   </tbody>
</table>

### Using the /etc/inittab file

This procedure is typically valid on all UNIX systems.

The following examples assume that the su()
system utility is located in the /bin directory.

The start procedures in this section require you to update key system files. If errors
are made, the system may no longer boot correctly, so the system administration should make these modifications.

You can use the logger() system command to store error messages
displayed during an automatic start. For this to operate correctly,
the syslogd() system daemon must be running on your system. The
system administrator can identify the
specific Transfer CFT messages in the system log files at the:

-   Error level and the
    local0 facility for error messages
-   Information level
    and the local0 facility for a correct start

Define the Transfer CFT service

Use a standard editor to add the following line
at the end of the /etc/inittab file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cft:2:once:/bin/su - cft -c ’. Axway/Transfer_CFT/runtime//profile; cft start –batch’         </td>
      </tr>
   </tbody>
</table>

Define the Transfer CFT Copilot service

Use a standard editor to add the following line to the end of the /etc/inittab file:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>cftcopilot:2:once:/bin/su - cft -c ’. Axway/Transfer_CFT/runtime//profile; copstart’         </td>
      </tr>
   </tbody>
</table>

### Adding a file to /etc/rc2.d

You can only use this method on systems with a /etc/rc2.d
directory (SOLARIS for example).

The following examples assume that the su()
system utility is located in the /bin directory.

The start procedures in this section require you to update key system files. If errors
are made, the system may no longer boot correctly, so the system administration should make these modifications.

You can use the logger() system command to store error messages
displayed during an automatic start. For this to operate correctly,
the syslogd() system daemon must be running on your system. The
system administrator can identify the
specific Transfer CFT messages in the system log files at the:

-   Error level and the
    local0 facility for error messages
-   Information level
    and the local0 facility for a correct start

Define the Transfer CFT service

Use a standard editor, *vi* for example, to create a new file called
/etc/rc2.d/S99cft.  

Add the appropriate operating system start shell script to this
file. The following shell script provides a basic example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>#!bin/sh</p>
            <p># Starting Transfer CFT</p>
            <p> </p>
            <p>if [ -f /home/cft/Axway/Transfer_CFT/runtime/profile]</p>
            <p>then</p>
            <p>/bin/su - mycft -c ’. Axway/Transfer_CFT/runtime/profile; cft start –batch’</p>
            <p>fi</p>         </td>
      </tr>
   </tbody>
</table>

Define the Transfer CFT Copilot service

Use a standard editor, vi for example, to create a new file called /etc/rc2.d/S99cftcopilot.

Add the appropriate operating system start shell script to this file. The following shell script provides a basic example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>#!bin/sh</p>
            <p># Starting Transfer CFT Copilot</p>
            <p>if [ -f /home/cft/Axway/Transfer_CFT/runtime/profile]</p>
            <p>then</p>
            <p>/bin/su - mycft -c ’. Axway/Transfer_CFT/runtime/profile; copstart’</p>
            <p>fi</p>         </td>
      </tr>
   </tbody>
</table>
