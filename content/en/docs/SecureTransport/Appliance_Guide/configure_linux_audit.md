{
    "title": "Configure Linux audit framework",
    "linkTitle": "Configure linux audit framework",
    "weight": "100"
}Use the following procedure to configure the Linux audit framework. The Linux audit framework is disabled by default.

1.  Connect to the console. See <a href="../appliancestartup_reboot_shutdown#_Ref331672216" class="MCXref xref">Reboot or shut down the appliance</a> for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **H**, Hardening & Security.
3.  On the Hardening & Security menu, type **L**, Linux Audit Framework.
4.  On the Hardening & Security menu, type **L**, Linux Audit Framework Configuration.
5.  The Linux Audit Framework Configuration page displays. On this screen, you use **Alt+&lt;key>** combinations to choose highlighted options. For example, **Alt+I** takes you to the Log File path where you can type in the file path.
6.  Use the Tab key to cycle through the fields on the page. Specify values for each of the following fields as necessary:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>Dispatcher</p>         </td>
             <td><p>The audit dispatcher can be used to send event notifications in addition to - or instead of - writing them to the audit log. In the Dispatcher window, type <strong>I</strong> to manually type in the file path and dispatcher program name, or type <strong>L</strong> to select the program on the computer.</p>         </td>
          </tr>
          <tr>
             <td><p>Disk space</p>         </td>
             <td><p>Select and assign the disk space rules on the window that opens. Options include rules on what to do when disk space is starting to run low, when admin space is running low, and when the disk is full or there is an error.</p>         </td>
          </tr>
          <tr>
             <td><p>Rules for 'auditctl'</p>         </td>
             <td><p>Set the audit framework rules. For more information, see <a href="#Configur" class="MCXref xref">Configure audit framework rules</a>.</p>         </td>
          </tr>
          <tr>
             <td><p>Log File</p>         </td>
             <td><p>Set the file path for the audit log file.</p>         </td>
          </tr>
          <tr>
             <td><p>Select File</p>         </td>
             <td><p>Opens a window from which the audit log file can be chosen.</p>         </td>
          </tr>
          <tr>
             <td><p>Format</p>         </td>
             <td><p>Set the audit log file format to one of these two options:</p>
    <ul>
    <li><strong>RAW</strong> - Information is stored as it is sent.</li>
    <li><strong>NOLOG</strong> - Information is not written to a file.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>Flush</p>         </td>
             <td><p>Set whether the audit log is written to disk, how, and how often. The options are:</p>
    <ul>
    <li><strong>NONE</strong> - The audit data will not be written to a file.</li>
    <li><strong>INCREMENTAL</strong> - The audit data will be written to the file in the increments specified.</li>
    <li><strong>DATA</strong> - Keeps the data part of the disk file in sync at all times.</li>
    <li><strong>SYNC</strong> - Includes both data and metadata.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>Frequency (Number of Records)</p>         </td>
             <td><p>Sets the number of records before the data is written to the audit log file.</p>         </td>
          </tr>
          <tr>
             <td><p>Max File Size</p>         </td>
             <td><p>Set the maximum file size, in megabytes, of the audit log.</p>         </td>
          </tr>
          <tr>
             <td><p>Maximum File Size Action</p>         </td>
             <td><p>Set the action to be performed when the audit log file size reaches the maximum.  Use the up and down arrow keys to make your selection.  The options are:</p>
    <ul>
    <li><strong>IGNORE</strong> - Ignore the maximum file size set and continue recording in the audit log file.</li>
    <li><strong>SYSLOG</strong> - Write to the system log.</li>
    <li><strong>SUSPEND</strong> - Stop recording in the audit log file.</li>
    <li><strong>ROTATE</strong> - Rotate between the different audit log files.</li>
    <li><strong>KEEP_LOGS</strong> - Save the audit log file and start another.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>Number of Log Files</p>         </td>
             <td><p>Set the number of log files to keep.</p>         </td>
          </tr>
          <tr>
             <td><p>Computer Name Format</p>         </td>
             <td><p>Set the format of the computer name to be used. Use the up and down arrow keys to make your selection. The options are:</p>
    <ul>
    <li><strong>None</strong> - No special computer name format.</li>
    <li><strong>Hostname</strong> - The hostname will be used.</li>
    <li><strong>FQD</strong> - The fully qualified domain name will be used.</li>
    <li><strong>User</strong> - The specified user-defined name will be used. Type <strong>E</strong> to specify the user-defined name.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>User Defined Name</p>         </td>
             <td><p>This field appears only when "User" is chosen for the Computer Name Format. Enter the user-defined name that will be used as the computer name format.</p>         </td>
          </tr>
       </tbody>
    </table>
7.  Once each section of the Linux Audit Framework Configuration is set, type **Alt+F**, Finish, to complete the configuration.

For more information on configuration options, press **Alt+H** to open online help.

<span id="Configur"></span>

## Configure audit framework rules

By configuring the Linux audit framework rules, you can specify which system components are audited:

-   System calls
-   File and directory watches
-   Basic system parameters

Use the following procedure to access the Configuration of Linux Audit Framework (LAF) screen:

1.  Connect to the console. See <a href="../appliancestartup_reboot_shutdown#_Ref331672216" class="MCXref xref">Reboot or shut down the appliance</a> for more information.  
    The Appliance Console Menu is displayed.
2.  On the Appliance Console Menu, type **H**, Hardening & Security.
3.  On the Hardening & Security menu, type **L**, Linux Audit Framework.
4.  On the Hardening & Security menu, type **L**, Linux Audit Framework Configuration.
5.  On the Linux Audit Framework Configuration page, type **T** to access the rules screen.
6.  Use the Tab key to cycle through the fields on the page and the up and down arrows to view the information in the `audit.rules` box. Specify values for each of the following fields as necessary:  
    <table>
       <thead>
          <tr>
    <th class="HeadE-Column1-Header1">Field         </th>
    <th class="HeadD-Column1-Header1">Description         </th>
          </tr>
       </thead>
       <tbody>
          <tr>
             <td><p>Set Enabled Flag</p>         </td>
             <td><p>Set the enabled flag to one of these options:</p>
    <ul>
    <li><strong>Auditing enabled</strong> - Turns auditing on.</li>
    <li><strong>Auditing disabled</strong> - Turns auditing off.</li>
    <li><strong>Rules are locked (until next boot)</strong> - Locks the auditing rules until the next time the system is booted.</li>
    </ul>         </td>
          </tr>
          <tr>
             <td><p>audit.rules</p>         </td>
             <td><p>Edit the rules for the audit subsystem.</p>         </td>
          </tr>
          <tr>
             <td><p>Check Syntax</p>         </td>
             <td><p>Check the syntax of the audit rules for errors.</p>         </td>
          </tr>
          <tr>
             <td><p>Restore 'audit.rules'</p>         </td>
             <td><p>Reset the audit rules to the state before changes were made.</p>         </td>
          </tr>
          <tr>
             <td><p>Restore and Reset</p>         </td>
             <td><p>Restore and reset all settings to the state before changes were made.</p>         </td>
          </tr>
          <tr>
             <td><p>Load</p>         </td>
             <td><p>Load the modified audit rules.</p>         </td>
          </tr>
       </tbody>
    </table>

### Audit system parameters

The following audit system parameters can be used:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-D</p>         </td>
         <td><p>Deletes any preexisting rules to avoid problems with new rules.</p>         </td>
      </tr>
      <tr>
         <td><p>-b</p>         </td>
         <td><p>Sets the number of outstanding audit buffers. If no more buffers are available, the failure flag is checked for action.</p>         </td>
      </tr>
      <tr>
         <td><p>-f</p>         </td>
         <td><p>Sets the failure flag, which controls the reaction to critical errors. Value options:</p>
<ul>
<li><strong>0</strong> - Silent</li>
<li><strong>1</strong> - Print a failure message (printk)</li>
<li><strong>2</strong> - Shutdown the system (panic). There is a risk of data loss and corruption with this option.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-e</p>         </td>
         <td><p>Sets the enable flag, which enables or temporarily disables the audit. Value options:</p>
<ul>
<li><strong>0</strong> - Disables the audit.</li>
<li><strong>1</strong> - Enables the audit and the audit contexts for system calls.</li>
<li><strong>2</strong> - Enables the audit and audit contexts and locks down the configuration.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>-w</p>         </td>
         <td><p>Sets a file system watch. Example: <code>-w /etc/audit/audit.rules -p rxwa</code></p>         </td>
      </tr>
      <tr>
         <td><p>-p</p>         </td>
         <td><p>Sets permission filtering. In the example <code>-w /etc/audit/audit.rules -p rxwa</code>, permission filtering is turned on for read, write, execute, and attribute change.</p>         </td>
      </tr>
      <tr>
         <td><p>-k</p>         </td>
         <td><p>Attaches a text string to a recorded event. Example: <code>-w /var/log/audit/ -k LOG_audit</code>. This helps with searches using the ausearch log analyzer.</p>         </td>
      </tr>
   </tbody>
</table>

The above information was adapted from <https://www.suse.com/>.
