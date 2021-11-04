{
    "title": "Migrating from Transfer CFT 2.4 to 3.9",
    "linkTitle": "Migrating from Transfer CFT 2.4.x",
    "weight": "220"
}This topic describes how to migrate from Transfer CFT 2.4 to version <span class="mc-variable axway_variables.Component_Version variable">3.9</span>. Before starting this migration procedure, review the prerequisites and information on [loading the environment](../). Additionally, you must have installed your new <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="mc-variable axway_variables.Release_Number variable">3.9</span> and applied the most recent service pack.

## Migrating the configuration

### Migrating the main configuration

Migrate PARM, PART, IDF and other static configuration objects.

1.  Load the Transfer CFT 2.4 environment. See the <a href="../" class="MCXref xref">Migration prerequisites</a> for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter: <span class="code">CFTUTIL CFTEXT type=all, fout=cft-extract.conf</span>

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> installation.

<!-- -->

1.  Load the Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.
2.  Stop <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> if you have not already done so.

<!-- -->

1.  Import your static configuration objects using the cftinit command. Enter:

<!-- -->


    cftinit cft-extract.conf

### Migrating trkapi.cfg file parameters

Migrate the parameters from the Transfer CFT 2.4 trkapi.cfg file.

1.  In the trkapi.cfg file, select the parameters you want to import in <span class="mc-variable axway_variables.Component_Version variable">3.9</span>.

<!-- -->

1.  Create a script file, for example:

-   UNIX:<span class="code"> trkapi-import.sh</span>
-   Windows:<span class="code"> trkapi-import.bat</span>

1.  For each parameter you select, add a UCONF command line to your new script file using the format:

<!-- -->


    UCONFSET id=<parameter_id>, value=<value>

Use the parameter mapping between trkapi and UCONF, as listed in the following table, to specify the correct parameter id.

<span class="autonumber"></span>Parameter mapping between the trkapi.cfg file and UCONF

<table>
   <th>
      <tr>
<th><p>Parameter in trkapi.cfg</p>         </th>
<th><p>Parameter names in UCONF</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>TRACE</p>         </td>
         <td><p>sentinel.trktrace</p>         </td>
      </tr>
      <tr>
         <td><p>TRKGMTDIFF</p>         </td>
         <td><p>sentinel.trkgmtdiff</p>         </td>
      </tr>
      <tr>
         <td><p>TRKIPADDR_BKUP</p>         </td>
         <td><p>sentinel.trkipaddr_bkup</p>         </td>
      </tr>
      <tr>
         <td><p>TRKIPPORT</p>         </td>
         <td><p>sentinel.trkipport</p>         </td>
      </tr>
      <tr>
         <td><p>TRKIPPORT_BKUP</p>         </td>
         <td><p>sentinel.trkipport_bkup</p>         </td>
      </tr>
      <tr>
         <td><p>TRKLOCALADDR</p>         </td>
         <td><p>sentinel.trklocaladdr</p>         </td>
      </tr>
      <tr>
         <td><p>TRKPRODUCTNAME</p>         </td>
         <td><p>sentinel.trkproductname</p>         </td>
      </tr>
      <tr>
         <td><p>XFB.BufferSize</p>         </td>
         <td><p>sentinel.xfb.buffer_size</p>         </td>
      </tr>
      <tr>
         <td><p>XFB.Log (UNIX)</p>         </td>
         <td><p>sentinel.xfb.log</p>         </td>
      </tr>
      <tr>
         <td><p>XFBLOG (Windows)</p>         </td>
         <td><p>sentinel.xfb.log</p>         </td>
      </tr>
      <tr>
         <td><p>XFB.Sentinel</p>         </td>
         <td><p>sentinel.xfb.enable</p>         </td>
      </tr>
      <tr>
         <td><p>XFB.Trace</p>         </td>
         <td><p>sentinel.xfb.trace</p>         </td>
      </tr>
      <tr>
         <td><p>XFB.Transfer</p>         </td>
         <td><p>sentinel.xfb.transfer</p>         </td>
      </tr>
   </tbody>
</table>

1.  Load the Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace &lt;script\_filename> with the new script file path.

<!-- -->



    CFTUTIL <prefix_character><script_filename>

Example

-   UNIX: CFTUTIL @trkapi-import.sh
-   Windows: CFTUTIL #trkapi-import.bat

### Migrating copconf.ini parameters

Migrate parameters from the Transfer CFT 2.4 copconf.ini file.

1.  From the copconf.ini file, select the parameters you want to import into version <span class="mc-variable axway_variables.Component_Version variable">3.9</span>.

<!-- -->

1.  Create a script file, for example:

-   UNIX: copconf-import.sh
-   Windows: copconf-import.bat

1.  For each selected parameter add a UCONF command line in your new script file using the format:

UCONFSET id=&lt;parameter\_id>, value=&lt;value>

Use the parameters mapping between copconf and UCONF as listed in the following table to specify the correct parameter id.

<span class="autonumber"></span>Parameter mapping between copconf file and UCONF

<table>
   <th>
      <tr>
<th><p>Parameter in copconf.ini</p>         </th>
<th><p>Parameter name in UCONF</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>BatchList</p>         </td>
         <td><p>copilot.batches</p>         </td>
      </tr>
      <tr>
         <td><p>CFTCOM</p>         </td>
         <td><p>copilot.cft.com</p>         </td>
      </tr>
      <tr>
         <td><p>CFTMEDIACOM</p>         </td>
         <td><p>copilot.cft.mediacom</p>         </td>
      </tr>
      <tr>
         <td><p>ChildProcessTimeout</p>         </td>
         <td><p>copilot.misc.childprocesstimeout</p>         </td>
      </tr>
      <tr>
         <td><p>HttpRootDir</p>         </td>
         <td><p>copilot.http.httprootdir</p>         </td>
      </tr>
      <tr>
         <td><p>MinNbProcessReady</p>         </td>
         <td><p>copilot.misc.minnbprocessready</p>         </td>
      </tr>
      <tr>
         <td><p>NbProcessToStart</p>         </td>
         <td><p>copilot.misc.nbprocesstostart</p>         </td>
      </tr>
      <tr>
         <td><p>NBWAITCFTCATA</p>         </td>
         <td><p>copilot.cft.nbwaitcftcata</p>         </td>
      </tr>
      <tr>
         <td><p>ServerHost</p>         </td>
         <td><p>copilot.general.serverhost</p>         </td>
      </tr>
      <tr>
         <td><p>ServerPort</p>         </td>
         <td><p>copilot.general.serverport</p>         </td>
      </tr>
      <tr>
         <td><p>SslCertFile</p>         </td>
         <td><p>copilot.ssl.sslcertfile</p>         </td>
      </tr>
      <tr>
         <td><p>SslCertPassword</p>         </td>
         <td><p>copilot.ssl.sslcertpassword</p>         </td>
      </tr>
      <tr>
         <td><p>SslKeyFile</p>         </td>
         <td><p>copilot.ssl.sslkeyfile</p>         </td>
      </tr>
      <tr>
         <td><p>SslKeyPassword</p>         </td>
         <td><p>copilot.ssl.sslkeypassword</p>         </td>
      </tr>
      <tr>
         <td><p>TcpTimeout</p>         </td>
         <td><p>copilot.misc.tcptimeout</p>         </td>
      </tr>
      <tr>
         <td><p>TIMERWAITCFTCATA</p>         </td>
         <td><p>copilot.cft.timerwaitcftcata</p>         </td>
      </tr>
      <tr>
         <td><p>TrcMaxLen</p>         </td>
         <td><p>copilot.trace.trcmaxlen</p>         </td>
      </tr>
      <tr>
         <td><p>TrcType</p>         </td>
         <td><p>copilot.trace.trctype</p>         </td>
      </tr>
      <tr>
         <td><p>wlogComment</p>         </td>
         <td><p>copilot.batches.wlog.comment</p>         </td>
      </tr>
      <tr>
         <td><p>wlogParams</p>         </td>
         <td><p>copilot.batches.wlog.params</p>         </td>
      </tr>
      <tr>
         <td><p>WsiComplience</p>         </td>
         <td><p>copilot.webservices.wsicomplience</p>         </td>
      </tr>
   </tbody>
</table>

1.  Load the Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace the &lt;script\_filename> with the new script file path.

<!-- -->



    CFTUTIL <prefix_character><script_filename>

Example

-   UNIX: CFTUTIL @copconf-import.sh

<!-- -->

-   Windows: CFTUTIL #copconf-import.bat

### Migrating PKI certificates

You must be at Transfer CFT 2.4.1 SP5 or higher before performing this procedure.

1.  Load the Transfer CFT 2.4 environment.

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT:

<!-- -->



    PKIUTIL PKIEXT fout=pki-extract.conf

1.  Load the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate variable:

-   UNIX: $CFTPKU

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable

<!-- -->



    PKIUTIL PKIFILE fname=<pki_database_filename>, mode='CREATE’

1.  Import your PKI certificates into Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path.

<!-- -->



    PKIUTIL <prefix_character><script_filename>

Example

-   UNIX: PKIUTIL @pki-extract.conf

<!-- -->

-   Windows: PKIUTIL #pki-extract.conf

## Migrating the runtime environment

### Migrating the catalog

1.  Load the Transfer CFT 2.4 environment.

<!-- -->

1.  Export the catalog using the command CFTMI240:

<!-- -->



    CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=<catalog_2.4_filename>, ofname=catalog_output.xml

1.  Load the Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

<!-- -->



    CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=<catalog_filename_new_installation>

### Migrating the communication media files

1.  Load the Transfer CFT V2.4 environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:

<!-- -->



    CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=<com_2.4_filename>, ofname=com_output.xml

1.  Load Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace &lt;com\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCOM

<!-- -->

-   Windows: $CFTCOM

<!-- -->


    CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=<com_filename_new_installation>
