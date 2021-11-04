{
    "title": "Upgrade  Transfer CFT ",
    "linkTitle": "Upgrade Transfer CFT",
    "weight": "170"
}This section explains how to upgrade an existing Transfer CFT from 3.1.3 or higher to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> <span class="mc-variable Primary.Transfer_CFT version_long variable">3.9</span>. It begins by detailing the prerequisites for a standalone (non multi-node) upgrade. For details on upgrading a multi-node installation, see <a href="../upgrade_multinode_ux#Upgrade" class="MCXref xref">Upgrade a Transfer CFT multi-node installation</a>.

## About upgrades

As of <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> 3.4 there is no separate upgrade package, you use the installation package to perform an upgrade procedure as described in the sections below.

All passwords stored in the UCONF dictionary, or in the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> databases (for example, CFTPART, CFTPARM) are cyphered using the key generated at installation. If you are performing an upgrade, all passwords are cyphered using a hard-coded key. We recommend that you generate an encryption key.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>See also silent mode for details on using the silent installation method.         </td>
      </tr>
   </tbody>
</table>

<span id="Before"></span>

## Before you start

Before beginning the upgrade procedure, you should:

-   Download the Transfer CFT installation kit, available  at [support.axway.com](https://support.axway.com/).

<!-- -->

-   Stop the Transfer CFT server and the Transfer CFT Copilot server, by entering:
    -   cft stop
    -   copstop -f

## Limitations

During an upgrade, if the CFTCOM file path is greater than 64 characters the COM file is not migrated, and you must migrate it manually.

When upgrading from <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> 3.1.3 to 3.3.2 or higher, check that the PKIPASSW length value in the CFT 3.1.3 version (source) is not greater than 8 characters. If it is, truncate the password as described in <a href="../../../mig_impact_considerations" class="MCXref xref">Migration or upgrade impact and considerations</a>

## Use <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> to upgrade <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>

<span id="testing"></span>You can perform <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> upgrades using <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>. However, from the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> interface you cannot remove service packs or patches, and can only upgrade Transfer CFT as of Transfer CFT 3.1.3 with last service pack (to the latest version). You cannot perform a <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> migration via <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

Please refer to the [Central Governance documentation](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/AxwayStartPage.htm) for details.

<span id="Upgrade"></span>

## Upgrade options

You can use the following installer options for <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> <span class="mc-variable axway_variables.Release_Number variable">3.9</span> when performing an upgrade:

**--architecture &lt;architecture>**: Installation architecture (single or cluster mode).

-   Default: single
-   Allowed: single first\_host additional\_host

**--runtimedir &lt;runtimedir>**: Shared Runtime Directory. On LEGACY upgrades, this is the shared data directory where the Axway Installer was installed.

-   Only used when architecture=additional\_host

**--installdir &lt;installdir>**: Directory where the Transfer CFT is installed/upgraded. On LEGACY upgrades, this is the directory where the Axway Installer was installed.

-   Not used when architecture=additional\_host
-   Default:&lt;Current Drive>:\\axway\\cft

**--conf-file &lt;conf-file>**: File used to personalize installation of Transfer CFT

-   In this type of installation only 2 parameters are used:
    -   \- architecture and installdir (if architecture = single/first\_host), or
    -   \- architecture and runtimedir (if architecture = additional\_host)

You can set these using command line or the configuration file. The values passed in command line take precedence over the values in the configuration file.

## Upgrade Transfer CFT 3.1.3, 3.2.x, or 3.3.2 to <span class="mc-variable Primary.Transfer_CFT version_long variable">3.9</span>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Remember to update the product key between versions.         </td>
      </tr>
   </tbody>
</table>

**Step 1: Upgrade to the latest Transfer CFT 3.1.3, 3.2.x, or 3.3.2 Service Pack**

Run the Axway Installer in update mode.

1.  Launch the Axway Installer

2.  Apply the Transfer\_CFT\_3.x.y\_SP\*\*\*\*\*.zip

    Where \*\*\*\*\* represents the SP level and the platform

    Example: Transfer\_CFT\_3.1.3\_SP3\_aix-power-64\_BN8712000.zip

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In this step you are working with a zip file (not a jar as in earlier Installer versions). Do NOT unzip/uncompress the zip file.         </td>
      </tr>
   </tbody>
</table>

Step 2: Upgrade to Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>This operation removes the old Axway Installer and all its content, so no rollback is available. You should backup the content of your installation directory if you want to have the option of undoing this operation.         </td>
      </tr>
   </tbody>
</table>

1.  Uncompress the Transfer CFT installation kit.

2.  From the Transfer CFT installation kit, enter:  


        ./Transfer_CFT_3.9_Install_<OS>_<BN>.run [<options>]

3.  Accept the license and the appropriate installation mode (for example, single installation).

4.  When prompted for the installation directory, enter the path to the existing Transfer CFT installation directory.

Available options

The following available options are described in detail in [Upgrade options](#Upgrade):

-   --architecture &lt;architecture>
-   --runtimedir &lt;runtimedir> (only available when architecture = additional\_hosts)
-   --installdir &lt;installdir>
-   --conf-file &lt;conf-file>
-   --help
-   --debuglevel
-   --mode

<span id="Upgrade"></span>

## Post upgrade

After completing the upgrade procedure, your Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span>, exec scripts are operational. However, you must rebuild your programs that use C and COBOL APIs and exits.

After performing an upgrade, all passwords are cyphered using a hard-coded key. We recommend that you generate an encryption key as described in [Generate an encryption](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Security/cipher_key.htm).

### Set the profile

Once you complete an upgrade from 3.7 or lower, you must execute the profile before running Transfer CFT 3.8 or higher.

### Check the new version

To check the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> version, as well as the license key and system information, enter the command:



    CFTUTIL ABOUT