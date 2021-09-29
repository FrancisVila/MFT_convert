{
    "title": "Migrating from Transfer CFT\u00a02.5 or 2.6.x",
    "linkTitle": "Migrating from Transfer CFT\u00a02.5 or 2.6.x",
    "weight": "230"
}This topic describes how to migrate Transfer CFT 2.5 or 2.6 to version 3.9. Before starting this migration procedure, review the prerequisites and information on [loading the environment](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment). Additionally, you must have installed your new Transfer CFT 3.9 and applied the most recent service pack.

## Migrate the configuration

### Migrating the main configuration

Migrate PARM, PART, IDF and other static configuration objects.

1.  Load the former Transfer CFT (2.5 or 2.6) environment. See the [Migration prerequisites](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment) for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT. Enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p><span>CFTUTIL CFTEXT type=all, fout=cft-extract.conf</span></p></td>
</tr>
</tbody>
</table>

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.

<!-- -->

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Stop Transfer CFT if you have not already done so.
2.  Import your static configuration objects using the cftinit command.  
    Enter:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>cftinit cft-extract.conf</td>
</tr>
</tbody>
</table>

### Migrating UCONF parameters

1.  Load the former Transfer CFT (2.5 or 2.6) environment.

<!-- -->

1.  Display your UCONF parameters using the CFTUTIL LISTUCONF command. Enter: CFTUTIL LISTUCONF scope=user

<!-- -->

1.  Select the UCONF parameters that you want to import into the new Transfer CFT 3.9.

<!-- -->

1.  Create a script file such as:

-   UNIX: uconf-import.sh

-   Windows: uconf-import.bat

1.  For each parameter you select, add a line to the new script file in the format:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>UCONFSET id=&lt;parameter_id&gt;, value=&lt;value&gt;</p></td>
</tr>
</tbody>
</table>

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Import the selected UCONF parameters using the script file and the CFTUTIL command. Replace the &lt;script\_filename> with the new script file path:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><span>CFTUTIL &lt;prefix_character&gt;&lt;script_filename&gt;</span></td>
</tr>
</tbody>
</table>

Example

-   UNIX: CFTUTIL @uconf-import.sh

<!-- -->

-   Windows: CFTUTIL #uconf-import.bat

### Migrating PKI certificates

For Transfer CFT 2.5, you must be at Transfer CFT 2.5.1 SP2 or higher before performing this procedure. For Transfer CFT 2.6.4, you must be at Transfer CFT 2.6.4 SP2 or higher before performing this procedure.

1.  Load the former Transfer CFT environment (2.5 or 2.6).

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT: PKIUTIL PKIEXT fout=pki-extract.conf

<!-- -->

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate value: PKIUTIL PKIFILE fname=&lt;pki\_database\_filename>, mode='CREATE’

-   UNIX: $CFTPKU

-   Windows: The absolute path value for the CFTPKU environment variable

1.  Import your PKI certificates into the new Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path: PKIUTIL &lt;prefix\_character>&lt;script\_filename>

Example

-   UNIX: PKIUTIL @pki-extract.conf

<!-- -->

-   Windows: PKIUTIL #pki-extract.conf

## Migrating the runtime environment

### Migrating the catalog

1.  Load the former Transfer CFT (2.5 or 2.6) environment.

<!-- -->

1.  Export the catalog using the command CFTMI240.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_2.5_filename&gt;, ofname=catalog_output.xml</td>
</tr>
</tbody>
</table>

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA
-   Windows: $CFTCATA

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=&lt;catalog_filename_new_installation&gt;</td>
</tr>
</tbody>
</table>

### Migrating the communication media files

1.  Load the former Transfer CFT (2.5 or 2.6) environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=&lt;com_2.5_filename&gt;, ofname=com_output.xml</p></td>
</tr>
</tbody>
</table>

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace the &lt;com\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCOM

<!-- -->

-   Windows: $CFTCOM

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=&lt;com_filename_new_installation&gt;</td>
</tr>
</tbody>
</table>
