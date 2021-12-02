{
    "title": "Migrating from Transfer CFT 2.4 to 3.9",
    "linkTitle": "Migrating from Transfer CFT 2.4.x",
    "weight": "220"
}This topic describes how to migrate from Transfer CFT 2.4 to version {{< TransferCFT/componentversion  >}}. Before starting this migration procedure, review the prerequisites and information on [loading the environment](../). Additionally, you must have installed your new {{< TransferCFT/componentshortname  >}} {{< TransferCFT/releasenumber  >}} and applied the most recent service pack.

## Migrating the configuration

### Migrating the main configuration

Migrate PARM, PART, IDF and other static configuration objects.

1.  Load the Transfer CFT 2.4 environment. See the <a href="../" class="MCXref xref">Migration prerequisites</a> for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter: `CFTUTIL CFTEXT type=all, fout=cft-extract.conf`

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the Transfer CFT {{< TransferCFT/componentversion >}} installation.

<!-- -->

1.  Load the Transfer CFT {{< TransferCFT/componentversion >}} environment.
2.  Stop {{< TransferCFT/hflongproductname >}} if you have not already done so.

<!-- -->

1.  Import your static configuration objects using the cftinit command. Enter:

### Migrating trkapi.cfg file parameters

Migrate the parameters from the Transfer CFT 2.4 trkapi.cfg file.

1.  In the trkapi.cfg file, select the parameters you want to import in {{< TransferCFT/componentversion >}}.

<!-- -->

1.  Create a script file, for example:

-   UNIX:` trkapi-import.sh`
-   Windows:` trkapi-import.bat`

1.  For each parameter you select, add a UCONF command line to your new script file using the format:

Use the parameter mapping between trkapi and UCONF, as listed in the following table, to specify the correct parameter id.

Parameter mapping between the trkapi.cfg file and UCONF

1.  Load the Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace &lt;script\_filename> with the new script file path.

Example

-   UNIX: CFTUTIL @trkapi-import.sh
-   Windows: CFTUTIL #trkapi-import.bat

### Migrating copconf.ini parameters

Migrate parameters from the Transfer CFT 2.4 copconf.ini file.

1.  From the copconf.ini file, select the parameters you want to import into version {{< TransferCFT/componentversion >}}.

<!-- -->

1.  Create a script file, for example:

-   UNIX: copconf-import.sh
-   Windows: copconf-import.bat

1.  For each selected parameter add a UCONF command line in your new script file using the format:

UCONFSET id=&lt;parameter\_id>, value=&lt;value>

Use the parameters mapping between copconf and UCONF as listed in the following table to specify the correct parameter id.

Parameter mapping between copconf file and UCONF

1.  Load the Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the selected UCONF parameters using the command CFTUTIL. Replace the &lt;script\_filename> with the new script file path.

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

1.  Load the new Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the appropriate variable:

-   UNIX: $CFTPKU

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable

1.  Import your PKI certificates into Transfer CFT {{< TransferCFT/componentversion >}} using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path.

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

1.  Load the Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

### Migrating the communication media files

1.  Load the Transfer CFT V2.4 environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:

<!-- -->

1.  Load Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace &lt;com\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCOM

<!-- -->

-   Windows: $CFTCOM
