{
    "title": "Virtual File Directories",
    "linkTitle": "Virtual File Directories",
    "weight": "110"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Overview

Gateway can act as a file server for FTP, SFTP or HTTP transfers. As a server, Gateway securely stores the physical files it receives, away from direct viewing by users. Gateway administrators can control the views that users have of files from client machines. For individual users, you can create virtual views of the system of stored files, while keeping the real contents inaccessible.

This user-adapted view of the file system is known as a <span style="font-style: italic;">Virtual File Directory (VFD)</span>. A VFD appears in the GUI to users with the appropriate rights. Users to whom you have granted VFD rights can access only the set of directories that you organize for their use. Users are unaware of any directories and files that are not expressly intended for their viewing.

Gateway creates the file contents of VFDs from the contents of Transfer Request records contained in the Mailbox. Unless you select a mounting option, the virtual files represented in the VFD do not link to real files stored on the Gateway host machine.

You can set restrictions to user actions within the directories. You can specify:

-   The type of file to which users have access
-   The type of operations users can perform on VFD directories:
    -   List
    -   Create
    -   Remove
-   The type of operations users can perform on VFD files:
    -   Read
    -   Delete
    -   Write

## Example

You can create a VFD to handle the file deposits and requests of FTP clients connecting from Agency A, Agency B and Agency C. You can create an individual VFD for each agency so each agency has a view only of the file directories with which it is concerned.

Your administrator view of the complete VFD directory structure might appear as follows:

<img src="/Images/Gateway/VFDadmin.gif" width="232" height="465" />

 

You can manage the FTP access to the VFD for each Agency. For example, you might restrict the Agency B access so that when the agency connects the Gateway with an FTP client, the agency view of the directory structure appears as follows.

<img src="/Images/Gateway/VFDclientview2.gif" width="166" height="162" />

[Next topic](../ov_trading_partners)

Related topics

[About Virtual File Directories](../../transfers_start_here/virtual_file_directory_start_here)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
