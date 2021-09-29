{
    "title": "Running Transfer CFT for the first time",
    "linkTitle": "Running Transfer CFT for the first time",
    "weight": "210"
}# <span id="kanchor5"></span><span id="Running_CFT_for_the_first_time__Windows_"></span>Running Transfer CFT for the first time

The elements and tasks required to
start Transfer CFT for the first time include:

-   [Set the environment](#operations_to_perform_before_starting_cft)
-   [Start Transfer
    CFT using a command](#starting_cft)
-   [Shut
    down Transfer CFT using a command](#shutting_down_cft)
-   [Start or stop Transfer CFT via a user interface](#start)
-   [Service mode](#service)
-   [Start the CFTW desktop window](#start2)

## <span id="Operations_to_perform_before_starting_CFT"></span>Set the environment

After installing Transfer CFT
, but before starting Transfer CFT you should:

-   Execute the profile.bat in the Transfer CFT runtime directory to define environment
    variables, or execute profile.ps1 if you are using Windows PowerShell instead of Batch.
-   Create a new set of Transfer
    CFT working files, parameters, partners, catalog, communication file, logs,
    use the sample configuration files cft-tcp.conf and cft-tcp-part.conf in the `runtime\conf` directory. You can configure these during the product installation or manually after installation.
-   Use cftinit &lt;configuration\_file> > and/or cftupdate to interpret the parameter and
    partner files.  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><p>cftinit conf\cft-tcp.conf</p>
    cftupdate conf\cft-tcp-part.conf</td>
    </tr>
    </tbody>
    </table>

      
    or  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>cftinit conf\cft-tcp.conf conf\cft-tcp-part.conf</td>
    </tr>
    </tbody>
    </table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Caution  </strong></span></td>
<td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">These commands generate an initial configuration by <strong>creating</strong> the configuration files. Any previous configurations, and any data in the communication file, catalog, or log files will be <strong>lost</strong>.</td>
</tr>
</tbody>
</table>

Sample file details

-   cft-tcp.conf: Contains PARM object definitions (PARM, CAT, COM, LOG, ACCNT, PROT, SEND, RECV,...etc.).
-   cft-tcp-part.conf: Contains partner definitions (CFTPART, CFTTCP, CFTSSL).

Delivered partners are:

-   PARIS - NEW YORK
-   LOOP
-   LOOPSSL0

### Start and stop commands

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Version 2.7.1 and higher</th>
<th>Version 2.7.0 and lower</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>cft start</td>
<td>cftstart</td>
</tr>
<tr class="even">
<td>cft stop</td>
<td>cftstop</td>
</tr>
<tr class="odd">
<td>cft status</td>
<td>cftstatus</td>
</tr>
<tr class="even">
<td>cft force-stop</td>
<td>cftstop -kill</td>
</tr>
<tr class="odd">
<td>cft force-stop -kill</td>
<td>cftstop -forcedkill</td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The <span>cftstart </span>and <span>cftstop </span>commands, from version 2.7.0 and earlier, are redirected to the standardized commands for continued compatibility.</td>
</tr>
</tbody>
</table>

## <span id="Starting_CFT"></span>Start Transfer CFT using a command

If you have not already done so, from the runtime directory execute the profile.bat to set the Transfer CFT environment.
Then in the same dos session, enter the command: cft start

## <span id="Shutting_down_CFT"></span>Shut down Transfer CFT using a command

You can use one of the following methods to shut down Transfer CFT:

-   CFTUTIL utility  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><p>CFTUTIL shut fast=no</p>
    <p><em>or</em></p>
    <p>CFTUTIL shut fast=yes</p></td>
    </tr>
    </tbody>
    </table>
-   cft utility using stop  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>cft stop</td>
    </tr>
    </tbody>
    </table>

For more information, see the administrative commands in [Manage the Transfer CFT server](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/administration/start_stop_cft.htm).

## <span id="Start"></span>Start or stop Transfer CFT using a user interface

You can also use either [Central Governance](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CentralGov/operations/t_startCFT.htm) or the Transfer CFT Copilot UI to start or shut down Transfer CFT.

## <span id="Service"></span>Service mode

You can retroactively install Service mode for Transfer CFT. Use the Installer Configure mode to install and uninstall the services for the Transfer CFT Server and Transfer CFT Copilot. To launch the Installer in **Configure** mode, from the Start menu select Axway Software &gt; Axway Transfer CFT &gt; Configure.

## <span id="Start2"></span>Start the CFTW desktop window

You can use the Windows utility `cftw.exe` to open a desktop window that displays the Transfer CFT log messages and processes list in separate tabs. The `cft start` command automatically launches this cftw.exe utility when the UCONF parameter `cft.nt.start_graphmode` is set to **Yes** (default value).

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">When Transfer CFT is running as a service, you must have the service configured to authorize desktop interaction, and you must manually launch the cftw.exe.</td>
</tr>
</tbody>
</table>

If Transfer CFTis not running, use the `-wait `option with cftw so that the utility waits for Transfer CFT to start instead of exiting immediately.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cftw.exe -w</td>
</tr>
</tbody>
</table>

As of Transfer CFT v3.0.1, a second cftw UCONF parameter,` cft.nt.cftw_display_log_messages`, is available. To display log messages in the cftw window, change the parameter setting from **No** (default value) to **Yes**.

For more information, see the administrative commands in [Manage the Transfer CFT server](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/administration/start_stop_cft.htm).
