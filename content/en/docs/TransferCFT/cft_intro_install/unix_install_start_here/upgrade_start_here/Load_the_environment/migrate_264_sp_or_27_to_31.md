{
    "title": "Migrating from Transfer CFT 2.6.4-SP2 or 2.7",
    "linkTitle": "Migrating from Transfer CFT 2.6.4-SP2 or 2.7",
    "weight": "240"
}This topic describes how to migrate Transfer CFT 2.6.4 SP2, or higher, or 2.7 to version 3.9. Before starting this migration procedure, review the prerequisites and information on [loading the environment](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment). Additionally, you must have installed your new Transfer CFT 3.9 and applied the most recent service pack.

## Migrating the main configuration and UCONF parameters

You can migrate the PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load the former Transfer CFT environment. See the [Migration prerequisites](..//transfercft/cft_intro_install/unix_install_start_here/upgrade_start_here/load_the_environment) for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTUTIL CFTEXT type=all, fout=cft-extract.conf</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.

<!-- -->

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Stop Transfer CFT if you have not already done so.
2.  Import your static configuration objects using the cftinit command. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>cftinit cft-extract.conf</span></td>
    </tr>
    </tbody>
    </table>

## Migrating PKI certificates

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>PKIUTIL PKIEXT fout=pki-extract.conf</span></td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the OS appropriate value:

-   UNIX: $CFTPKU

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable:  
    PKIUTIL PKIFILE fname=&lt;pki\_database\_filename>, mode='CREATE’

1.  Import your PKI certificates into the new Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>PKIUTIL &lt;prefix_character&gt;&lt;script_filename&gt;</td>
    </tr>
    </tbody>
    </table>

Examples

UNIX: PKIUTIL @pki-extract.conf

Windows: PKIUTIL #pki-extract.conf

## Migrating the runtime environment

### Migrating the catalog

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export the catalog using the command CFTMI240:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><p>CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_2.7_filename&gt;, ofname=catalog_output.xml</p></td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load the new Transfer CFT 3.9 environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><span>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=&lt;catalog_filename_new_installation&gt;</span></td>
</tr>
</tbody>
</table>

### Migrating the communication media files

1.  Load the former Transfer CFT (2.6.4 or 2.7.0) environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=&lt;com_2.7.0_filename&gt;, ofname=com_output.xml</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load the new Transfer CFT3.9 environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace the `<com_filename_new_installation>` with the corresponding environment variable:

-   UNIX: \_CFTCOM

<!-- -->

-   Windows: `$CFTCOM`

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><span>CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=&lt;com_filename_new_installation&gt;</span></td>
</tr>
</tbody>
</table>
