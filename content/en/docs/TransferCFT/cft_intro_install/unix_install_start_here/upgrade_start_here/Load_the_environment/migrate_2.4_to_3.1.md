{
    "title": "Migrating from Transfer CFT 2.4.x",
    "linkTitle": "Migrating from Transfer CFT 2.4.x",
    "weight": "220"
}This topic describes how to migrate from Transfer CFT 2.4 to version 3.9. Before starting this migration procedure, review the prerequisites and information on [loading the environment](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment). Additionally, you must have installed your new Transfer CFT 3.9 and applied the most recent service pack.

## Migrating the configuration

### Migrating the main configuration

Migrate PARM, PART, IDF and other static configuration objects.

1.  Load the Transfer CFT 2.4 environment. See the [Migration prerequisites](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment) for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter: CFTUTIL CFTEXT type=all, fout=cft-extract.conf

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the Transfer CFT 3.9 installation.

<!-- -->

1.  Load the Transfer CFT 3.9 environment.
2.  Stop Transfer CFT if you have not already done so.

<!-- -->

1.  Import your static configuration objects using the cftinit command. Enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cftinit cft-extract.conf</td>
</tr>
</tbody>
</table>

### Migrating trkapi.cfg file parameters

Migrate the parameters from the Transfer CFT 2.4 trkapi.cfg file.

1.  In the trkapi.cfg file, select the parameters you want to import in 3.9.

<!-- -->

1.  Create a script file, for example:

-   UNIX: trkapi-import.sh
-   Windows: trkapi-import.bat

1.  For each parameter you select, add a UCONF command line to your new script file using the format:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>UCONFSET id=&lt;parameter_id&gt;, value=&lt;value&gt;</td>
</tr>
</tbody>
</table>

Use the parameter mapping between trkapi and UCONF, as listed in the following table, to specify the correct parameter id.

Parameter mapping between the trkapi.cfg file and UCONF

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Parameter in trkapi.cfg</p></th>
<th><p>Parameter names in UCONF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TRACE</p></td>
<td><p>sentinel.trktrace</p></td>
</tr>
<tr class="even">
<td><p>TRKGMTDIFF</p></td>
<td><p>sentinel.trkgmtdiff</p></td>
</tr>
<tr class="odd">
<td><p>TRKIPADDR_BKUP</p></td>
<td><p>sentinel.trkipaddr_bkup</p></td>
</tr>
<tr class="even">
<td><p>TRKIPPORT</p></td>
<td><p>sentinel.trkipport</p></td>
</tr>
<tr class="odd">
<td><p>TRKIPPORT_BKUP</p></td>
<td><p>sentinel.trkipport_bkup</p></td>
</tr>
<tr class="even">
<td><p>TRKLOCALADDR</p></td>
<td><p>sentinel.trklocaladdr</p></td>
</tr>
<tr class="odd">
<td><p>TRKPRODUCTNAME</p></td>
<td><p>sentinel.trkproductname</p></td>
</tr>
<tr class="even">
<td><p>XFB.BufferSize</p></td>
<td><p>sentinel.xfb.buffer_size</p></td>
</tr>
<tr class="odd" data-mc-conditions="Primary.unix_in">
<td><p>XFB.Log (UNIX)</p></td>
<td><p>sentinel.xfb.log</p></td>
</tr>
<tr class="even" data-mc-conditions="Primary.windows_in">
<td><p>XFBLOG (Windows)</p></td>
<td><p>sentinel.xfb.log</p></td>
</tr>
<tr class="odd">
<td><p>XFB.Sentinel</p></td>
<td><p>sentinel.xfb.enable</p></td>
</tr>
<tr class="even">
<td><p>XFB.Trace</p></td>
<td><p>sentinel.xfb.trace</p></td>
</tr>
<tr class="odd">
<td><p>XFB.Transfer</p></td>
<td><p>sentinel.xfb.transfer</p></td>
</tr>
</tbody>
</table>

1.  Load the Transfer CFT 3.9 environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace &lt;script\_filename> with the new script file path.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL &lt;prefix_character&gt;&lt;script_filename&gt;</p></td>
</tr>
</tbody>
</table>

Example

-   UNIX: CFTUTIL @trkapi-import.sh
-   Windows: CFTUTIL #trkapi-import.bat

### Migrating copconf.ini parameters

Migrate parameters from the Transfer CFT 2.4 copconf.ini file.

1.  From the copconf.ini file, select the parameters you want to import into version 3.9.

<!-- -->

1.  Create a script file, for example:

-   UNIX: copconf-import.sh
-   Windows: copconf-import.bat

1.  For each selected parameter add a UCONF command line in your new script file using the format:

UCONFSET id=&lt;parameter\_id>, value=&lt;value>

Use the parameters mapping between copconf and UCONF as listed in the following table to specify the correct parameter id.

Parameter mapping between copconf file and UCONF

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Parameter in copconf.ini</p></th>
<th><p>Parameter name in UCONF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>BatchList</p></td>
<td><p>copilot.batches</p></td>
</tr>
<tr class="even">
<td><p>CFTCOM</p></td>
<td><p>copilot.cft.com</p></td>
</tr>
<tr class="odd">
<td><p>CFTMEDIACOM</p></td>
<td><p>copilot.cft.mediacom</p></td>
</tr>
<tr class="even">
<td><p>ChildProcessTimeout</p></td>
<td><p>copilot.misc.childprocesstimeout</p></td>
</tr>
<tr class="odd">
<td><p>HttpRootDir</p></td>
<td><p>copilot.http.httprootdir</p></td>
</tr>
<tr class="even">
<td><p>MinNbProcessReady</p></td>
<td><p>copilot.misc.minnbprocessready</p></td>
</tr>
<tr class="odd">
<td><p>NbProcessToStart</p></td>
<td><p>copilot.misc.nbprocesstostart</p></td>
</tr>
<tr class="even">
<td><p>NBWAITCFTCATA</p></td>
<td><p>copilot.cft.nbwaitcftcata</p></td>
</tr>
<tr class="odd">
<td><p>ServerHost</p></td>
<td><p>copilot.general.serverhost</p></td>
</tr>
<tr class="even">
<td><p>ServerPort</p></td>
<td><p>copilot.general.serverport</p></td>
</tr>
<tr class="odd">
<td><p>SslCertFile</p></td>
<td><p>copilot.ssl.sslcertfile</p></td>
</tr>
<tr class="even">
<td><p>SslCertPassword</p></td>
<td><p>copilot.ssl.sslcertpassword</p></td>
</tr>
<tr class="odd">
<td><p>SslKeyFile</p></td>
<td><p>copilot.ssl.sslkeyfile</p></td>
</tr>
<tr class="even">
<td><p>SslKeyPassword</p></td>
<td><p>copilot.ssl.sslkeypassword</p></td>
</tr>
<tr class="odd">
<td><p>TcpTimeout</p></td>
<td><p>copilot.misc.tcptimeout</p></td>
</tr>
<tr class="even">
<td><p>TIMERWAITCFTCATA</p></td>
<td><p>copilot.cft.timerwaitcftcata</p></td>
</tr>
<tr class="odd">
<td><p>TrcMaxLen</p></td>
<td><p>copilot.trace.trcmaxlen</p></td>
</tr>
<tr class="even">
<td><p>TrcType</p></td>
<td><p>copilot.trace.trctype</p></td>
</tr>
<tr class="odd">
<td><p>wlogComment</p></td>
<td><p>copilot.batches.wlog.comment</p></td>
</tr>
<tr class="even">
<td><p>wlogParams</p></td>
<td><p>copilot.batches.wlog.params</p></td>
</tr>
<tr class="odd">
<td><p>WsiComplience</p></td>
<td><p>copilot.webservices.wsicomplience</p></td>
</tr>
</tbody>
</table>

1.  Load the Transfer CFT 3.9 environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace the &lt;script\_filename> with the new script file path.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTUTIL &lt;prefix_character&gt;&lt;script_filename&gt;</p></td>
</tr>
</tbody>
</table>

Example

-   UNIX: CFTUTIL @copconf-import.sh

<!-- -->

-   Windows: CFTUTIL #copconf-import.bat

### Migrating PKI certificates

You must be at Transfer CFT 2.4.1 SP5 or higher before performing this procedure.

1.  Load the Transfer CFT 2.4 environment.

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIUTIL PKIEXT fout=pki-extract.conf</p></td>
</tr>
</tbody>
</table>

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate variable:

-   UNIX: $CFTPKU

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIUTIL PKIFILE fname=&lt;pki_database_filename&gt;, mode='CREATE’</p></td>
</tr>
</tbody>
</table>

1.  Import your PKI certificates into Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>PKIUTIL &lt;prefix_character&gt;&lt;script_filename&gt;</p></td>
</tr>
</tbody>
</table>

Example

-   UNIX: PKIUTIL @pki-extract.conf

<!-- -->

-   Windows: PKIUTIL #pki-extract.conf

## Migrating the runtime environment

### Migrating the catalog

1.  Load the Transfer CFT 2.4 environment.

<!-- -->

1.  Export the catalog using the command CFTMI240:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_2.4_filename&gt;, ofname=catalog_output.xml</p></td>
</tr>
</tbody>
</table>

1.  Load the Transfer CFT 3.9 environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=&lt;catalog_filename_new_installation&gt;</p></td>
</tr>
</tbody>
</table>

### Migrating the communication media files

1.  Load the Transfer CFT V2.4 environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=&lt;com_2.4_filename&gt;, ofname=com_output.xml</p></td>
</tr>
</tbody>
</table>

1.  Load Transfer CFT 3.9 environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace &lt;com\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCOM

<!-- -->

-   Windows: $CFTCOM

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=&lt;com_filename_new_installation&gt;</td>
</tr>
</tbody>
</table>
