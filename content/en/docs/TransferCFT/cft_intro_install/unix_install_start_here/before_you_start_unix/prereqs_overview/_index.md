{
    "title": "1. Prerequisites ",
    "linkTitle": "1. Prerequisites ",
    "weight": "130"
}## Overview

Axway products are delivered electronically from Sphere, the Axway support website. A welcome letter notifies you that your products are ready for download.

To install you will perform the following tasks:

1.  Check your license key and authorization.
2.  Check the hardware and system requirements.
3.  Download product.
4.  Install products.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you have a 32-bit Transfer CFT installed, the Transfer CFT installer will update this to a 64-bit installation during a version <span>3.9</span> upgrade or migration.         </td>
      </tr>
</table>

## License keys

Before installing or upgrading, make sure you have obtained a license for Transfer CFT. Check that the license key is correct for the features and operating system you intend to install. It is not mandatory to enter the license key during the Transfer CFT installation, but you do require a key to start the product.

For information on applying a license key post installation, or if you have a problem with your license key, refer to the appropriate Troubleshooting topic.

-   [UNIX: Applying a license key](../../troubleshoot_registration/t_license_key_unix)

### Multi-node license keys

Transfer CFT in multi-node architecture requires a shared file system for use of a multi-node architecture on several hosts (active/active). Additionally, the system must be configured prior to the multi-node installation and the shared disk ready when starting the Copilot server.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">See <a href="../../../windows_install_start_here/before_you_start_win/n_active_active/shared_file_prereq_win" xrefformat="{paratext}">Shared file system prerequisites</a> for details.         </td>
      </tr>
</table>

You can use a single key for a multi-node installation, as either:

-   The hostname must not be defined for the key, or
-   The hostname defined for the key matches the hostname of one of the hosts that composes the multi-node instance

Additionally, the key must have the cluster option.

## Check your authorization

Verify that you can access Axway Support at [support.axway.com](https://support.axway.com/) and log in. If you do not have an account, follow the instructions in your welcome letter.

Log in to download or access:

-   The product installation package
-   Your product license key
-   Product documentation
-   Product updates, including patches and service packs
-   Product announcements
-   Axway Supported Platforms Guide
-   The case center, to open a new case or to track opened cases

You can also access other resources, such as articles in the Knowledge Base, the Axway User Forum, and documentation for all Axway products.
