{
    "title": "Upgrade a Transfer CFT multi-node installation",
    "linkTitle": "Upgrade a multi-node installation",
    "weight": "180"
}This section describes how to upgrade from a Transfer CFT 3.1.3, 3.2.x, 3.3.2, or 3.4 multi-node, multihost installation to Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span>.

As of <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> 3.4 there is no separate upgrade package, you use the installation package to perform an upgrade procedure as described in the sections below.

<span id="Before"></span>

## Before you start

Before beginning the upgrade procedure, download the Transfer CFT installation kit available at [support.axway.com](https://support.axway.com/).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Remember that <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> clusters must be fully stopped while performing an upgrade.         </td>
      </tr>
   </tbody>
</table>

## Limitation

During an upgrade, if the CFTCOM file path is greater than 64 characters the COM file is not migrated, and you must migrate it manually.

## Procedure

For details on shared disks, node commands, and other multi-node considerations, see *[Manage multi-node architecture](../../../../about_multinode)*.

### Upgrade all hosts

1.  Stop Copilot. This command stops Copilot as well all cftnodes running on that machine.  



        copstop -f

2.  Connect to the first machine and execute the following command:

3.  

        ./Transfer_CFT_3.9_Install_<OS>_<BN>.run --architecture first_host --installdir <installdir>

     

4.  For each additional host, connect to the machine and execute the following command:  



        ./Transfer_CFT_3.9_Install_<OS>_<BN>.run --architecture additional_host --runtimedir <runtimedir>

-   Use the two following parameters, depending on if this is the first host or an additional host:
    -   <span class="code">architecture </span>and <span class="code">installdir </span>(first\_host), *or*
    -   <span class="code">architecture </span>and <span class="code">runtimedir </span>(additional\_host)
-   Where:
    -   --architecture &lt;architecture>: Installation architecture (first\_host or additional\_host).
    -   --installdir &lt;installdir>: For a legacy upgrade, this is the directory where the Axway Installer was installed. When this parameter is assigned, it overwrites any reference in the configuration file (first\_host).
    -   --runtimedir &lt;runtimedir>: For a legacy upgrade, this is the shared data directory where the Axway Installer was installed. When this parameter is assigned, it overwrites any reference in the configuration file (additional\_host).

### Restart the upgraded Transfer CFT multihost multi-node environment

1.  Launch the Transfer CFT profile from the Transfer CFT runtime directory on the shared disk of each machine.  

2.  Check the new version using the following command:  



        CFTUTIL ABOUT

3.  Start Copilot (start each of the Copilots in the multi-node environment).  



        copstart

4.  After restarting the Copilots, restart the Transfer CFT server:  



        cft restart

5.  Check the upgraded Transfer CFT multi-node multihost system.  



        CFTUTIL listnode

    -   All of the Copilots should be started

    <!-- -->

    -   All of the Transfer CFT nodes must be started

Your Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> exec scripts are now operational. However, you must rebuild your APIs and Exits. Once Transfer CFT has been upgraded on a host you can start that instance, there is no need to wait until Transfer CFT is upgraded on every host.

## Managing multi-node

For details on shared disks, node commands, and other multi-node considerations, refer to the *Transfer CFT <span class="mc-variable axway_variables.Release_Number variable">3.9</span> User Guide &gt; *Manage multi-node architecture**.

## Post upgrade

After completing the upgrade procedure, your Transfer CFT <span class="mc-variable axway_variables.Component_Version variable">3.9</span>, exec scripts are operational. However, you must rebuild your programs that use APIs and exits.

After performing an upgrade, all passwords are cyphered using a hard-coded key. We recommend that you generate an encryption key as described in [Generate an encryption](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Security/cipher_key.htm).

## Check the new version

To check the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> version, as well as the license key and system information, enter the command:



    CFTUTIL ABOUT

## Uninstall an upgrade pack

The procedure is the same as when you uninstall a Service Pack. See [Uninstall Transfer CFT](../../uninstall_transfercft_ux).