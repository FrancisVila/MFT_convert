{
    "title": "Manage the database ciphering key",
    "linkTitle": "Manage the database ciphering key",
    "weight": "230"
}This topic describes how to manage the ciphering key using the <span class="bold_in_para">cftcrypt </span>tool,  which ciphers all passwords. Information includes:

-   Overview
-   Command description
-   Renew a key
-   Upgrade a Transfer CFT
    -   Export the configuration    
    -   Generate a key
    -   Import the configuration

## Overview

All passwords stored in the UCONF dictionary, or in the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> databases (for example, CFTPART, CFTPARM) are cyphered using the key generated at installation. If you are performing an upgrade, all passwords are cyphered using a hard-coded key. We recommend that you generate an encryption key as described in [Generate an encryption](#Generate).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The encryption key is mandatory to use the embedded <a href="../sr_overview">SecureRelay.</a>         </td>
      </tr>
   </tbody>
</table>

## cftcrypt command

Syntax

cftcrypt -- ACTION -- OPTION

Actions:

-   genkey: Generate an encryption key using a password.
-   renewkey: Regenerate an encryption key using a new password along with the old password.
-   help: Display this help.

Genkey options:

-   keyfname: File where the generated key is stored.
-   saltfname: File where the computed salt is stored.
-   pass: Password.

Renewkey options:

-   pkitmp: Temporary file where the PKI configuration is stored.
-   pkipref : Prefix for certificates temporary files (z/OS only, on all other systems the non modifiable <span class="code">cftcrtmp </span> value is the prefix, for example, an exported certificate could have a name such as "cftcrtmpROOT0001").
-   noremove: Do not remove the temporary file; you can use this to keep track of what has been exported.
-   nopki:  Do not export/import the PKI base.
-   pass: Password.
-   oldpass: Old password.
-   tmpfname: Temporary file where the Transfer CFT configuration is stored.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Passwords must contain at least 8 characters, lower case, upper case, numeric and special characters(*#$!?+-@).         </td>
      </tr>
   </tbody>
</table>

Use the following command to generate an encryption key using the provided password. This creates the <span class="code">--keyfname</span> and <span class="code">--saltfname</span> files, and references them in UCONF.



    cftcrypt --genkey --keyfname FILENAME --saltfname FILENAME --pass PASSWORD

Encryption parameters in UCONF

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>crypto.key_fname         </td>
         <td><p>The path to the encryption key, which is required at <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> runtime.</p>
<p>If this parameter is not set (empty), at runtime <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> uses a hard-coded key and operates as in <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> 3.2.4.</p>         </td>
      </tr>
      <tr>
         <td>crypto.salt_fname         </td>
         <td>The path to the salt file, which is required to renew the key.         </td>
      </tr>
   </tbody>
</table>

## Renew the encryption key

To renew an encryption key run the <span class="code">renewkey</span> command:


    cftcrypt --renewkey --keyfname FILENAME --saltfname FILENAME --oldpass PASSWORD --pass PASSWORD 

The command succeeds if the referenced key and salt files exist and the <span class="code">oldpass </span>matches the password used to generate the previous key. This command exports the configuration, generates a new encryption key, and imports the configuration.

Platform specifics

-   z/OS: Use the JCL CFTRNKEY for key renewal.

### Troubleshoot the key renewal

The cftcrypt tool automatically exports/imports the PKI database when you perform a key renewal. However, to avoid potential issues, the process stops and an error is returned if an issue is detected during the PKI export/import.

-   To perform a key renewal with an empty PKI base or without a PKI file, you can use: <span class="code"> cftcrypt --renewkey --nopki </span>
-   To facilitate debugging, you can use the <span class="code">--noremove</span> option, so that the temporary files used by cftcrypt are not deleted. See the <span class="code">cftcrypt --help </span>for more information.

<span id="Generate"></span>

## Generate an encryption key following an upgrade

It is highly recommended that you generate an encryption key when you upgrade a Transfer CFT 3.2.4 or lower to Transfer CFT 3.3.2 or higher. For example:

1.  From the <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span> runtime directory, perform the extract to export the configuration.  

2.  Export the PKI database.  


        PKIUTIL PKIEXT FOUT=PKI.EXT

3.  Generate a new encryption key.  

4.  Import the PKI database.  

5.  Import the configuration.  

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>On z/OS platforms, use the JCL CFTGNKEY to generate the key.         </td>
      </tr>
   </tbody>
</table>
