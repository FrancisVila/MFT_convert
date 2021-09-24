{
    "title": "Migrating from Transfer CFT 3.2.x or higher",
    "linkTitle": "Migrating from Transfer CFT 3.2.x or higher",
    "weight": "280"
}This topic describes how to migrate Transfer CFT 3.2.x, 3.3.2, or 3.4 to version 3.9. It is divided in 2 sections, the first section describes migration for a single node architecture, and the second section multi-node architecture. Lastly there are instructions explaining what would be needed to migrate from single node architecture to multi node architecture.

## Single node architecture

Stop Transfer CFT and the Copilot server before starting the migration.

### Migrating the configuration

#### Migrating the main configuration and UCONF parameters

Migrate PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load the former Transfer CFT 3.x environment. See the [Migration prerequisites](../../../../unix_install_start_here/upgrade_start_here/load_the_environment) for details.

2.  Export your static configuration objects using the command CFTUTIL CFTEXT. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL CFTEXT type=all, fout=cft-extract.conf         </td>
      </tr>
   </tbody>
</table>

3.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.

4.  Load Transfer CFT 3.9 environment.

5.  Stop Transfer CFT if you have not already done so.

6.  Import your static configuration objects using the cftinit command. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
               <li>cftinit cft-extract.conf               </li>
         </td>
      </tr>
   </tbody>
</table>

### Migrating PKI certificates

Stop Transfer CFT and the Transfer CFT Copilot server before starting.

1.  Load the former Transfer CFT 3.x environment.

2.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
               <li>PKIUTIL PKIEXT fout=pki-extract.conf               </li>
         </td>
      </tr>
   </tbody>
</table>

3.  Copy all files that are referenced in the pki-extractconf file (INAME OR IKNAME) to the folder where you are going to execute the PKI command on the new version. In the following example, copy ROOT0001 to the new folder in Transfer CFT 3.9.

4.  Load the Transfer CFT 3.9 environment.

5.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename&gt; with the appropriate value: $CFTPKU for UNIX, the absolute path value for the CFTPKU for Windows. Enter:

6.  Import your PKI certificates into Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;prefix\_character&gt; based on your system, @ for UNIX and # for Windows.  
    Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>PKICER       ID          = 'LOCALROOT',
              </p>
            <p> ROOTCID     = 'LOCALROOT',
</p>
            <p>               ITYPE       = 'ROOT',
 /* </p>
            <p>PKIFNAME = '',*/ /*<![CDATA[ ]]></p>
            <p> COMMENT     = '',*/
              </p>
            <p> INAME       = '<b>ROOT0001</b>',
              </p>
            <p> IFORM       = 'DER',
 /*           </p>
            <p> IKNAME      = '',*/
 /* </p>
            <p>           IKFORM      = '',*/
 /*           </p>
            <p> FOUT        = '',*/
              </p>
            <p> MODE        = 'REPLACE'</p>
         </td>
      </tr>
   </tbody>
</table>

### Migrating the runtime environment

Stop Transfer CFT and the Transfer CFT Copilot server before starting.

#### Migrating the catalog

1.  Load the former Transfer CFT 3.x environment.

2.  Export the catalog using the command CFTMI. Replace the &lt;catalog\_filename > with the corresponding environment variable, \_CFTCATA for UNIX or $CFTCATA for Windows. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><span>PKIUTIL PKIFILE fname=&lt;pki_database_filename&gt;, mode='CREATE’</span>
         </td>
      </tr>
   </tbody>
</table>

3.  Load Transfer CFT 3.9 environment.

4.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename > with the corresponding environment variable, \_CFTCATA for UNIX or $CFTCATA for Windows. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL &lt;prefix_character&gt;pki-extract.conf
                                     </td>
      </tr>
   </tbody>
</table>

#### Migrating the communication media files

1.  Load the former Transfer CFT 3.x environment.

2.  Export the communication media file using command CFTMI. Replace the &lt;com\_filename > with the corresponding environment variable, \_CFTCOM for UNIX, or $CFTCOM for Windows. Enter:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTMI MIGR type=CAT, direct=FROMCAT, ifname=&lt;catalog_filename_former_cft&gt;, ofname=catalog_output.xml         </td>
      </tr>
   </tbody>
</table>

3.  Load Transfer CFT 3.9 environment.

4.  Import the communication media file using command CFTMI. Replace the &lt;com\_filename > with the corresponding environment variable, \_CFTCOM for UNIX or $CFTCOM for Windows. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=&lt;catalog_filename_new_cft &gt;         </td>
      </tr>
   </tbody>
</table>

#### Executables and binaries

Remember that you can copy your post-processing scripts directly from the runtime/exec to the new version (3.9). When you copy files from the exec folder, be certain to modify any paths that point to the former version (3.x in this case). However, you must rebuild APIs and EXITS (binaries).

## Migrate a multi-node to multi-node architecture

### Migrating the configuration

Stop Transfer CFT and the Transfer CFT Copilot server before starting the migration.

#### Migrating the main configuration and UCONF parameters

Migrate PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load the former Transfer CFT 3.x environment.

2.  Export your static configuration objects using the command CFTUTIL CFTEXT. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTMI MIGR type=COM, direct=FROMCOM, ifname=&lt;com_filename_former_cft&gt;, ofname=com_output.xml         </td>
      </tr>
   </tbody>
</table>

3.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT 3.9 installation.

4.  Load Transfer CFT 3.9 environment.

5.  Import your static configuration objects using the cftinit command. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=&lt;com_filename_new_cft &gt;         </td>
      </tr>
   </tbody>
</table>

### Migrating PKI certificates

Stop Transfer CFT and the Transfer CFT Copilot server before starting.

1.  Load the former Transfer CFT 3.x environment.

2.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL CFTEXT type=all, fout=cft-extract.conf         </td>
      </tr>
   </tbody>
</table>

3.  Load the Transfer CFT 3.9 environment.

4.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate value, $CFTPKU for UNIX or the absolute path value for the CFTPKU for Windows. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>cftinit cft-extract.conf
                                </p>
         </td>
      </tr>
   </tbody>
</table>

5.  Import your PKI certificates into Transfer CFT 3.9 using the command PKIUTIL. Replace the &lt;prefix\_character> based on your system, @ for UNIX and # for Windows. Enter:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL PKIEXT fout=pki-extract.conf         </td>
      </tr>
   </tbody>
</table>

### Migrating the runtime environment

Stop Transfer CFT and the Transfer CFT Copilot server before starting.

#### Migrating the catalog

1.  Load the former Transfer CFT 3.x environment.

2.  Export all catalogs (one per node, named as cftcataXX, where XX is the node number with range from 00 to &lt;number of nodes - 1>) using the command CFTMI. For each catalog. Enter:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
                            PKIUTIL PKIFILE fname=&lt;pki_database_filename&gt;, mode='CREATE’
                                
                                 </td>
      </tr>
   </tbody>
</table>

3.  Load Transfer CFT 3.9 environment.

4.  Import all catalogs using the command CFTMI for each of them. Use the same node number on both &lt;node> on command. Enter:   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>PKIUTIL &lt;prefix_character&gt;pki-extract.conf         </td>
      </tr>
   </tbody>
</table>

#### Migrating the communication media files

1.  Load the former Transfer CFT 3.x environment.
2.  Export all communication media files (cftcom and cftcomXX, where XX is the node number with range from 00 to &lt;number of nodes - 1>) using the command CFTMI.   
    For each communication media file, enter:
3.  For each node, enter:
4.  Load Transfer CFT 3.9 environment.
5.  Import all communication media files using the CFTMI command.   
    For the manager, enter:
6.  For each node, enter:

## Single-node to multi-node architecture migration

The only difference between migrating from single node to multi-node architecture and migrating from single-node to single-node architecture is the catalog migration step. Since there is no catalog named cftcata in multi-node, import the catalog exported from single-node architecture to the catalog of any of the nodes in the multi-node architecture.

Be certain to stop Transfer CFT and the Transfer CFT Copilot server before performing the procedure.
