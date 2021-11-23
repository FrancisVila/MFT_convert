{
    "title": "Upgrading to 6.17",
    "linkTitle": "Migrating to 6.17",
    "weight": "80"
}This topic describes a step ­by­ step procedure to upgrade from Gateway V6.16.x to V6.17.

**Important**: Before you start this upgrade procedure you must perform the operations described in <a href="../before_migrating" class="MCXref xref">Before Upgrading</a>. To avoid a conflict between the old and new environment variables, it is strongly recommended to configure the old and new versions of Gateway on separate consoles.

## Step 1: Install and configure Gateway V6.17

To upgrade the configuration files from previous versions to V6.17:

1.  Ensure that the previous version is **V6.16.1 SP12**.
2.  Do not install the new version of Gateway in the old environment. Check that the environment variables do not point to the old version of Gateway.
3.  Ensure that the old version of Gateway is stopped.
4.  Ensure you have a new product key if required.
5.  Download and install the latest Service Packs and patches.
6.  Check the hardware and software requirements for Gateway V6.17 in the {{< Gateway/componentshortname >}} *[Installation guide](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm)* .
7.  For UNIX platforms, also refer to the *Gateway [*Configuration Guide*](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm)*.

### Procedure

1.  Install Gateway V6.17.3 SP10 in a different location from the previous version. Use the same local Site name that was used in the previous version.
2.  Go to the Gateway V6.17 home installation directory.
3.  Back up and then remove the following files:
    -   `run_time/etc/newconf.ini `(if it exists)
    -   run\_time/etc/pelsetup.ini
    -   run\_time/etc/dconfsave.ini
    -   `run_time/etc/pelsetup.def` (refer to notes below)
4.  Copy the following files from the previous version:
    -   run\_time/etc/pelsetup.ini
    -   run\_time/etc/dconfsave.ini
    -   `run_time/etc/pelsetup.def` (refer to notes below)
5.  Run the following command:
    -   On UNIX: `run_time/etc/setup_server.sh migrate`` `
    -   On Windows: `run_time\etc\setup_server.bat migrate`
6.  Use the `gatestart `command to start Gateway V6.17.
7.  Use the GUI to complete the information for the global and additional parameters from the information recovered during the audit (other than the specific parameters associated with different protocols).
8.  Use the `gatestop `command to stop Gateway V6.17.

### **Notes**

-   If the file `run_time/etc/pelsetup.def `was not modified in the previous version, it is not recommended to replace the new version of this file with the previous one

-   If you are using the old `pelsetup.def`, you must take the following values from the backed-­up `pelsetup.def`:
    -   `p_xsr_java_home`
    -   `notif_exec_path`
    -   `gc_cstcp_command`
    -   `gc_csiui_command`
    -   the entire Collector section

-   The file `pelsetup.ini `must be modified with the values taken from the backed­-up `pelsetup.ini `file ``for:
    -   `cstcp_command`
    -   `csiui_command`

-   If the new product key is different from the previous one, either:
    -   Edit the file `pelsetup.ini `file and manually replace the value of the key (section \[monitor\], parameter name product\_key  
        OR
    -   start {{< Gateway/gatewayname >}} and change the value of the product key in the configuration menu of the GUI.

-   When using {{< Gateway/securerelayname >}} (formerly XSR), it is strongly advised to update to version 2.6.4 .

-   When using {{< Gateway/gatewayname >}} with {{< Gateway/integratorname >}}, a shared directory must be pointed to by the configuration. If this entry has been filled with a relative path under the previous Gateway home directory it will not be valid after the upgrade. In this case copy the directory to the same place in the new {{< Gateway/gatewayname >}} installation.

-   If your scripts use one of the following functions (perl and C) :
    -   `ExitXferAfterBegin_C`
    -   `ExitXferAfterEnd_C`
    -   `ExitRcProtoConn_C`

    then you have to refactor the function calls and recompile. This is because the parameter `In_TlsSessionInfo_t `now refers to a modified structure, to allow for both TLS and SSH protocols.  
    See exitext.h and exitxdef.h files for information about the modified structure definition.

-   To migrate from a 32-bit AIX system to a 64-bit system:

    1\) Export the `xfer.dat `and `xferb.dat `files from the 32-bit AIX:

    pelexport -outfile xferaix32.dat

    pelexport -outfile xferbaix32.dat -io xferb

    2\) Import the same files into the 64-bit system:

    pelimport -infile xferaix32.dat

    pelimport -infile xferbaix32.dat -io xferb

    The location of files `xfer.dat `and `xferb.dat `files is taken from the profile environment

## Step 2: Copy files to the new environment

1.  If required, copy the following to the new environment:
    -   Character conversion tables
    -   Security tables
    -   Statistics dictionary
    -   All the files that can be retained (as described in Files that can be retained)

## Step 3: Start Gateway V6.17

1.  Load the profile: `run_time/etc/profile`

<!-- -->

1.  Use the `gatestart `command to start Gateway.

### Automatic startup (Windows)

Under Windows, you can create an automatic startup of Gateway. To do this, you need to create a service for Gateway. Use the following command to create the service:

`bin\pelinst `*Service\_Name*` `*Directory\_Path*` `*User Password description*

If you want to delete the service, enter the command:

`bin\pelinst `*Service\_Name*` remove`

## Step 4: Import Gateway objects

### Delete the default Rule Table

1.  Load the profile: `run_time/etc/profile `

<!-- -->

1.  Before importing your Gateway objects, delete the newly­created default Rule Table:

peladm delete\_ruletable -n DEFAULT -type XFER\_CHANGE\_STATE

### Import the objects

Use the following command to import all objects that you exported to the `output_file `output file:

pelbase import -input output\_file -site -model -appli -list -profile -user -cgategroup –cgate –ruletable -decisionrule -proxy -proplist -purgemodel - tradepart -xmsctor –sgategroup -sgate -import\_pwd\_cleartext -error\_free

> **Note:**
>
> Use the -error\_free parameter when creating the different objects. When this parameter is used, errors are ignored and the process does not stop.

### Import TLS Security Profiles

Use the following command to import the Security Profile into the database. In this example, the Security Profile is contained in the file `sprof1.sprof`:

`secbase import -if sprof1.sprof -sp -import_pwd_cleartext`

### Import SSH Security Profiles

Use the following command to import the Security Profile into the database. In this example, the Security Profile is contained in the file `sshprof1.sshprof`:

`secbase import -if sshprof1.sshprof -shp -import_pwd_cleartext`

### Import security objects

Use the `secbase import `command to import security objects that you have exported from the previous version of Gateway:

-   Security Profiles (sprof), using the `secbase import –sprof `command
-   SSH Security Profiles (sshprof), using the `secbase import –sshprof `command
-   Network Profiles (nprof), using the `secbase import –netprof `command
-   Certificates, using the `secbase import -cert `command
-   Keys, using the `secbase import –key `command

For example, to import the Network Profiles contained in the file `nprof_ouput_file `into the database, enter:

`secbase import –input nprof_ouput_file –netprof`

> **Note:**
>
> It is highly recommended that you import the Security Profiles first.

### Importing Certificates

Example

secbase import\_cert –certificate\_name "CERT"

–certificate\_file "SopraCA.pem"

–certificate\_file\_type BASE64

<span id="Migrate_exits"></span>

## Step 5: upgrade exits

Synchronous user exits are retained. Customized user exits must be recompiled, linked and then regenerated. They can be found in:

-   The Windows installation directory: `src\exituser`, `src\exitextc and src\exitclnt`

<!-- -->

-   The UNIX installation directory: `src/exituser`, `src/exitextc `and `src/exitclnt`

### Windows

> **Note:**
>
> You must recompile user exits using MS Visual Studio 2012.

1.  Use the script `profile.bat `located in `run_time\etc `in the installation directory to load the environment variables:  
    `run_time\etc\profile.bat `
2.  Execute the following command in the directory where the exit was modified:  
    `nmake /f Makefile `

### UNIX

1.  Use the `userprof.sh `script found in the installation directory to load the environment variables:  
    `sh userprof.sh `
2.  Execute the following command:  
    `make -f Makefile `

<span id="page29"></span>

## Step 6: Configure protocols and shut down Gateway

1.  Start Gateway.
2.  In the configuration menu of the GUI, complete the protocol parameters using the information that you recorded during the audit.
3.  Shut down Gateway.
4.  Edit the file `run_time/data/supctx.dat `to obtain the same chronology in the new environment. For the following parameters, enter the same values as in the old file:
    -   xfer\_local\_ident
    -   xfer\_yday
    -   xfer\_sequence
    -   sup\_state
    -   chk\_state
    -   nug\_last\_ident

## Step 7: upgrade the Mailbox and virtual Sites

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>Stop Gateway before upgrading the Mailbox.         </td>
      </tr>
   </tbody>
</table>

### Upgrading Mailbox records from an earlier version (V6.16.x) to V6.17

1.  Decrypt the Mailbox if it is encrypted:
    -   To determine whether or not the Mailbox is encrypted, use the Gateway configuration menu to see whether the Mailbox encryption option value is set to *Database files and transfer mailbox.*
    -   To decrypt the Mailbox, deactivate the Mailbox encryption option (value *None* or *Database*files only) in the configuration menu.
2.  Load the profile: `run_time/etc/profile`
3.  Execute the command:  
    6.16.0: `pelmon change_pass_phrase –ocpf password`  
    6.16.1: `pelmon change_pass_phrase –ocpdkf dkfile –ocpencf encfile`
4.  upgrade the Mailbox from the previous version to the V6.17 environment:
    -   **Caution**: Before you use the `pelmig `command, you must shut down Gateway.
    -   `pelmig –im <path6.16.x>/xfer.dat –iv V6.16 –om <path6.17>/xfer.dat –ov V6.17`
5.  upgrade the extended Mailbox from the previous version (`xferb.dat`) to the V6.17 environment:  
    Copy `xferb.dat `from 6.16.x to 6.17, replacing the default `xferb.dat `
6.  If required, re­-encrypt the Mailbox in the V6.17 environment, as described in Encrypting Mailbox Records.
7.  When using the mirrored Mailbox feature, copy the newly­ created `xfer.dat `and `xferb.dat `files into the mirror subdirectory.

**Notes:**

-   *V6.16.x* takes either of the following values: V6.16.0, V6.16.1.
-   `<path6.16.x>` indicates the pathname to the file `xfer.dat `of V6.16.x.
-   *&lt;path6.17>* indicates the pathname to the file xfer.dat of 6.17.

### Upgrading virtual sites

Please note that {{< Gateway/gatewayname  >}} version {{< Gateway/componentlongversion  >}} does not currently provide for the upgrade of virtual sites.

`vsite03.dat `will be recreated automatically.

### Encrypting Mailbox Records

If you set the encryption mode to *Database files and transfer mailbox after installation*, all Transfer records are encrypted in the Mailbox. The transferred Mailbox must therefore be encrypted using the `pelmon change_pass_phrase `command. Be sure to shut down Gateway **before** using this command.

**Example**: The following command encrypts the newly­ transferred Mailbox:

-   6.16.0: `pelmon change_pass_phrase –ncpf mailbox_password`
-   6.16.1: `pelmon change_pass_phrase –ncpdkf dkfile –ncpencf encfile `

This command creates new files with the `.new `extension and uses the key that was generated to write the encrypted data to those files. If the operation succeeds, the old files are renamed with the extension `.old`. The new files that will be used by Gateway V6.17 are assigned the extension `.dat`.

It is recommended that you back up the `.old` files, and then delete them from your Axway Gateway database directory.

To avoid destroying files with the extension `.old`, the next `pelmon change_pass_phrase `command ``is not executed if these files are still present in the Axway Gateway database directory.

> **Note:**
>
> If an error occurs during the processing of these files, the password modification operation is immediately canceled and no file is renamed. In this case, you can:

> -   Correct the problem and start the password modification operation from the beginning
> -   Delete the files with the extension .new and restore the previous values for the encryption parameters

## Step 8: Import Virtual File Directories (VFD)

1.  Load the profile: `run_time/etc/profile `
2.  Before importing Virtual File Directories, make sure that:
    -   **Gateway is shut down**
    -   You have manually deleted the data files in the VFD library (`p_runtime_dir/vfd`)
3.  Use the following command to import the VFDs that you previously exported to the file `vfd_output_file`:
    -   `vfdbase import -if vfd_output_file`  
        **Note**: If a previously mounted path on an RFD (real file directory) is missing, then:  
        \* a warning will be displayed in the console  
        \* in the case where `-iw Y` was used when importing the VFDs, the mounting point will be removed.
4.  You can then retrieve the VFD tree structure and VFD items.

## Step 9: Restart Gateway

1.  Load the profile: `run_time/etc/profile `

<!-- -->

1.  Use the `gatestart `command to restart Gateway. You have now finished upgrading Gateway.

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
