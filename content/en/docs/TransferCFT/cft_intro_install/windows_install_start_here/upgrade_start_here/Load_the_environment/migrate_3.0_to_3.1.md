{
    "title": "Migrate from Transfer CFT 3.0.1 ",
    "linkTitle": "Migrate from Transfer CFT 3.0.1 ",
    "weight": "270"
}This topic describes how to migrate Transfer CFT 3.0.1 or 3.1.2 to version 3.9. It is divided in 2 sections, the first section describes migration for a single node architecture, and the second section multi-node architecture. Lastly there are instructions explaining what would be needed to migrate from single node architecture to multi node architecture.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">When migrating from 3.0.1 to 3.3.x, you must install SP10 P6 on all Transfer CFTs 3.0.1 that inter-operate with any Transfer CFTs 3.3.x prior to migrating.</td>
</tr>
</tbody>
</table>

## Single node architecture

### Migrating the configuration

#### Migrating the main configuration and UCONF parameters

Migrate PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load former Transfer CFT 3.0.1 or 3.1.x environment. See the [Migration prerequisites](../../../../unix_install_start_here/upgrade_start_here/load_the_environment) for details.
2.  Export your static configuration objects using the command CFTUTIL CFTEXT. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTUTIL CFTEXT type=all, fout=cft-extract.conf</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.
2.  Load Transfer CFT 3.9 environment.
3.  Stop Transfer CFT if you have not already done so.
4.  Import your static configuration objects using the cftinit command. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>cftinit cft-extract.conf</td>
    </tr>
    </tbody>
    </table>

### Migrating PKI certificates

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>PKIUTIL PKIEXT fout=pki-extract.conf</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load the Transfer CFT 3.9 environment.
2.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate value: $CFTPKU for UNIX, the absolute path value for the CFTPKU for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>PKIUTIL PKIFILE fname=&lt;pki_database_filename&gt;, mode='CREATE’</span></td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Import your PKI certificates into Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;prefix\_character> based on your system, @ for UNIX and # for Windows.  
    Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>PKIUTIL &lt;prefix_character&gt;pki-extract.conf</span></td>
    </tr>
    </tbody>
    </table>

### Migrating the runtime environment

#### Migrating the catalog

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export the catalog using the command CFTMI. Replace the &lt;catalog\_filename > with the corresponding environment variable, \_CFTCATA for UNIX or $CFTCATA for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_filename_former_cft&gt;, ofname=catalog_output.xml</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load Transfer CFT 3.9 environment.
2.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename > with the corresponding environment variable, \_CFTCATA for UNIX or $CFTCATA for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=&lt;catalog_filename_new_cft &gt;</td>
    </tr>
    </tbody>
    </table>

#### Migrating the communication media files

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export the communication media file using command CFTMI. Replace the &lt;com\_filename > with the corresponding environment variable, \_CFTCOM for UNIX, or $CFTCOM for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI MIGR type=COM, direct=FROMCOM, ifname=&lt;com_filename_former_cft&gt;, ofname=com_output.xml</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load Transfer CFT 3.9 environment.
2.  Import the communication media file using command CFTMI. Replace the &lt;com\_filename > with the corresponding environment variable, \_CFTCOM for UNIX or $CFTCOM for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=&lt;com_filename_new_cft &gt;</td>
    </tr>
    </tbody>
    </table>

#### Executables and binaries

Remember that you can copy your post-processing scripts directly from the runtime/exec to the new version (3.9). When you copy files from the exec folder, be certain to modify any paths that point to the former version (for example, 3.0.1, 3.1.3, or 3.2.x). However, you must rebuild APIs and EXITS (binaries).

## Multi-node architecture

### Migrating the configuration

#### Migrating the main configuration and UCONF parameters

Migrate PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export your static configuration objects using the command CFTUTIL CFTEXT. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTUTIL CFTEXT type=all, fout=cft-extract.conf</td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.
2.  Load Transfer CFT 3.9 environment.
3.  Import your static configuration objects using the cftinit command. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>cftinit cft-extract.conf</span></td>
    </tr>
    </tbody>
    </table>

### Migrating PKI certificates

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter: PKIUTIL PKIEXT fout=pki-extract.conf

<!-- -->

1.  Load the Transfer CFT 3.9 environment.
2.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate value, $CFTPKU for UNIX or the absolute path value for the CFTPKU for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>PKIUTIL PKIFILE fname=&lt;pki_database_filename&gt;, mode='CREATE’</span></td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Import your PKI certificates into Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;prefix\_character> based on your system, @ for UNIX and # for Windows. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>PKIUTIL &lt;prefix_character&gt;pki-extract.conf</td>
    </tr>
    </tbody>
    </table>

### Migrating the runtime environment

#### Migrating the catalog

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export all catalogs (one per node, named as cftcataXX, where XX is the node number with range from 00 to &lt;number of nodes - 1>) using the command CFTMI. For each catalog. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td><span>CFTMI MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_filename_former_cft_for_node_&lt;node&gt;&gt;, ofname=catalog_output_&lt;node&gt;.xml</span></td>
    </tr>
    </tbody>
    </table>

<!-- -->

1.  Load Transfer CFT 3.9 environment.
2.  Import all catalogs using the command CFTMI for each of them. Use the same node number on both &lt;node> on command. Enter:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output_&lt;node&gt;.xml, ofname=&lt;catalog_filename_new_cft&gt;&lt;node&gt;</td>
    </tr>
    </tbody>
    </table>

#### Migrating the communication media files

1.  Load former Transfer CFT 3.0.1 or 3.1.2 environment.
2.  Export all communication media files (cftcom and cftcomXX, where XX is the node number with range from 00 to &lt;number of nodes - 1>) using the command CFTMI. For each communication media file.
    -   Enter: CFTMI MIGR type=COM, direct=FROMCOM, ifname=&lt;com\_filename\_for\_node\_manager\_on\_former\_cft>, ofname=com\_output.xml
    -   For each node, enter: CFTMI MIGR type=COM, direct=FROMCOM, ifname=&lt;com\_filename\_for\_node\_&lt;node>\_on\_former\_cft>, ofname=com\_output\_&lt;node>.xml
3.  Load Transfer CFT 3.9 environment.
4.  Import all communication media files using command CFTMI for each of them. Use the same node number on both &lt;node> on command.
    -   Enter: CFTMI MIGR type=COM, direct=TOCOM, ifname=com\_ouput.xml, ofname=&lt;com\_filename\_for\_node\_manager\_on\_new\_cft>
    -   For each node, enter: CFTMI MIGR type=COM, direct=TOCOM, ifname=com\_ouput\_&lt;node>.xml, ofname=&lt;com\_filename\_for\_node\_&lt;node>\_on\_new\_cft>

## Single-node to multi-node architecture migration

The only difference between migrating from single node to multi-node architecture and migrating from single-node to single-node architecture is the catalog migration step. Since there is no catalog named cftcata in multi-node, import the catalog exported from single-node architecture to the catalog of any of the nodes in the multi-node architecture.
