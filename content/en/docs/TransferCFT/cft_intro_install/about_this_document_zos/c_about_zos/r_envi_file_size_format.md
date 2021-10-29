{
    "title": "File sizes and formats",
    "linkTitle": "File sizes and formats",
    "weight": "160"
}This section describes the installation environment and the space requirements for installation.

A *distribution* environment is created during the product retrieval phase of the installation. This distribution environment contains the transferred files that provide the product contents, as well as any installed upgrades.

The Transfer CFT *instance* is the environment that the user configures for operational use, and is created from the distribution environment. File sizes in the user target environment are defined in the JCL J2IICFT. This JCL is defined twice - in the UPLIB library, and in the INSTALL library of the distribution environment.

The tables in this section provide information about the files and allocation requirements for the distribution and instance environments. Note that an ESD installation requires an additional 1100 disk cylinders (3390 disk) of space.

## <span id="Distribution_environment file_formats_and_requirements_"></span><span id="kanchor70"></span>Distribution environment file formats and requirements

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>File</th>
         <th>Info</th>
         <th>Allocation in cylinders</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>INSTALL</p>         </td>
         <td>            <p>Installation and exploitation</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>10</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SAMPLE</p>         </td>
         <td>            <p>Sample JCLs, and Transfer CFT sample parameters</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>2</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SAMPLEO</p>         </td>
         <td>            <p>COBOL samples (Exit and API)</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>2</p>         </td>
      </tr>
      <tr class="even">
         <td>COPY         </td>
         <td>            <p>Copy book (Cobol)</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>2         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SAMPLEC</p>         </td>
         <td>            <p>C samples (Exit and API)</p>
            <p>PO – VB – 255</p>
DSNTYPE=LIBRARY         </td>
         <td>            <p>2</p>         </td>
      </tr>
      <tr class="even">
         <td>H         </td>
         <td>            <p>C headers</p>
            <p>PO – VB – 255</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>2         </td>
      </tr>
      <tr class="odd">
         <td>SAMPLEA         </td>
         <td>            <p>ASM samples (Exit and API)</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>2         </td>
      </tr>
      <tr class="even">
         <td>            <p>OBJ</p>         </td>
         <td>            <p>Object modules</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>
            <p>(NON-SMP/E INSTALLATION)</p>         </td>
         <td>            <p>100</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>PFTOBJ</p>         </td>
         <td>            <p>Patched object modules</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>
            <p>(NON-SMP/E INSTALLATION)</p>         </td>
         <td>            <p>300</p>         </td>
      </tr>
      <tr class="even">
         <td>LOAD         </td>
         <td>Transfer CFT load modules
(SMP/E INSTALLATION)         </td>
         <td>120         </td>
      </tr>
      <tr class="odd">
         <td>            <p>DOC</p>         </td>
         <td>            <p>Readme (patch or service pack)</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>10</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>CNTL</p>         </td>
         <td>            <p>Link edit control cards</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>3</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>MAC</p>         </td>
         <td>            <p>ASM macro</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>2</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SCR</p>         </td>
         <td>            <p>UI components (Copilot, Secure Relay) and patches</p>
            <p>PO –VB – 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>500</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>UPLIB</p>         </td>
         <td>            <p>Upload library for the product, service packs, and patches</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>100</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>LOG</p>         </td>
         <td>            <p>Installation log</p>
            <p>PS – VB – 255</p>
            <p>DSNTYPE=LIBRARY</p>
            <p>(NON-SMP/E INSTALLATION)</p>         </td>
         <td>            <p>1</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>UPARM</p>         </td>
         <td>            <p>Configuration parameters</p>
            <p>PO – VB – 255</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>2</p>         </td>
      </tr>
      <tr class="even">
         <td>EXEC         </td>
         <td>            <p>Transfer CFT procedures</p>
            <p>PO – FB 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>2         </td>
      </tr>
      <tr class="odd">
         <td>XMLLIB         </td>
         <td>            <p>XML components (CSD, etc.)</p>
            <p>PO – VB - 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>2         </td>
      </tr>
      <tr class="even">
         <td>PKIMSG         </td>
         <td>            <p>Trusted File messages</p>
            <p>PO – FB - 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>1         </td>
      </tr>
   </tbody>
</table>

## <span id="Instance"></span><span id="kanchor71"></span>Instance environment file formats and requirements

The following allocations are required per Transfer CFT.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p><strong>File</strong></p></th>
         <th>            <p><strong>Environment</strong></p></th>
         <th>            <p><strong>Allocation</strong></p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>INSTALL</p>         </td>
         <td>            <p>PO – FB – 80</p>
            <p>DSNTYPE=PDS</p>         </td>
         <td>            <p>SPACE = (3120,(600,225,40) )</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SAMPLE</p>         </td>
         <td>            <p>PO – FB – 80</p>
            <p>DSNTYPE=PDS</p>         </td>
         <td>            <p>SPACE = (27920,(100,100,30))</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>SAMPLEO</p>         </td>
         <td>            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>SPACE = (27920,(100,100,-))</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SAMPLEC</p>         </td>
         <td>            <p>PO – VB - 255</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>SPACE = (27920,(100,100,-))</p>         </td>
      </tr>
      <tr class="odd">
         <td>SAMPLEA         </td>
         <td>PO – FB - 80
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE = (27920,(100,100,-))         </td>
      </tr>
      <tr class="even">
         <td>            <p>cftroot/wwwroot</p>         </td>
         <td>            <p>ZFS directory</p>
            <p>(Copilot)</p>         </td>
         <td>            <p>25 Mega</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>EXEC</p>         </td>
         <td>            <p>PO – FB – 80</p>
            <p>DSNTYPE=PDS</p>         </td>
         <td>            <p>SPACE = (3120,(195,195,30))</p>         </td>
      </tr>
      <tr class="even">
         <td>XSR         </td>
         <td>            <p>ZFS directory</p>
            <p>(Secure Relay)</p>         </td>
         <td>          </td>
      </tr>
      <tr class="odd">
         <td>            <p>XMLLIB</p>         </td>
         <td>            <p>PO – VB – 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>SPACE = (27998,(100,50,-))</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>CERTIF</p>         </td>
         <td>            <p>PO – VB – 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE = (27998,(10,5,-))         </td>
      </tr>
      <tr class="odd">
         <td>            <p>LOAD</p>         </td>
         <td>            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>SPACE  = (CYL,(120,50,-))</p>         </td>
      </tr>
      <tr class="even">
         <td><span id="USER.load"></span>USER.LOAD         </td>
         <td>DSNTYPE=LIBRARY         </td>
         <td>SPACE = (CYL,(50,20,-))         </td>
      </tr>
      <tr class="odd">
         <td>            <p>UCONF</p>         </td>
         <td>            <p>Runtime configuration parameters</p>
            <p>PS – VB - 2048</p>         </td>
         <td>            <p>SPACE = (TRK,(5,2))</p>         </td>
      </tr>
      <tr class="even">
         <td>UCONFRUN         </td>
         <td>            <p>Runtime configuration parameters</p>
            <p>PS – VB – 2048</p>         </td>
         <td>SPACE=(TRK,(5,2))         </td>
      </tr>
      <tr class="odd">
         <td>USER.OBJ         </td>
         <td>            <p>API and exits objects</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE=(3200,(200,100,-))         </td>
      </tr>
      <tr class="even">
         <td>            <p>UPARM</p>         </td>
         <td>            <p>PO – VB - 255</p>
            <p>DSNTYPE=PDS</p>         </td>
         <td>            <p>SPACE = (TRK,(5,5,20))</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>PKIMSG</p>         </td>
         <td>            <p>PO – VB - 4090</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>            <p>SPACE=(TRK,(1,1,-))</p>         </td>
      </tr>
      <tr class="even">
         <td>XLATE         </td>
         <td>            <p>PO – FB - 256</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE=(TRK,(5,5,-))         </td>
      </tr>
      <tr class="odd">
         <td>FTEST         </td>
         <td>            <p>Test file</p>
            <p>PS – VB – 84</p>         </td>
         <td>SPACE = (TRK,(1,1))         </td>
      </tr>
      <tr class="even">
         <td>INCDLL         </td>
         <td>            <p>SYSDEFSD – Link-edit IMPORT control statements</p>
            <p>PO – FB – 80</p>
            <p>DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE = (TRK,(50,10,-))         </td>
      </tr>
      <tr class="odd">
         <td>MONLOG         </td>
         <td>            <p>Started Transfer CFT server log for multi-node</p>
            <p>PS – VB – 255</p>         </td>
         <td>SPACE = (TRK,(20,10))         </td>
      </tr>
      <tr class="even">
         <td>UPLOAD         </td>
         <td>            <p>Upload library used by Central Governance</p>
            <p>PO – FB – 80
DSNTYPE=LIBRARY</p>         </td>
         <td>SPACE = (TRK,(20,10))         </td>
      </tr>
      <tr class="odd">
         <td>LOG         </td>
         <td>Installation LOG
PS – VB - 255         </td>
         <td>SPACE =
(TRK,(10,50))         </td>
      </tr>
      <tr class="even">
         <td>CRYPKEY         </td>
         <td>File name containing the private key that enciphers data         </td>
         <td>          </td>
      </tr>
      <tr class="odd">
         <td>CRYPSALT         </td>
         <td>File name containing the salt used to create the private key         </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">          </td>
      </tr>
   </tbody>
</table>

-   The *Instance environment* list above does not include files that Transfer CFT creates in its implementation, such as CATALOG, PARM, PART, COM, PKIFILE, LOG, ACCOUNT etc.
-   The persistent cache file for PassPort AM (CFTAM, VSAM KSDS) is created when the UCONF AM.type=passport variable is set to Yes.
-   To customize INSTALL, SAMPLE, EXEC and UPARM THE library must be PDS and not PDSE.

Related topics

-   [About Transfer CFT in z/OS](transfercft/cft_intro_install/about_this_document_zos/c_about_zos)
-   Installation overview
