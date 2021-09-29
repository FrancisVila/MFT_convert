{
    "title": "Unix operations",
    "linkTitle": "Unix operations",
    "weight": "160"
}The elements and tasks required to
start Transfer CFT for the first time include:

-   [Set the environment](#set)
-   [Start and stopping Transfer
    CFT](#configuring_cft_)
    -   [Start using a command](#start)
    -   [Shut
        down using a command](#shut)
    -   [Start or stop via a user interface](#start2)

## <span id="Set"></span>Set the environment

After installing Transfer CFT
, but before starting Transfer CFT you should:

-   Execute the profile in the Transfer CFT runtime directory to define environment
    variables. Run: ‘. ./profile’
-   Create a new set of Transfer
    CFT working files, parameters, partners, catalog, communication file, logs,
    use the sample configuration files cft-tcp.conf and cft-tcp-part.conf in the runtime/conf directory. You can configure these during the product installation, or manually after installation.
-   Use cftinit &lt;configuration\_file> > and/or cftupdate to interpret the parameter and
    partner files.  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><p>cftinit conf/cft-tcp.conf</p>
    <p>cftupdate conf/cft-tcp-part.conf</p></td>
    </tr>
    </tbody>
    </table>

      
    or  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>cftinit conf/cft-tcp.conf conf/cft-tcp-part.conf</td>
    </tr>
    </tbody>
    </table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Caution  </strong></span></td>
<td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" data-valign="top">These commands generate an initial configuration by <span>creating </span>the configuration files. Any previous configurations, and any data in the communication file, catalog, or log files will be <strong>lost</strong>.</td>
</tr>
</tbody>
</table>

Sample file details

-   cft-tcp.conf: Contains PARM object definitions (PARM, CAT, COM, LOG, ACCNT, PROT, SEND, RECV,...etc.)
-   cft-tcp-part.conf: Contains partner definitions (CFTPART, CFTTCP, CFTSSL)

Delivered partners are:

-   PARIS - NEW YORK
-   LOOP
-   LOOPSSL0

## Start and stop commands

The following table lists the commands according to Transfer CFT version.

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
<td>cft force-stop –kill</td>
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

### <span id="Configuring_CFT_"></span>Start up

You can start Transfer CFT with the cft start utility; see also Transfer CFT Management Utilities.

### <span id="Shut"></span>Shut down

You can use one of the following methods to shut down Transfer CFT:

-   The CFTUTIL utility
-   The cft utility

For more information, see the administrative commands in [Manage the Transfer CFT server](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/administration/start_stop_cft.htm).

## <span id="Start2"></span>Start or stop via a user interface

You can also use either [Central Governance](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CentralGov/operations/t_startCFT.htm) or the Transfer CFT to start or shut down Transfer CFT.
