{
    "title": "Migrating Transfer CFT 2.6.4 SP2 or 2.7 to 3.9",
    "linkTitle": "Migrating from Transfer CFT 2.6.4-SP2 or 2.7",
    "weight": "240"
}This topic describes how to migrate Transfer CFT 2.6.4 SP2, or higher, or 2.7 to version <span class="mc-variable axway_variables.Component_Version variable">3.9</span>. Before starting this migration procedure, review the prerequisites and information on [loading the environment](../). Additionally, you must have installed your new <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="mc-variable axway_variables.Release_Number variable">3.9</span> and applied the most recent service pack.

## Migrating the main configuration and UCONF parameters

You can migrate the PARM, PART, IDF, other static configuration objects and UCONF parameters as follows:

1.  Load the former Transfer CFT environment. See the <a href="../" class="MCXref xref">Migration prerequisites</a> for details.

<!-- -->

1.  Export your static configuration objects using the command CFTUTIL CFTEXT.  
    Enter:  


        CFTUTIL CFTEXT type=all, fout=cft-extract.conf

<!-- -->

1.  Open the extract configuration files, cft-extract.conf, and update the file paths with those of the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> installation.

<!-- -->

1.  Load the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Stop <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> if you have not already done so.

2.  Import your static configuration objects using the cftinit command. Enter:  

## Migrating PKI certificates

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export your PKI certificates using the command PKIUTIL PKIEXT. Enter:  

<!-- -->

1.  Load the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Create a new PKI internal datafile using the command PKIUTIL PKIFILE. Replace &lt;pki\_database\_filename> with the OS appropriate value:

-   UNIX: <span class="code">$CFTPKU</span>

<!-- -->

-   Windows: The absolute path value for the CFTPKU environment variable:  
    <span class="code">PKIUTIL PKIFILE fname=&lt;pki\_database\_filename>, mode='CREATE’</span>

1.  Import your PKI certificates into the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> using the command PKIUTIL. Replace the &lt;script\_filename> with the new script file path:  


        PKIUTIL <prefix_character><script_filename>

Examples

UNIX: <span class="code">PKIUTIL @pki-extract.conf</span>

Windows: <span class="code">PKIUTIL #pki-extract.conf</span>

## Migrating the runtime environment

### Migrating the catalog

1.  Load the former Transfer CFT (2.6.4 or 2.7) environment.

<!-- -->

1.  Export the catalog using the command CFTMI240:  



        CFTMI240 MIGR type=CAT, direct=FROMCAT, ifname=<catalog_2.7_filename>, ofname=catalog_output.xml

<!-- -->

1.  Load the new Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the catalog using the command CFTMI. Replace the &lt;catalog\_filename\_new\_installation> with the corresponding environment variable:

-   UNIX: \_CFTCATA

<!-- -->

-   Windows: $CFTCATA

Example


    CFTMI MIGR type=CAT, direct=TOCAT, ifname=catalog_output.xml, ofname=<catalog_filename_new_installation>

### Migrating the communication media files

1.  Load the former Transfer CFT (2.6.4 or 2.7.0) environment.

<!-- -->

1.  Export the communication media file using command CFTMI240:  


        CFTMI240 MIGR type=COM, direct=FROMCOM, ifname=<com_2.7.0_filename>, ofname=com_output.xml

<!-- -->

1.  Load the new Transfer CFT<span class="mc-variable axway_variables.Component_Version variable">3.9</span> environment.

<!-- -->

1.  Import the communication media file using command CFTMI. Replace the `<com_filename_new_installation>` with the corresponding environment variable:

-   UNIX: <span class="code">\_CFTCOM</span>

<!-- -->

-   Windows: `$CFTCOM`

Example


    CFTMI MIGR type=COM, direct=TOCOM, ifname=com_ouput.xml, ofname=<com_filename_new_installation>