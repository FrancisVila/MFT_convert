{
    "title": "1. Prerequisites",
    "linkTitle": "1. Prerequisites",
    "weight": "140"
}Axway products are delivered electronically from Sphere, the Axway support website. A welcome letter notifies you that your products are ready for download.

To install you will perform the following tasks:

1.  Check your license key and authorization.
2.  Check the hardware and system requirements.
3.  Download product.
4.  Install products.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"><span>Transfer CFT</span> 3.7 is available as a 64-bit installation. If you are using and existing 32-bit <span>Transfer CFT</span>, you can use the Transfer CFT 3.7 install kit to move from the existing version to Transfer CFT 3.7 64-bit.</td>
</tr>
</tbody>
</table>

## License keys

Before installing or upgrading, make sure you have obtained a license for Transfer CFT. Check that the license key is correct for the features and operating system you intend to install. It is not mandatory to enter the license key during the Transfer CFT installation, but you do require a key to start the product.

For information on applying a license key post installation, or if you have a problem with your license key, refer to the appropriate Troubleshooting topic.

-   [Windows: Applying a license key](../../troubleshoot_registration/license_key_win)
     

### Multi-node license keys

Transfer CFT in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">See <a href="../n_active_active/shared_file_prereq_win">Shared file system prerequisites</a> for details.</td>
</tr>
</tbody>
</table>

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

Transfer CFT in a multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation, and the shared disk ready when starting the Copilot server.

-   *Windows only*: You must map the shared disk to a drive letter.
-   *Windows only*: The Copilot Service Mode cannot be started as the LocalSystem account.
-   *Windows only*: If you are running Copilot in Service Mode, you must set up a dependency with the shared disk's service for multi-node.

## End User License Agreement

You should read and accept the End User License Agreement (EULA) prior to installing Transfer CFT. The EULA file is in the directory where you decompressed the Transfer CFT package.

## Check your authorization

Verify that you can access Axway support at [support.axway.com](https://support.axway.com/) and log in. If you do not have an account, follow the instructions in your welcome letter.

Log in to download or access:

-   The product installation package
-   Your product license key
-   Product documentation
-   Product updates, including patches and service packs
-   Product announcements
-   Axway Supported Platforms Guide
-   The case center, to open a new case or to track opened cases

You can also access other resources, such as articles in the Knowledge Base, the Axway User Forum, and documentation for all Axway products.
