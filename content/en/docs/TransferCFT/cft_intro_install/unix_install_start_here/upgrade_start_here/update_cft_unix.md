{
    "title": "Update Transfer CFT",
    "linkTitle": "Update Transfer CFT",
    "weight": "160"
}This section describes how to update Transfer CFT with a patch or service pack. You can manually perform the operation, or use <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>.

## Download the update file

Download product updates from the [Axway support website](https://support.axway.com/) to the machine you where you want to perform the update. Please note that the update file is a zip file. Do not unzip this file.

## Impacted directories when updating a product

When you install a service pack, the contents of the home directory are updated, but the runtime directory remains untouched. This is so that your customizations, such as APIs, are not overwritten.

## Use <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> for updates

You can easily perform <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> updates and apply Service Packs using <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>. Please see the Central Governance documentation for details. Because Central Governance can manage all update operations in a centralized fashion (without intervention on the Transfer CFT side), there is no need to stop the product components on the Transfer CFT machine.

Note that from the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> interface you cannot:

-   Remove service packs or patches.
-   Update <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>s installed in multi-node/multi-hosts from <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>.

<span id="Install"></span>

## Install a standard update

Stop <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> prior to installing a service pack or patch.

### Update in silent mode

Use the following command to update Transfer CFT in silent mode:



    ./Transfer_CFT_3.6_<Install/SP/Patch><OS><BN>.run --mode unattended --installdir <installation_directory>

### Update in text mode

Use the following command to update Transfer CFT in text mode:


    ./Transfer_CFT_3.6_<Install/SP/Patch>_<OS>_<BN>.run --mode text

## Uninstall an update

This section describes uninstalling a patch or service pack.

To uninstall install the previous patch or service pack. For example, to remove Transfer CFT 3.6 SP2, from the Transfer CFT 3.6 SP1 kit, run the installation pointing to the Transfer CFT 3.6 SP2 installation directory. The installer detects and replaces the SP2 content, impacting only the <span class="code">home </span>directory.

**Example**



    ./Transfer_CFT_3.6_SP1_<OS>_<BN>.run --mode text

To verify, from the Transfer CFT &lt;runtime\_dir> run the <span class="code">about </span>command.

## Install patches and service packs in a multi-node, multiple host environment

This section describes the procedure to apply a patch or service pack on a multi-node architecture based on *N* hosts. You update a Transfer CFT multi-node architecture with multi-hosts using the same procedure as for a patch or service pack, one host at a time.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> clusters can still run while performing an update.         </td>
      </tr>
   </tbody>
</table>

1.  Connect to the first host.
2.  Stop all nodes running on this host by running the command: <span class="code">copstop</span>  
    Copilot services are stopped, and local nodes are automatically re-started on the other hosts.
3.  Check that the nodes are re-started by using the command: <span class="code">CFTUTIL listnode</span>
4.  Install the patch or the service pack as usual using <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> installer as described in [Install a standard update](#Install).
5.  Start Copilot services.
6.  Connect to the next host and repeat the procedure starting at of <span class="bold_in_para">Step 2</span> (above).