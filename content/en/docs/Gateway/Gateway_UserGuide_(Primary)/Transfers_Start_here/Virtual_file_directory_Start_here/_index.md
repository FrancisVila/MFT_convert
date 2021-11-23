{
    "title": "Virtual directories",
    "linkTitle": "Virtual File Directories",
    "weight": "120"
}{{< Gateway/componentlongname  >}}: Managing Transfers

## About Virtual File Directories

[About the Virtual File Directory](#About_the_Virtual_File_Directory)

[VFD running modes](#VFD_running_modes)

[Virtual File Directory tree](#Virtual_directory_tree)

[Mounted directories](#Mounted_directories)

[Real File Directory tree](#Real_File_Directory_tree)

[VFD name length limitations](#name_limitation)

<a href="#max_listing" class="MCXref xref">VFD concurrent listing</a>

Related topics

[Working with Virtual File Directories](working_with_virtual_file_directories_(gui))

<span id="About_the_Virtual_File_Directory"></span>

### About the Virtual File Directory

Gateway can act as a file server for FTP, SFTP or HTTP transfers. You can use *Virtual File Directories* to control the views that users have from client machines of files stored on Gateway.

The Virtual File Directory (VFD) is a virtual device that enables you to provide an administrator-controlled view of data organization to specific users via a file directory tree. The VFD comprises directories and files.

When you start Gateway for the first time, it creates a root directory automatically. All new directories that you create subsequently belong to the root directory and can contain sub-directories or files.

You can only use the VFD:

-   In Responder mode
-   With [FTP](../../protocols_about/ftp_about), [SFTP](../../protocols_about/sftp_about) and [HTTP](../../protocols_about/http_about) file transfer protocols, where file organization in directories is meaningful

**Note:** This topic describes the VFD, but does not describe how to assign VFD access via CGate and CGateGroup objects. Refer to [CGates: Transfer phase](../../managing_partners_start_here/cgates_start_here/cgates_transfer_phase).

<span id="VFD_running_modes"></span>

### VFD running modes

The VFD has two operating modes that you can run separately or simultaneously:

-   <span style="font-weight: bold;">VFD (Virtual File Directory) mode:</span> The VFD is a logical representation of directories and files (<span style="font-weight: bold;font-style: italic;">VFD Files</span>). The logical files in the VFD represent a duplication of a given Transfer Request extract in the Gateway Mailbox. From the Gateway client side (FTP, SFTP or HTTP clients), you can view the logical representation of these files, but cannot directly access them.
-   <span style="font-weight: bold;">RFD (Real File Directory) mode:</span> You can use a mount mechanism to link the logical file system (VFD) to the physical file system (RFD) on the Gateway host machine. The files seen from the client side are then <span style="font-style: italic;">real</span> files that are located on the Gateway host machine. These files are optionally associated with a Gateway Mailbox Transfer.

<span id="Directory_contents"></span>

#### Directory contents

The contents of a VFD directory depend on its associated running mode.

-   Logical directories contain:
    -   Logical sub-directories
    -   VFD Items (files)
    -   Mounted sub-directories (that point to a real directory tree)
-   Real directories and mounted directories contain:
    -   Real sub-directories
    -   Real files

<span style="font-weight: bold;">Note:</span> You can define the root directory as a mount point, but in this case it cannot contain any logical objects (file or directory).

The following diagram illustrates the Virtual File Directory tree.

<img src="/Images/Gateway/VFD_DirectoryTree.png" class="maxWidth" />

<span id="Virtual_directory_tree"></span>

### Virtual File Directory tree

In virtual mode, directories and files are logical representations of real directories and files.

<span id="Virtual_directories"></span>

#### Virtual directories

From an FTP, SFTP or HTTP client view, the Gateway virtual directory tree works in the same way as any other directory tree provided by standard FTP, SFTP or HTTP servers. Virtual directories can contain sub-directories (virtual and mounted) and VFD Items. Virtual directories have the following attributes:

-   Comment field
-   Alias (a unique identifier independent of the directory location)
-   User attribute (provided to the Gateway exits during the transfer phase)

<span id="VFD_Files"></span>

#### VFD files

A VFD file is a duplicate extract of a Gateway Mailbox record that is directly linked to a Transfer Request. Since VFD files are only meaningful within Gateway, you can only modify them via Gateway. From a client view, a VFD file is a file that is linked to a record in the Gateway Mailbox. Its availability to a client depends on its:

-   Protocol attributes (protocol, origin, destination, and so on)
-   Direction (OUT)

The logical part of the VFD is updated depending on Gateway Mailbox modifications (VFD Item creation, update, deletion, and so on).

> **Note:**
>
> For security concerns, the way that the put-at-disposal transfers are listed is limited for the specified user (by Remote Site), or group of users (by Template Site). It is no longer possible to have a login with a physical remote site and list the put-at-disposal transfers for a Template remote site, such as TSFTP.

<span id="Downloading_VFD_files"></span>

#### Downloading VFD files

You can download a VFD file from a directory if:

-   The VFD file exists in the directory (VFD file created via a Transfer Request)
-   The corresponding Gateway Mailbox Transfer direction is <span class="code">OUT</span> and its state is <span class="code">TO\_BEGIN</span>
-   The protocol parameters of the associated Gateway Mailbox record match those of the connected client

When the file transfer is terminated, the Gateway Mailbox state becomes ENDED and the file is no longer available for download by any other client. To make a file transfer available on a permanent basis for multiple client downloads, set the Transfer permanent flag to <span style="font-weight: bold;">YES</span>.

<span id="Uploading_VFD_files"></span>

#### Uploading VFD files

When Gateway receives a file upload request, it checks that the reception directory exists, confirms that the user is authorized to write to the directory, and creates a record in the Mailbox. When Gateway updates the Mailbox, it creates a new VFD file in the corresponding directory. When the reception directory is virtual, this file is not available for any other client because no outgoing request is posted to make this download possible.

<span id="VFD_naming_conventions"></span>

#### VFD naming conventions

The virtual part of the VFD is referenced using the UNIX path syntax. The absolute path of a VFD Item (or a virtual directory) is the concatenation of its parent directory names separated by a "<span class="code">/</span>" character, followed by the name of the current VFD Item (or directory).

In the following diagram, the VFD absolute path for the <span class="code">upload</span> directory is: <span class="code">/user1/upload</span>.

<img src="/Images/Gateway/VFD_AbsolutePath.png" class="mediumWidth" />

<span id="VFD_file_name_display_option"></span>

#### VFD file name display option

For FTP and SFTP you can determine how to display the file name for each VFD. You can choose one of the following options:

-   s.XferIdent.filename (default)
-   File name only

<span id="VFD_file_name_duplication_policy"></span>

#### VFD file name duplication policy

If you set the [VFD file name display option](#VFD_file_name_display_option) to <span style="font-style: italic;">file name only</span>, you also need to tell Gateway how to manage duplicate file names.

For FTP, HTTP and SFTP you can determine how to manage duplicate file names for each VFD. You can choose one of the following options:

-   <span style="font-weight: bold;">allow</span> duplicate file names (default)
-   <span style="font-weight: bold;">forbid</span> duplicate file names. A new transfer request is refused if the file name already exists in the same virtual directory.
-   <span style="font-weight: bold;">override</span> an existing transfer request with a newer one if the file name already exists in the same virtual directory. However, if the old transfer cannot be canceled (update failed), the new request is rejected.

<span id="Mounted_directories"></span>

### Mounted directories

A mounted directory is a virtual directory that serves as a logical link between the virtual directory tree and the physical file system on the Gateway host machine. Mounted directories have all the same attributes as virtual directories. In addition, mounted directories include a Mailbox recording option. This option enables you to specify whether or not to record all operations on the mounted directory in the Gateway Mailbox.

The mounted directory points to a <span style="font-style: italic;">real</span> sub-directory via the absolute path of the directory on the physical file system.

##### Mounted directory contents

If the physical directory <span class="code">C:\\Temp</span> contains the files <span class="code">meeting.txt</span> and <span class="code">meeting.ppt</span>, then from a client connected to Gateway, the <span class="code">/download</span> directory also contains the two files <span class="code">meeting.txt</span> and <span class="code">meeting.ppt</span>.

<img src="/Images/Gateway/VFD_Mount.png" class="mediumWidth" />

<span id="Real_File_Directory_tree"></span>

### Real File Directory tree

In <span style="font-weight: bold;">RFD</span> Real File Directory) mode, both directories and files are real and are located in the physical file system on the Gateway host machine. You can only manage these files via the corresponding operating system tools (copy, and so on). The RFD mechanism enables you to:

-   Integrate the generic data presentation of most FTP, SFTP and HTTP servers into Gateway
-   Optionally, use the file transfer phase tracing process

Gateway uses the RFD to provide the client with the image of the directory tree, based on the current state of the directory on the Gateway host machine.

The Gateway administrator must:

-   Manually create the required directory tree on the Gateway host machine
-   Link it with the VFD using a mount point

<span id="Real_directories"></span>

#### Real directories

RFD directories are not represented internally in Gateway. Since these directories are part of the local file system, you cannot manage them using Gateway tools. An RFD directory inherits its attributes from the logical mounted directory that points to the current directory.

Real directories can contain real sub-directories and real files.

<span id="Real_files"></span>

#### Real files

From an FTP, SFTP or HTTP client view, a real file is presented as if it were directly accessible on the Gateway host machine. The transfer phase mechanisms for a real file depend on the value of the <span class="code">mbx\_recording</span> (<span style="font-weight: bold;">Monitoring</span>) attribute of its parent directory. This value is inherited from the associated VFD mounted directory.

When you create the VFD, if you set the <span class="code">mbx\_recording</span> parameter to:

-   YES: the download or upload request dynamically creates a Mailbox record that Gateway updates during the data transfer phase
-   NO: Gateway does not create a record in the Mailbox and transfers data directly

Files that you upload to or download from the Gateway host machine remain available for subsequent operations:

-   Downloaded files are opened in read only mode and remain unchanged on the Gateway host machine
-   Uploaded files are physically written to the Gateway host machine file system

<span id="RFD_naming_conventions"></span>

#### RFD naming conventions

RFD file and directory naming conventions are as follows:

-   The beginning of the absolute file path, up to the mount point, is built as described in [VFD naming conventions](#VFD_naming_conventions).
-   The end of the absolute path comprises the relative path from the mount point to the designated object (the sub-directory names are separated by the "<span class="code">/</span>" character regardless of the local operating system: UNIX or Windows).

#### VFD real directory absolute path

<img src="/Images/Gateway/VFD_RealDirectory.png" class="mediumWidth" />

The physical directory <span class="code">C:\\users\\upload\\http</span> is referenced in the VFD using the following absolute path: <span class="code">/mydir/upload/http</span>, where:

-   <span class="code">/mydir</span> is the VFD absolute path up to the mount point
-   <span class="code">/upload/http</span> is the relative path from the mount point (sub-directory names are separated by "<span class="code">/</span>")

<span id="name_limitation"></span>

### VFD name length limitations

All objects in the VFD are subjected to name length limitations. Individual directory names and file names are restricted to 127 characters, while the maximum length of a directory path is 255 characters.

As such, it is not possible to create a virtual directory node with a name longer than 127 characters, or in such a way that the absolute path of the new directory is longer than 255 characters.

Mounted RFD directories, subdirectories and files that exceed these limitations will not be handled correctly by the VFD mechanism. They will not appear in the Navigator view or in the output of the <span class="code" style="font-weight: bold;">vfddsp list\_dir</span> command. Furthermore they will not be made available to clients connecting to Gateway.

As an exception, Mailbox entries (as opposed to RFD mapped files) have a file name length limit of 255 characters inherited from the transfer properties.

<span id="max_listing"></span>

### VFD concurrent listing

You can set a limit to the number of concurrent listings for each protocol, using the `max_listings `parameter. This parameter can be controlled using the `peluconf `command:

peluconf set -s ft\_ftp max\_listing xxx

(values from 0 to 999, where 0 means "no limit" )

This parameter is available for the following protocols: FTP, HTTP, SFTP, AS2, AS3, RN\_HTTP.

Related topics

[Overview: Virtual File Directories](../../ov_gateway/ov_vfd)

[Working with Virtual File Directories](working_with_virtual_file_directories_(gui))

[Working with Virtual File Directories (command line)](working_with_vfds_cli)

[Virtual File Directories: Parameters List](working_with_vfds_cli/vfd_parameter_list)

[Working with File Transfer Requests](../submitting_transfer_requests_start_here/working_with_transfers_(gui)#Submitting_a_Transfer_Request)

[Transfers: Parameters List](../submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
