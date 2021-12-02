{
    "title": "Upgrade Transfer CFT IBM i",
    "linkTitle": "Upgrade Transfer CFT IBM i",
    "weight": "230"
}This page describes two upgrade procedures for Transfer CFT 3.7 IBM i. The automatic upgrade procedure requires fewer user inputs than the manual procedure, and is the procedure of choice. This upgrade procedure enables you to change the version of an installed Transfer CFT to a more recent version while conserving its current configuration. Additionally, you can use the [rollback](#) feature if a situation arises where you need to return to a previous version.

> **Note:**
>
> The UPGRADE procedure delivered in the installation package performs the same steps as those described in the manual upgrade procedure. However, we strongly recommend using the automatic upgrade procedure instead of the manual upgrade.

> **Note:**
>
> Tip  
> CFTPGM is the standard name for the program library, and CFTPROD is the standard name for the library where the configuration files are usually located.

<span id="Upload"></span>

## Before you start

Before beginning the upgrade procedure:

-   Check that you can access the Transfer CFT upgrade pack available for download from Axway at [support.axway.com](https://support.axway.com/).
-   Stop the Transfer CFT server and the Transfer CFT Copilot (UI) server. Enter:

Optionally, you can use the display command to check the version or product details prior to upgrading.

<span id="Automati"></span>

## Automatic upgrade procedure

### Uploading the installation package

Start the UPGRADE process by uploading the Transfer CFT installation package in binary mode to the IBM i system:

1.  Log in with the `CFTINST `user.
2.  Create a temporary library: `CRTLIB CFTTMP`
3.  Create a SAVF file: `CRTSAVF FILE(CFTTMP/CFT37)`
4.  Upload the installation package to the SAVF in binary mode using FTP:  

<!-- -->

1.  Restore the SAVF file in the temporary library:  

<!-- -->

1.  After restoring the SAVF, you must add the library name in the first position of the library list for the user profile. Execute the command:  

> **Note:**
>
> The user performing the upgrade requires the same rights as for a regular installation or update (\*JOBCTL, \*SPLCTL, and \*ALLOBJ).

### Executing the UPGRADE command

Enter the UPGRADE command and press F4 to display the Transfer CFT IBM i installation screen.

The following fields are mandatory; you should complete as per your system details:

-   CFTEXTLIB: Enter the name of the temporary library used to process the upgrade. This can be existing or non-existent library, but its content is cleared during the process.
-   CFTPGM: Enter the name of the library containing the binaries of your Transfer CFT to upgrade.
-   CFTPROD: Enter the name of the library containing the working files of your Transfer CFT to upgrade.
-   ROLLBACK: '1': Enables the rollback mode (YES).  
    ‘2’: Indicates that you are NOT rolling back to a previous {{< TransferCFT/transfercftname >}} version (NO).
-   SAVF: This field only displays when you enter '1' in the ROLLBACK field. In this case, enter the name of the SAVF for the version you want to apply. The default value is the name of SAVF for the version that you downloaded. See [Rolling back an upgrade](#Rolling) for details.

### Check the new version

To check the Transfer CFT version, as well as the license key and system information, enter the command:

### About the UPGRADE command

Running the UPGRADE command:

1.  Creates a temporary library.
2.  Extracts your configuration, COM file, CAT file into this temporary library.
3.  Saves your IFS directories by moving them to new directories having the same name but which are suffixed by “\_save”.
4.  Saves your {{< TransferCFT/transfercftname >}} libraries in the SAVF located in the temporary lib.
5.  Replaces the binaries in your CFTPGM libraries by those of the new {{< TransferCFT/transfercftname >}} version.
6.  Replaces your IFS directories by those of the new {{< TransferCFT/transfercftname >}} version.
7.  Imports your configuration into your upgraded {{< TransferCFT/transfercftname >}}.

As a result, your {{< TransferCFT/transfercftname  >}} binaries are upgraded, but their location is conserved.

### Upgrading multi-node installations

The UPGRADE procedure supports multi-node configurations, where your configuration remains strictly the same.

### About IASP installations

The procedure supports the upgrade of {{< TransferCFT/transfercftname  >}} installed on an IASP. The process remains the same, the UPGRADE procedure itself detects if the {{< TransferCFT/transfercftname  >}} is an installation on ASP, and then keeps the {{< TransferCFT/transfercftname  >}} in the same ASP.

> **Note:**
>
> The UPGRADE procedure does not support the upgrade from a non-IASP CFT to an IASP Transfer CFT or vice versa. In the same spirit, an upgrade from one type of IASP to another is not supported.

<span id="Manual"></span>

## Manual upgrade procedure

This section explains how to upgrade an existing Transfer CFT IBM i from 2.7.1, 3.0.1, 3.1.3, 3.3.2, 3.4, or 3.5 to Transfer CFT {{< TransferCFT/releasenumber  >}} for either a [single installation](#Manually) or a [multi-node installation](#Manually2).

<span id="Manually"></span>

### Manually upgrade a single installation

The manual upgrade procedure is similar to the migration procedure.

1.  Load the former Transfer CFT CFT 2.7.1, 3.0.1, or 3.1.3 environment.
2.  Stop Transfer CFT.
3.  Create a backup library to save your configuration:

<!-- -->

1.  Export your configuration.
    -   Export your static configuration objects using the command CFTUTIL CFTEXT:

    <!-- -->

    -   Export your PKI certificates using the PKIUTIL PKIEXT command. Enter:

    <!-- -->

    -   Export the catalog using the CFTMI command. Enter:

    <!-- -->

    -   Export the communication media file using the CFTMI command:

    <!-- -->

    -   Additionally, you must export any procedures that are specific to your production, sample APIs, exits, and execs to your backup library.

2.  Rename the INSTALL directory, the RUNTIME directory, and the Transfer CFT libraries.

3.  You can now install the new Transfer CFT version. See <a href="../../install_intro_ibmi/use_install_command" class="MCXref xref">About the INSTALL command</a>.

4.  Import the configuration.

    -   Import your static configuration objects using the command:

    <!-- -->

    -   Import your PKI certificates using the PKIUTIL command:

    <!-- -->

    -   Import the catalog using the CFTMI command:

    <!-- -->

    -   Import the communication media file using the CFTMI command:

    <!-- -->

    -   Import specific procedures to your production, for example APIs, EXITs, and execs from the CFTUPGLIB backup library.

    > **Note:**
    >
    > You must recompile these after upgrading.

### Check the new version

To check the Transfer CFT version, as well as the license key and system information, enter:

<span id="Manually2"></span>

### Manually upgrade a Transfer CFT 2.7.1, 3.0.1, or 3.1.3 multi-node installation

The multi-node procedure is similar to the single instance upgrade procedure. **However, when exporting CAT and COM, you must export your configuration for each node.**

1.  Load the former Transfer CFT 2.7.1, 3.0.1, or 3.1.3 environment.
2.  Stop Transfer CFT IBM i.
3.  Create a temporary library for your exported configuration:

<!-- -->

1.  Export your configuration.
    -   Export your static configuration objects using the command:

    <!-- -->

    -   Export your PKI certificates using the PKIUTIL PKIEXT command:

    <!-- -->

    -   Export the catalog using the CFTMI command:

    <!-- -->

    -   Export the communication media file using the command:
        -   For each communication media file, enter:
        -   For each node, enter:

    <!-- -->

    -   You must also export any procedures that are specific to your production, such as APIs, exits, execs, etc. (Copy your API, exit sources, exec, and specific scripts.)
2.  Change the hostname for each Transfer CFT.
    Rename the INSTALL and RUNTIME directories, and the Transfer CFT libraries:  
3.  You can now install the new Transfer CFT version. See <a href="../../install_intro_ibmi/use_install_command" class="MCXref xref">About the INSTALL command</a>.
4.  Import the configuration that you saved previously in the temporary directory created in Step 3:
    -   Import the PKI certificates using the PKIUTIL command:

    <!-- -->

    -   Import the catalog using the CFTMI command:

    <!-- -->

    -   Import the communication media file using the CFTMI command:
        -   For each communication media file, enter:
        -   For each node, enter:

    -   Import specific procedures to your production, for example APIs, EXITs, and execs from the CFTUPGLIB backup library.

        > **Note:**
        >
        > You must recompile these after upgrading.

### Check the new version

To check the Transfer CFT version, as well as the license key and system information, enter the command:

<span id="Rolling"></span>

## 
