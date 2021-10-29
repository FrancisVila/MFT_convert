{
    "title": "Update Transfer CFT",
    "linkTitle": "Update Transfer CFT",
    "weight": "160"
}This section describes how to update Transfer CFT with a patch or service pack. You can manually perform the operation, or use Central Governance.

## Download the update file

Download product updates from the [Axway support website](https://support.axway.com/) to the machine you where you want to perform the update. Please note that the update file is a zip file. Do not unzip this file.

## Impacted directories when updating a product

When you install a service pack, the contents of the home directory are updated, but the runtime directory remains untouched. This is so that your customizations, such as APIs, are not overwritten.

## Use Central Governance for updates

You can easily perform Transfer CFT updates and apply Service Packs using Central Governance. Please see the Central Governance documentation for details. Because Central Governance can manage all update operations in a centralized fashion (without intervention on the Transfer CFT side), there is no need to stop the product components on the Transfer CFT machine.

Note that from the Central Governance interface you cannot:

-   Remove service packs or patches.
-   Update Transfer CFTs installed in multi-node/multi-hosts from Central Governance.

## <span id="Install"></span>Install a standard update

Stop Transfer CFT prior to installing a service pack or patch.

### Update in silent mode

Use the following command to update Transfer CFT in silent mode:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>./Transfer_CFT_3.6_&lt;Install/SP/Patch&gt;&lt;OS&gt;&lt;BN&gt;.run --mode unattended --installdir &lt;installation_directory&gt;</p>         </td>
      </tr>
   </tbody>
</table>

### Update in text mode

Use the following command to update Transfer CFT in text mode:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td><span>./Transfer_CFT_3.6_&lt;Install/SP/Patch&gt;_&lt;OS&gt;_&lt;BN&gt;.run --mode text</span>         </td>
      </tr>
   </tbody>
</table>

## Uninstall an update

This section describes uninstalling a patch or service pack.

To uninstall install the previous patch or service pack. For example, to remove Transfer CFT 3.6 SP2, from the Transfer CFT 3.6 SP1 kit, run the installation pointing to the Transfer CFT 3.6 SP2 installation directory. The installer detects and replaces the SP2 content, impacting only the home directory.

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>./Transfer_CFT_3.6_SP1_&lt;OS&gt;_&lt;BN&gt;.run --mode text</p>         </td>
      </tr>
   </tbody>
</table>

To verify, from the Transfer CFT &lt;runtime\_dir> run the about command.

## Install patches and service packs in a multi-node, multiple host environment

This section describes the procedure to apply a patch or service pack on a multi-node architecture based on *N* hosts. You update a Transfer CFT multi-node architecture with multi-hosts using the same procedure as for a patch or service pack, one host at a time.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"><span>Transfer CFT</span> clusters can still run while performing an update.         </td>
      </tr>
   </tbody>
</table>

1.  Connect to the first host.
2.  Stop all nodes running on this host by running the command: copstop  
    Copilot services are stopped, and local nodes are automatically re-started on the other hosts.
3.  Check that the nodes are re-started by using the command: CFTUTIL listnode
4.  Install the patch or the service pack as usual using Transfer CFT installer as described in [Install a standard update](#Install).
5.  Start Copilot services.
6.  Connect to the next host and repeat the procedure starting at of Step 2 (above).
