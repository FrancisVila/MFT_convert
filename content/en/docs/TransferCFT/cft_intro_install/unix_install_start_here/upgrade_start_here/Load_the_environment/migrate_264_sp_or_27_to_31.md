{
    "title": "Migrating Transfer CFT 2.6.4 SP2 or 2.7 to 3.9",
    "linkTitle": "Migrating from Transfer CFT 2.6.4-SP2 or 2.7",
    "weight": "240"
}This topic describes how to migrate Transfer CFT 2.6.4 SP2, or higher, or 2.7 to version {{< TransferCFT/componentversion  >}}.  Before starting this migration procedure, review the prerequisites and information on [loading the environment](../). Additionally, you must  have installed your new   {{< TransferCFT/componentshortname  >}} {{< TransferCFT/releasenumber  >}} and applied the most recent service pack.

## Migrating the main configuration and UCONF parameters

You can migrate the PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load the former Transfer CFT  environment.  See the <a href="../" class="MCXref xref">Migration prerequisites</a> for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter:  
    ```
    CFTUTIL CFTEXT type=all, fout=cft-extract.conf
    ```

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT {{< TransferCFT/componentversion >}} installation.

<!-- -->

1.  Load the new Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Stop {{< TransferCFT/hflongproductname >}} if you have not already done so.
2.  Import your static configuration objects using the cftinit command. Enter:  
    ```
3.  `cftinit cft-extract.conf`

## Migrating PKI certificates

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:  
    ```
2.  `PKIUTIL PKIEXT fout=pki-extract.conf`

<!-- -->

1.  Load the new Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the OS appropriate value:

-   UNIX: `$CFTPKU`

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable:  
    `PKIUTIL PKIFILE fname=<pki_database_filename>, mode='CREATE’`

1.  Import your PKI certificates into the new Transfer CFT {{< TransferCFT/componentversion >}} using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path:  
    ```
    PKIUTIL <prefix_character><script_filename>
    ```

Examples

UNIX: `PKIUTIL @pki-extract.conf`

Windows: `PKIUTIL #pki-extract.conf`

## Migrating the runtime environment

### Migrating the catalog

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export the catalog using the command CFTMI240:  
    ```
    CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=<catalog_2.7_filename>, ofname=catalog_output.xml
    ```

<!-- -->

1.  Load the new Transfer CFT {{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

Example

```
```

### Migrating the communication media files

1.  Load the former Transfer CFT (2.6.4 or 2.7.0) environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:  
    ```
    CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=<com_2.7.0_filename>, ofname=com_output.xml
    ```

<!-- -->

1.  Load the new Transfer CFT{{< TransferCFT/componentversion >}} environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace the `<com_filename_new_installation>` with the corresponding environment variable:

-   UNIX: `_CFTCOM`

<!-- -->

-   Windows: `$CFTCOM`

Example

```
```
