{
    "title": "Update Transfer CFT",
    "linkTitle": "Update Transfer CFT",
    "weight": "180"
}This section describes how to update Transfer CFT with a patch or service pack. You can manually perform the operation or use Central Governance.

## Download the update file

Download product updates from the [Axway support website](https://support.axway.com/) to the machine you where you want to perform the update. Please note that the update file is a zip file. Do not unzip this file.

## Impacted directories when updating a product

When you install a service pack, the contents of the home directory are updated, but the runtime directory remains untouched. This is so that your customizations, such as APIs, are not overwritten.

## Use Central Governance for updates

You can easily perform Transfer CFT updates using Central Governance as of Transfer CFT 3.1.3. Refer to the Central Governance documentation for details.

Limitations:

-   You cannot remove SP or patches via the Central Governance interface.
-   You cannot update Transfer CFTs installed in multi-node/multi-hosts from Central Governance.

## Windows users

The same user that did the initial installation (or at least the same type of user) must start the update procedure. Additionally, if you install a service pack or patch for the installer, make sure all Windows services created by the installer are stopped.

#### Services modification

Some products support an installation in service mode with a user other than the default (Local System Account).

If the domain field is not shown in the products service configuration dialog, then it must be introduced in the username field, using this format:

&lt;domain>\\&lt;username>

If it is a local user (a user that was created on the local machine) then the &lt;domain> field can be . or the &lt;hostname>.

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p> Local user: user1</p>
            <p>.\user1</p>
            <p>&lt;hostname&gt;\user1</p>
            <p> Network user: user2</p>
            <p>&lt;domain_name&gt;\user2</p>
         </td>
      </tr>
   </tbody>
</table>

## Install a standard update

Stop Transfer CFT prior to installing a service pack or patch.

### Update in silent mode

Use the following command to update Transfer CFT in silent mode:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>C:\axway\Transfer_CFT_<span>3.9</span>_&lt;Install\SP\Patch&gt;_&lt;OS&gt;_&lt;BN&gt;.exe --mode unattended --installdir &lt;installation_directory&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

## Uninstall an update

This section describes uninstalling a patch or service pack.

To uninstall install the previous patch or service pack. For example, to remove Transfer CFT 3.4 SP2, from the Transfer CFT 3.4 SP1 kit, run the installation pointing to the Transfer CFT 3.4 SP2 installation directory. The installer detects and replaces the SP2 content, impacting only the home directory.

**Example**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>C:\axway\Transfer_CFT_<span>3.9</span>_SP1_&lt;OS&gt;_&lt;BN&gt;.exe --mode  unattended </p>
         </td>
      </tr>
   </tbody>
</table>

To verify, from the Transfer CFT &lt;runtime\_dir> run the about command.

## Install patches and service packs in a multi-node, multi-host environment

This section describes the procedure to apply a patch or service pack on a multi-node architecture based on *N* hosts. You update a Transfer CFT multi-node architecture with multi-hosts using the same procedure as for a patch or service pack, one host at a time.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>Transfer CFT</span> clusters can still run while performing an update.         </td>
      </tr>
</table>

1.  Connect to the first host.
2.  Stop all nodes running on this host by running the command: copstop  
    Copilot services are stopped, and local nodes are automatically re-started on the other hosts.
3.  Check that the nodes are re-started by using the command: CFTUTIL listnode
4.  Install the patch or the service pack as usual using Transfer CFT installer as described in [Install a standard update](#install).
5.  Start Copilot services.
6.  Connect to the next host and repeat the procedure starting as of Step 2 (above).
