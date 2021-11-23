{
    "title": "Managing the Mailbox (command line) ",
    "linkTitle": "Managing the Mailbox",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Managing Transfers

[About Mailbox management commands](#About)

[Initializing the Mailbox](#Initializing_Mailbox)

[Optimizing the Mailbox](#Optimizing_Mailbox)

[Managing the Mailbox](#Managing_Mailbox_pelmon)

[Backing up the Mailbox (mirroring)](#Mailbox_mirroring)

<span id="About"></span>

## About Mailbox management commands

This topic contains information to help you manage the Mailbox in your daily operations. It includes descriptions of the processes and commands that are useful to operate and protect your Mailbox.

Gateway Mailbox management commands are designed for use by experienced users. While these commands are powerful tools, they can also be quite complex.

<span id="Initializing_Mailbox"></span>

## Initializing the Mailbox

You do not have to initialize this version of Gateway. The Installer executes the `gateinit` command for you. The command still exists in this version of Gateway for reasons of compatibility. This command, among other things, creates the Mailbox file. Subsequently, when you start Gateway, the software either automatically creates the Mailbox, or re-opens it, as required.

Alternatively, to initialize the Mailbox you can use the `pelmon init_base` command.

<span id="Optimizing_Mailbox"></span>

## Optimizing the Mailbox

Gateway includes the *Key File Management Copy* (`kfmcp`) tool. This tool enables you to [maintain and optimize the Gateway Mailbox files](../maintaining_mailbox) (`xfer.dat` and `xferb.dat`). They are located in` <Gateway installation directory>/run_time/data`. These files contain status information for current file Transfer Requests.

<span id="Managing_Mailbox_pelmon"></span>

## Managing the Mailbox

After you initialize the Mailbox for the first time and then optimize the Mailbox, you can use the `pelmon` command to perform Mailbox management operations:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Command         </th>
<th class="HeadD-Column1-Header1">Operation         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><code>pelmon init_base</code>         </td>
         <td>Initialize Gateway and the Mailbox         </td>
      </tr>
      <tr>
         <td><code>pelmon restart</code>         </td>
         <td>Restart Gateway and activate links to the Mailbox         </td>
      </tr>
      <tr>
         <td><code>pelmon check_base</code>         </td>
         <td>Check the integrity of Gateway and the Mailbox         </td>
      </tr>
      <tr>
         <td><code>pelmon recover_base</code>         </td>
         <td>Recover a corrupted Mailbox         </td>
      </tr>
      <tr>
         <td><code>pelmon change_pass_phrase</code>         </td>
         <td>Change the Mailbox database ciphering key         </td>
      </tr>
      <tr>
         <td><code>pelmon rebuild_vfd</code>         </td>
         <td>Repair the Virtual File Directory         </td>
      </tr>
      <tr>
         <td><code>pelmon reset</code>         </td>
         <td>Reset the status prompted by the <code>gatestatus</code> command to the default value         </td>
      </tr>
   </tbody>
</table>

### Deprecated pelmon subcommands

Do not use the following `pelmon` subcommands that were used in previous versions of Gateway. Only use the replacement commands:

-   `pelmon start`  
    Replaced with the `gatestart` command.
-   `pelmon stop`  
    Replaced with the `gatestop` command.
-   `pelmon status`  
    Replaced with the `gatestatus` command.

<span id="pelmon_init_base"></span>

### pelmon init\_base

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon init_base</strong> [-force (-f)] [-cipher_passphrase_dkfile (-cpdkf)] [-cipher_passphrase_encfile (-cpencf)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to initialize Gateway, and activate links to the Mailbox. You can use this command to restart Gateway after a system crash that caused integrity problems on both Mailboxes.</p>
<p>If the Mailbox file does not already exist, this command creates it.</p>
<p>If the Mailbox file already exists, this command truncates the file, deleting all transfers from the Mailbox and resetting the transfer identifier to 1.</p>
<p>If the Gateway <strong><a href="../../../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></strong> is activated, this command initializes both Mailboxes (master and mirror).</p>         </td>
      </tr>
      <tr>
         <td><p>Alternative command</p>         </td>
         <td><p><span class="code">gateinit</span></p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-force (-f)</span>: Use this parameter to force Mailbox initialization when there is no integrity problem on the Mailbox.</p>
<p>Additionally, this parameter removes all VFD Items without modifying the directory organization.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cipher_passphrase_dkfile (-cpdkf)</span>: Enter a path to a derived key used to encrypt the protection password. Maximum: 256 alphanumeric characters.</p>
<p>Use this parameter if AES encoding protects Gateway files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.</p>
<p>If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-cipher_passphrase_encfile (-cpencf)</span>: Enter a path to an encrypted password file.
Use this parameter if encoding protects the Mailbox and its associated object database files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.
If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Before initializing the Mailbox, stop Gateway.</p>
<p>Enter the command:</p>
<p><span class="code" style="font-weight: bold;">pelmon init_base</span></p>
<p>Gateway returns:</p>
<p>Testing Axway Gateway status: stopped</p>
<p>Checking software license key: xxxx xxxx xxxx xxxx xxxx</p>
<p>Expiration date :none</p>
<p>Max network connections :unlimited</p>
<p>Max site :unlimited</p>
<p>Protocol options :PSIT FTP</p>
<p>Misc product options :'Secured Mailbox'</p>
<p>Checking monitor option versus license:</p>
<p>Mirror option enable</p>
<p>Checking monitor context:</p>
<p>Monitor stopped normally</p>
<p>Initializing master mailbox: done</p>
<p>Initializing mirror mailbox: done</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_restart"></span>

### pelmon restart

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon restart</strong> [-trace_level (-l)] [-cipher_passphrase_dkfile (-cpdkf)] [-cipher_passphrase_encfile (-cpencf)] [-wait]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to restart Gateway, and by extension, to restart the tracking functions of the Mailbox. Use this command on Gateway when it is running.</p>
<p>This command does not clean the current contents of the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-trace_level (-l)</span>: Starts the Mailbox trace in binary format set to the specified level. Enter one of the following values:</p>
<ul>
<li>0 - not activated<br />
Use this parameter value for debugging purposes only, not for production</li>
<li>1</li>
<li>2</li>
<li>3</li>
<li>4 maximum trace information</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cipher_passphrase_dkfile (-cpdkf)</span>: Enter a path to a derived key used to encrypt the protection password.<br />
Maximum: 256 alphanumeric characters.</p>
<p>Use this parameter if encoding protects the Mailbox and its associated object database files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.</p>
<p>If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-cipher_passphrase_encfile (-cpencf)</span>: Enter a path to an encrypted password file.
Use this parameter if encoding protects the Mailbox and its associated object database files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.
If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.         </td>
      </tr>
      <tr>
         <td><p><span class="code">-wait</span>: Use this parameter if you want to check that Gateway starts up correctly.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-no_xsr</span>: Use this parameter to start Gateway without Secure Relay.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-auto_check (-auto)</span>: Y (Yes) or N (No) Enter Yes to enable automatic checking functions on restart. <span class="code">auto_check</span> corrects certain file content problems, for example it confirms and corrects VFD file structures.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_check_base"></span>

### pelmon check\_base

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon check_base</strong> [-recover_auto (-ra)] [-cipher_passphrase_dkfile (-cpdkf)] [-cipher_passphrase_encfile (-cpencf)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to check Mailbox integrity. If the Gateway <span style="font-weight: bold;"><a href="../../../../configuration_start_here/config_gateway_paras#Mirror_option">Mirror option</a></span> is activated, the command checks both Mailboxes. This command is mandatory if:</p>
<ul>
<li>Gateway stopped abnormally</li>
<li>a problem occurred when you started Gateway</li>
</ul>
<p>Stop Gateway before you check the Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-recover_auto (-ra)</span>: automatically recovers a corrupted file (master or mirror Mailbox), without using any other command.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cipher_passphrase_dkfile (-cpdkf)</span>: Enter a path to a derived key used to encrypt the protection password.<br />
Maximum: 256 alphanumeric characters.</p>
<p>Use this parameter if Gateway files are encrypted. If you specify a path, Gateway automatically tries to get the password phrase required to open the Mailbox file from the specified user file.</p>
<p>If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-cipher_passphrase_encfile (-cpencf)</span>: Enter a path to an encrypted password file.
Use this parameter if encoding protects the Mailbox and its associated object database files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.
If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p><span class="code">pelmon check_base  -recover_auto</span></p>
<p>Gateway returns:</p>
<p>Testing Axway Gateway status: stopped</p>
<p>Checking software license key : xxxx xxxx xxxx xxxx xxxx</p>
<p>Expiration date :none</p>
<p>Max network connections:unlimited</p>
<p>Max site :unlimited</p>
<p>Protocol options :PEL FTP</p>
<p>Misc product options :'Secured Mailbox'</p>
<p>Checking monitor option versus license:</p>
<p>Mirror option enable</p>
<p>Checking monitor context:</p>
<p>Monitor stopped normally</p>
<p>Last checking ended normally</p>
<p>Checking base integrity:</p>
<p>Master mailbox : corrupted</p>
<p>Mirror mailbox : OK</p>
<p>Recovering of master mailbox: Done</p>
<p>Automatic recovering done.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_recover_base"></span>

### pelmon recover\_base

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon recover_base</strong> [-force (-f)] [-how (-h)] [-cipher_passphrase_dkfile (-cpdkf)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to recover a corrupted Mailbox.</p>
<p>Stop Gateway before you execute this command.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-force (-f)</span>: Forces the recovery of a Mailbox that is not detected as corrupted.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-how (-h)</span>: Enables you to manually select the Mailbox (master or mirror) for recovery.</p>
<p>Select one of the following values:</p>
<ul>
<li><span class="code">auto</span> - (default) automatically determines which Mailbox to recover</li>
<li><span class="code">master</span> - recovers master Mailbox</li>
<li><span class="code">mirror</span> - recovers mirror Mailbox</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-cipher_passphrase_dkfile (-cpdkf)</span>: Enter a path to a derived key used to encrypt the protection password.<br />
Maximum: 256 alphanumeric characters.</p>
<p>Use this parameter if Gateway files are encrypted. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.</p>
<p>If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><span class="code">-cipher_passphrase_encfile (-cpencf)</span>: Enter a path to an encrypted password file.
Use this parameter if encoding protects the Mailbox and its associated object database files. If you provide a path, Gateway automatically tries to access the password phrase required to open the Mailbox file from the specified user file.
If you do not specify a value for this parameter, Gateway dynamically prompts you for the passphrase.         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Before initializing the Mailbox, stop Gateway.</p>
<p>Enter the command:</p>
<p><span class="code">pelmon recover_base</span></p>
<p>Gateway returns:</p>
<p>Testing Axway Gateway status: stopped</p>
<p>Checking software license key: xxxx xxxx xxxx xxxx xxxx</p>
<p>Expiration date :none</p>
<p>Max network connections :unlimited</p>
<p>Max site :unlimited</p>
<p>Protocol options :PSIT FTP</p>
<p>Misc product options :'Secured Mailbox'</p>
<p>Checking monitor option versus license:</p>
<p>Mirror option enable</p>
<p>Checking monitor context:</p>
<p>Monitor stopped normally</p>
<p>Last checking ended normally</p>
<p>Checking base integrity:</p>
<p>Master mailbox : corrupted</p>
<p>Mirror mailbox : OK</p>
<p>Recovering of master mailbox: Done</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_change_pass_phrase"></span>

### pelmon change\_pass\_phrase

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon change_pass_phrase</strong> [-old_cipher_passphrase_dkfile (-ocpdkf)] [-old_cipher_passphrase_encfile (-ocpencf)] [-new_cipher_passphrase_dkfile (-ncpdkf)]</p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to change the key used to encrypt the Gateway database files and to perform the encryption. The key is derived from the passphrase that you enter using this command.</p>
<p>For security purposes, you should regularly change the key.</p>
<p>If you later want to unencrypt the database files, specify the current passphrase in <span class="code">-ocpdkf</span> and <strong>do not</strong> specify a new passphrase in <span class="code">-ncpdkf</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>Prerequisites</p>         </td>
         <td><p>Before you change the passphrase:</p>
<ol>
<li>In the configuration menu, specify the <span style="font-weight: bold;"><a href="../../../../configuration_start_here/config_gateway_paras#olh_gateway_database_protection">Database protection option</a></span>.</li>
<li><a href="../../../../starting_and_stopping_server/t_reloading_profile">Reload the profile</a>.</li>
<li>Stop Gateway.</li>
<li>Back up all the database files (all <span class="code">.dat</span> files present in <span class="code">&lt;Gateway installation directory&gt;/run_time/data</span>).</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p><span class="code">-old_cipher_passphrase_dkfile (-ocpdkf)</span>: Enter the path to the file that contains the derived key for encrypting old passphrase for the key used to encrypt the file.</p>
<p>If you do not specify a value, Gateway will prompt you for the old password. Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-old_cipher_passphrase_encfile (-ocpencf)</span> : Enter the path to the file that contains the old encrypted passphrase for the key used to encrypt the file.</p>
<p>If you do not specify a value, Gateway will prompt you for the old password. Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><span class="code">-new_cipher_passphrase_dkfile (-ncpdkf): </span>Enter the path to the file that contains the derived key for encrypting new passphrase for the key used to encrypt the file.<span class="code"></span>
<p>If you do not specify a value, Gateway will prompt you for the new password.</p>
<p>If the database files are already encrypted and you do not specify a value, the command will unencrypt the files.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-new_cipher_passphrase_encfile (-ncpencf)</span>: Enter the path to the file that contains the encrypted new passphrase for the key used to encrypt the file.</p>
<p>If you do not specify a value, Gateway will prompt you for the new password.</p>
<p>If the database files are already encrypted and you do not specify a value, the command will unencrypt the files.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Result</p>         </td>
         <td><p>Gateway encrypts the database files using the newly-generated key and creates new files with the extension <span class="code">.new</span>. The files that Gateway encrypts depend on the value specified in the <strong>Database protection option</strong> in the configuration menu.</p>
<p><strong>If the operation is successful:</strong></p>
<blockquote>
<p>Gateway renames the previous files with the extension <span class="code">.old</span> and the new ones with the extension <span class="code">.dat</span>. Gateway then uses the new files.</p>
<p><strong>Important:</strong> Back up the old files and remove them from the Gateway database directory. If you do not do this, the next <strong>pelmon change_pass_phrase</strong> command that you enter will not be processed. This is to prevent the old files being overwritten.</p>
</blockquote>
<p><strong>If the operation fails:</strong></p>
<blockquote>
<p>If an error occurs, the change_pass_phrase operation is immediately aborted and the files are not renamed.</p>
<p>In this case you can do one of the following:</p>
<ul>
<li>Correct the problem, then restart the change_pass_phrase operation</li>
<li>Delete the <span class="code">.new</span> files and restore the old files with the previous encryption parameters</li>
</ul>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p>pelmon change_pass_phrase</p>
<p>Gateway returns:</p>
<p>Enter your OLD pass-phrase</p>
<p>Enter your NEW pass-phrase</p>
<p>Re-enter your NEW pass-phrase</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_rebuild_vfd"></span>

### pelmon rebuild\_vfd

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon rebuild_vfd</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to repair the Virtual File Directory (VFD) from the backup.</p>
<p>Stop Gateway before you rebuild the VFD. To stop Gateway use the <span class="code" style="font-weight: bold;"><a href="../../../../starting_and_stopping_server#starting_and_stopping_gw_server">gatestop</a></span> command.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p>pelmon rebuild_vfd</p>
<p>Gateway returns:</p>
<p>Testing Gateway status : stopped.</p>
<p>Recovering VFD database...</p>
<p>Importing VFD database from text file "d:\work_area\gw6114head\install_dir\run_time\arc/vfdexport.txt"...</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelmon_reset"></span>

### pelmon reset

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>Syntax</p>         </td>
         <td><p><strong>pelmon reset</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Description</p>         </td>
         <td><p>Use this command to reset the status prompted by the <span class="code" style="font-weight: bold;"><a href="../../../../starting_and_stopping_server#after_starting_gw_server">gatestatus</a></span> command to the default value.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p>Example</p>         </td>
         <td><p>Enter the command:</p>
<p>pelmon reset</p>
<p>Gateway returns:</p>
<p>Printing Gateway status : running.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Mailbox_mirroring"></span>

## Backing up the Mailbox (mirroring)

### About mirroring

The Mailbox is the file transfer database. It is one of the most important files in Gateway. If you lose this file, you lose all the monitored information about Gateway. Gateway mirroring is an optional feature that requires no specific hardware except a second physical disk device. Mirroring protects the Gateway Mailbox from a software or hardware crash. Mirroring is submitted to a software license key.

When you activate the <span style="font-weight: bold;">[Mirror option](../../../../configuration_start_here/config_gateway_paras#Mirror_option)</span> in the configuration menu, Gateway maintains two Mailbox files instead of a single file:

-   Master Mailbox
-   Mirror Mailbox

Each operation that you perform on the master Mailbox is duplicated on the mirror Mailbox, except for the read operation.

<span style="font-weight: bold;">Note:</span> The master Mailbox file is the same as the Mailbox file used when you do not activate the mirror option.

Locate the mirror Mailbox file on a different physical disk from that of the master Mailbox file, to protect the Mailbox from a hardware crash. The disk that supports the mirror Mailbox file should have the same availability as the disk that stores the master Mailbox. When you install Gateway, you specify the location of the mirror Mailbox.

### Error detection

When you try to recover a Mailbox error, determine the nature of the error, as well as which Mailbox contains the error (master or mirror).

Three files are used to maintain Mailbox integrity:

-   Master Mailbox file - checked for integrity
-   Mirror Mailbox file - checked for integrity
-   Context file - indicates whether a crash occurred.

The <span style="font-style: italic;">context file</span> (typically a file named <span class="code">supctx.dat</span> in the <span class="code">run\_time/data</span> directory) is a text file that contains:

-   Monitor run-time information
-   Two fields for managing database integrity:
    -   <span class="code">sup\_state = 0</span> (Monitor is stopped),<span class="code"> 1</span> (Monitor is running or was stopped abnormally)
    -   <span class="code">chk\_state = 0</span> (Error found in database),<span class="code"> 1</span> (Database integrity is granted)

<span style="font-weight: bold;">Caution:</span> You can browse the context file for information. However, you must <span style="font-weight: bold;">never modify</span> field values with an editor. If you edit the file, you will damage Mailbox integrity.

Since errors may have many different origins and many different results, Gateway always checks the integrity of both Mailboxes before startup. It performs this integrity check via the <span class="code">pelmon check\_base</span> command. This command stores any errors it detects in the Gateway context file. You must correct these errors before you can start Gateway.

When you start Gateway, it writes its running state in the context file. If the system crashes, Gateway can then detect that it did not stop normally. To restart Gateway, check Mailbox integrity manually.

### General guidelines for using mirroring

Stop Gateway before you perform any Mailbox maintenance operations.

When an integrity problem occurs, perform all the possible checks (using the <span class="code" style="font-weight: bold;">[pelmon](#Managing_Mailbox_pelmon)</span> command, or platform-specific tools) before attempting any recovery.

<span style="font-weight: bold;">Important:</span> Recovery is an irreversible operation. Backup both Mailbox files before attempting a recovery.

Related topics

[Maintaining the Mailbox (kfmcp command)](../maintaining_mailbox)

[About gatestatus messages](../../../../starting_and_stopping_server/c_gatestatus_messages)

[Configuration: Gateway parameters](../../../../configuration_start_here/config_gateway_paras)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
