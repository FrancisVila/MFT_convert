{
    "title": "Host system security",
    "linkTitle": "Host system security",
    "weight": "100"
}## Host system security

Gateway provides complete protection for the host system via:

-   **Virtual File Directory** - the VFD has two operating modes that you can run separately or simultaneously:

    -   **VFD** (Virtual File Directory) mode: The VFD is a logical representation of directories and files (VFD Files). The logical files in the VFD represent a duplication of a given Transfer Request extract in the Gateway Mailbox. From the Gateway client side (FTP, SFTP or HTTP clients), you can view the logical representation of these files, but cannot directly access them.
    -   **RFD** (Real File Directory) mode: You can use a mount mechanism to link the logical file system (VFD) to the physical file system (RFD) on the Gateway host machine. The files seen from the client side are then real files that are located on the Gateway host machine. These files are optionally associated with a Gateway Mailbox Transfer.

    Files in RFDs must be protected by the host administrator using proper access rights at the operating system level.

    Partner access rights to VFD and RFD files and directories are configured in Gateway via CGate/CGateGroup and SGate/SGateGroup objects.

-   **Database encryption**

    You can use AES (Advanced Encryption Standard) encryption mechanisms to store Gateway administration objects and/or the Mailbox file securely on the host machine. Only users with specific rights can read, modify, or delete files. This encryption mechanism prevents external attacks. No one can access data that could enable them to bypass the Gateway authentication process.

-   **Temporary file encryption**

    To route files, Gateway must make a local copy of the files before routing them. Gateway uses temporary file encryption to protect the files it temporarily stores from malicious attacks. This is particularly important when you deploy Gateway in a DMZ. In a DMZ deployment, you should take the additional precaution of encrypting the Gateway Mailbox.

    The key used for temporary file encryption is an AES key generated on the spot for each file received. The generated key is attached to the transfer entry in the mailbox and it is recovered when we need to recover the file. The mailbox can be also AES128 encrypted (but it is not by default) by activating the mailbox database encryption option.

    When you route files using Gateway and temporary file encryption, you must link the input transfer to the output transfer using the combination of a Decision Rule (to identify the incoming transfer) and an applied Model (to specify the outgoing transfer characteristics).

    This enables Gateway to identify the security key necessary to read the deposited ciphered file in order to process it for the subsequent transfer.

-   **User Access Control of Gateway objects**

    User Access Control applies to all methods of accessing Gateway objects: via the Gateway GUI, command lines, APIs or the Axway MFT Navigator.

    The User and Profile objects in Gateway enable you to define user identification and access rights. Typically only Administrators have access to these objects. The User object defines properties for each user and the Profile object defines the type of operations a set of users can perform on each Gateway object.

    For detailed implementation information please refer to <a href="../" class="MCXref xref">Security features</a>

 

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
