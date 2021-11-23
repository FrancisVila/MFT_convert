{
    "title": "Working with Virtual File Directories (command line)",
    "linkTitle": "Command line operations",
    "weight": "150"
}{{< Gateway/componentlongname  >}}: Managing Transfers

Managing VFD directories:

-   `vfdadm create_dir`
-   `vfdadm update_dir`
-   `vfdadm move_dir`
-   `vfdadm delete_dir`
-   `vfddsp display_dir`
-   `vfddsp list_dir`

Managing VFD files:

-   `vfddsp display_file`

Exporting and Importing VFDs:

-   `vfdbase export`
-   `vfdbase import`

<span id="Managing_VFD_directories"></span>

## Managing VFD directories

This section describes the Gateway commands you can use to manage VFD directories.

<span id="vfdadm_create_dir"></span>

### Creating a directory: vfdadm create\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><code>vfdadm create_dir {-dir_path}</code> [optional parameters - see parameters list below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to create a new directory and set its attributes. The directory that you create can be either a virtual directory or a mounted directory. A mounted directory is associated with a real directory located in the Gateway host File System.</p>
<p>The absolute path of the directory that you create is a <strong>mandatory</strong> parameter.</p>
<p><span style="font-weight: bold;">Do not create the VFD root directory manually</span>. Gateway automatically creates the root directory when you access the VFD for the first time. The absolute path of the root directory is: "<span class="code">/</span>".</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory you are creating.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter a name for the directory, unique for the whole VFD.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a comment about the VFD directory.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mount_point (-mp)</span>: Enter a value to determine whether or not to mount the current directory:</p>
<ul>
<li><strong>Y</strong></li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mount_dir_path (-mdp)</span>: Enter the absolute path of the physical directory (RFD) to be mounted.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_attribute (-ua)</span>: Enter a user parameter associated with the current directory.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mbx_recording (-mr)</span>: In RFD mode only, enter the Gateway Mailbox recording option. This option indicates whether or not to trace the transfer operations on the current directory (downloading and uploading) in the Gateway Mailbox.</p>
<ul>
<li><strong>Y</strong></li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-filename_display_option (-fdo)</span>: Enter a value to indicate how file names are displayed:</p>
<ul>
<li><span style="font-weight: bold;">Standard</span> = only the file name is displayed</li>
<li><span style="font-weight: bold;">XFB</span> = the file name is displayed in the format: <span class="code">s.XferIdent.filename</span> (default)</li>
</ul>
<p>For more information, refer to <a href="../#VFD_file_name_display_option">VFD file name display option</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-filename_duplicate_policy (-fdp)</span>: Enter a value to indicate how duplicate file names are managed:</p>
<ul>
<li><strong>duplicate</strong> = duplicate file names are allowed (default)</li>
<li><strong>forbid</strong> = if the file name already exists, the new transfer request is not accepted</li>
<li><strong>override</strong> = if the file name already exists, the old transfer is canceled and the new one is added</li>
</ul>
<p>For more information, refer to <a href="../#VFD_file_name_duplication_policy">VFD file name duplication policy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command creates a virtual sub-directory of the "<span class="code">/</span>" directory (automatically created). Its VFD absolute path is <span class="code">/Download</span> and it does not have any associated aliases.</p>
<p>vfdadm create_dir</p>
<p>-dir_path "/Download"</p>
<p>-mount_point "N"</p>
<p>-comments "users default download directory"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfdadm_update_dir"></span>

### Modifying a directory: vfdadm update\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfdadm update_dir</strong></span> [optional parameters - see parameters list below]</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to update the attributes (including the optional mount point attributes) of an existing VFD directory. You can reference the directory to be updated either via its VFD absolute path or its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory that you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-new_alias (-na)</span>: Enter a new directory name for the updated directory.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-comments (-cts)</span>: Enter a comment about the VFD directory.</p>
<p>Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mount_point (-mp)</span>: Enter a value to determine whether or not to mount the current directory:</p>
<ul>
<li><strong>Y</strong></li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mount_dir_path (-mdp)</span>: Enter the absolute path of the physical directory (RFD) to be mounted.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-user_attribute (-ua)</span>: Enter a user parameter associated with the current directory.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-mbx_recording (-mr)</span>: In RFD mode only, enter the Gateway Mailbox recording option. This option indicates whether or not to trace the transfer operations on the current directory (downloading and uploading) in the Gateway Mailbox.</p>
<ul>
<li><strong>Y</strong></li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-filename_display_option (-fdo)</span>: Enter a value to indicate how file names are displayed:</p>
<ul>
<li><span style="font-weight: bold;">Standard</span> = only the file name is displayed</li>
<li><span style="font-weight: bold;">XFB</span> = the file name is displayed in the format: <span class="code">s.XferIdent.filename</span> (default)</li>
</ul>
<p>For more information, refer to <a href="../#VFD_file_name_display_option">VFD file name display option</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-filename_duplicate_policy (-fdp)</span>: Enter a value to indicate how duplicate file names are managed:</p>
<ul>
<li><strong>duplicate</strong> = duplicate file names are allowed (default)</li>
<li><strong>forbid</strong> = if the file name already exists, the new transfer request is not accepted</li>
<li><strong>override</strong> = if the file name already exists, the old transfer is canceled and the new one is added</li>
</ul>
<p>For more information, refer to <a href="../#VFD_file_name_duplication_policy">VFD file name duplication policy</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>The following command updates the VFD directory whose absolute path is <span class="code">/Download</span>. This directory is set as a mounted directory that points to the <span class="code">C:\temp</span> directory in the Gateway host file system.</p>
<p>vfdadm update_dir</p>
<p>-directory_path "/Download"</p>
<p>-mount_point "Y"</p>
<p>-mount_dir_path "C:\temp"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfdadm_move_dir"></span>

### Moving or renaming a directory: vfdadm move\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfdadm move_dir</strong> [-dir_path] [-alias] [-new_dir_path]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to:</p>
<ul>
<li>move a VFD directory (or mounted directory) from its current location in the VFD to a new location</li>
<li>rename a VFD directory</li>
<li>move and rename a VFD directory</li>
</ul>
<p>You can use this command on a directory that is empty or not.</p>
<p>Internally, a VFD directory is identified by an ID node which remains the same during the renaming or moving process. This means that when you move or rename a directory, the match between the directory alias and its new location is automatically taken into account.</p>
<p>The command either renames or moves the directory, depending on the new absolute path to the directory:</p>
<ul>
<li>If the parent directory of the current directory remains unchanged, the command only renames the directory.</li>
<li>Otherwise, the command moves the current directory to the specified location.</li>
</ul>
<p>In addition, when you move a virtual directory:</p>
<ul>
<li>If the destination directory already exists, the current directory becomes a sub-directory of the destination directory and its name remains the same.</li>
<li>If the destination directory does not exist, the current directory:
<ul>
<li>takes a new name (the last element of the specified new location path)</li>
<li>takes the absolute path that you specify</li>
</ul></li>
</ul>
<p>You can reference the directory to move or rename either by its VFD absolute path or by its alias.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory that you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-new_dir_path (-ndp)</span>: Enter the absolute path of the directory you want to modify.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 1</strong></p>         </td>
         <td><p>In this example, the <span class="code">/smith</span> directory does not already exist.</p>
<p>vfdadm move_dir</p>
<p>-dp "/upload"</p>
<p>-ndp "/smith"</p>
<p>The command renames the directory from <span class="code">upload</span> to <span class="code">smith</span>, but does not move the directory. The parent directory of the directory to move remains unchanged ("<span class="code">/</span>").</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 2</strong></p>         </td>
         <td><p>In this example, the <span class="code">/jones</span> directory already exists.</p>
<p>vfdadm move_dir</p>
<p>-dp "/upload"</p>
<p>-ndp "/jones"</p>
<p>The <span class="code">/upload</span> directory keeps its name but becomes a new sub-directory of the <span class="code">/jones</span> directory.</p>
<p>Its new VFD absolute path is now: <span class="code">/jones/upload</span>.</p>
<p><span style="font-weight: bold;">Note:</span> If a <span class="code">/jones/upload</span> directory already exists before you run the command, an error is returned.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example 3</strong></p>         </td>
         <td><p>In this example, the <span class="code">/users</span> directory exists but <span class="code">/users/smith</span> does not exist.</p>
<p>vfdadm move_dir</p>
<p>-dp "/upload"</p>
<p>-ndp "/users/smith"</p>
<p>The command:</p>
<ul>
<li>Renames the <span class="code">/upload</span> directory as <span class="code">/smith</span></li>
<li>Moves the renamed directory and makes it a sub-directory of <span class="code">/users</span></li>
</ul>         </td>
      </tr>
   </tbody>
</table>

<span id="vfdadm_delete_dir"></span>

### Deleting a logical directory: vfdadm delete\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfdadm delete_dir</strong> [-dir_path] [-alias]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to delete a VFD logical directory. You can only delete a directory if it is empty: it must not contain any sub-directories or VFD items.</p>
<p>You must enter a value for at least one of the two parameters.</p>
<p>Before you can delete a mounted directory, you must first set the parameters:</p>
<ul>
<li><span class="code" style="font-weight: bold;">mount_point</span> to N</li>
<li><span class="code" style="font-weight: bold;">mount_dir_path</span> to blank</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory that you want to delete.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>This command deletes a logical VFD directory whose absolute path is <span class="code">/Upload</span></p>
<p>vfdadm delete_dir</p>
<p>-directory_path "/Upload"</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfddsp_display_dir"></span>

### Displaying a logical directory: vfddsp display\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfddsp display_dir</strong> [-dir_path] [-alias]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the details, or attributes, of a VFD logical directory that is identified by its VFD absolute path or its alias.</p>
<p>You must enter at least one of the two parameters.</p>
<p>The command returns the VFD logical directory parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory for which you want to display details.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory for which you want to display details.</p>         </td>
      </tr>
      <tr>
         <td><p>Details for use</p>         </td>
         <td><p>Gateway returns a display of display of parameters and values in which each parameter is displayed on a separate line in the format:</p>
<p>name_of_field="value"</p>
<p>Each field name is prefixed with the string <span class="code" style="font-weight: bold;">vd_</span> (Virtual Directory).</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the following command:</p>
<p>vfddsp display_dir</p>
<p>-dp "/upload"</p>
<p>Gateway returns the following <span class="code">/upload</span> logical directory attributes:</p>
<p>vd_dir_path=/upload</p>
<p>vd_comments=Default user upload directory</p>
<p>vd_alias=UPLOAD</p>
<p>vd_user_attribute=</p>
<p>vd_mount_dir_path=</p>
<p>vd_mbx_recording=Y</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfddsp_list_dir"></span>

### Listing a logical directory: vfddsp list\_dir

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfddsp list_dir {-dir_path}</strong> [-alias] [-filter] [-no_dir] [-no_file]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to list the contents of the directory that you specify.</p>
<p>You must enter values for at least one of the two parameters:</p>
<ul>
<li><span class="code">-dir_path</span></li>
<li><span class="code">-alias</span></li>
</ul>
<p>This command supports filters to help you find the required data. These filters can comprise:</p>
<ul>
<li>A type filter (<span class="code" style="font-weight: bold;">no_dir</span> or <span class="code" style="font-weight: bold;">no_file</span>)</li>
<li>A name pattern (wildcard characters such as<span class="code"> ?</span> and<span class="code"> *</span> are allowed). The command only displays the elements whose names match the pattern.</li>
</ul>
<p><span style="font-weight: bold;">Note:</span> This command works with both logical and real directories.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory whose attributes you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory whose attributes you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-filter (-f)</span>: Enter a string. Gateway displays the inner components of the current VFD directory whose name matches the filter string.</p>
<p>This string can contain<span class="code"> ?</span> and<span class="code"> *</span> wildcard characters.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-no_dir (-nd)</span>: (<span style="font-style: italic;">takes no value</span>) Enter this parameter to indicate that sub-directories must not be displayed.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-no_file (-nf)</span>: (<span style="font-style: italic;">takes no value</span>) Enter this parameter to indicate that files must not be displayed.</p>         </td>
      </tr>
      <tr>
         <td><p>Details for use</p>         </td>
         <td><p>The screen displays the directory contents that match the selection criteria that you specify.</p>
<p>A value X means that the corresponding attribute is meaningless for the current object.</p>
<p>If expected directories or filenames do not appear in the output of the command, make sure that you have respected the <a href="../#name_limitation">VFD name length limitations</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>See the following examples.</p>         </td>
      </tr>
   </tbody>
</table>

#### Example 1

The following example of the <span class="code" style="font-weight: bold;">vfddsp list</span> command displays the contents of the VFD <span class="code">/upload</span> directory without any selection criteria.

vfddsp list\_dir  -dp "/upload"

<table>
         
         
         
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Lid</p>         </td>
         <td><p>Filename</p>         </td>
         <td><p>T</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Xid</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Last Modif Date</p>         </td>
      </tr>
      <tr>
         <td><p>10</p>         </td>
         <td><p>FTP_B</p>         </td>
         <td><p>VF</p>         </td>
         <td><p>B</p>         </td>
         <td><p>10</p>         </td>
         <td><p>4</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>11</p>         </td>
         <td><p>FTP_B</p>         </td>
         <td><p>VF</p>         </td>
         <td><p>B</p>         </td>
         <td><p>11</p>         </td>
         <td><p>4</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>12</p>         </td>
         <td><p>FTP_B</p>         </td>
         <td><p>VF</p>         </td>
         <td><p>B</p>         </td>
         <td><p>12</p>         </td>
         <td><p>4</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>user1</p>         </td>
         <td><p>VD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>user2</p>         </td>
         <td><p>VD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>tmp</p>         </td>
         <td><p>MD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.48</p>         </td>
      </tr>
   </tbody>
</table>

#### Example 2

The following example displays the contents of the same <span class="code">/upload</span> directory, but in this case each element must be a directory (<span class="code">no\_file</span>).

vfddsp list\_dir  -dp "/upload"  -nf

<table>
         
         
         
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Lid</p>         </td>
         <td><p>Filename</p>         </td>
         <td><p>T</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Xid</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Last Modif Date</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>user1</p>         </td>
         <td><p>VD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>user2</p>         </td>
         <td><p>VD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.47</p>         </td>
      </tr>
      <tr>
         <td><p>X</p>         </td>
         <td><p>tmp</p>         </td>
         <td><p>MD</p>         </td>
         <td><p>X</p>         </td>
         <td><p>X</p>         </td>
         <td><p>0</p>         </td>
         <td><p>2006/10/24 16.48</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Managing_VFD_Files"></span>

## Managing VFD files

This section describes the operations allowed on VFD files. Gateway performs most of these operations automatically and internally. Operations that involve updating the Gateway Mailbox are not accessible to the end user, for example: creating, updating or deleting VFD files. VFD files are modified depending on updates to the Gateway Mailbox.

<span id="vfddsp_display_file"></span>

### Displaying a logical file (VFD file): vfddsp display\_file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfddsp display_file {-local_ident}</strong> [-dir_path] [-alias]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to display the details of a VFD logical file identified by its VFD parent directory absolute path (or its alias) and its name. The command returns the VFD logical file parameters.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>Mandatory</p>
<p><span class="code">-local_ident (-li)</span>: Local transfer identifier of the VFD file you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-dir_path (-dp)</span>: Enter the absolute path of the directory whose attributes you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-alias (-a)</span>: VFD directory alias.</p>
<p>Enter the name of the directory whose attributes you want to display.</p>         </td>
      </tr>
      <tr>
         <td><p>Details for use</p>         </td>
         <td><p>Each returned parameter is displayed on a separate line.</p>
<p>Each field name is prefixed with the string <span class="code" style="font-weight: bold;">vf_</span> (Virtual File).</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>vfddsp display_file  <span style="font-weight: bold;">-dp "/"  </span><span style="font-weight: bold;">-i 14</span></p>
<p>Gateway returns the attributes for the logical file <span class="code">14</span>. This file is located in the VFD "<span class="code">/</span>" directory:</p>
<p>vf_local_ident=14</p>
<p>vf_dir_path=/</p>
<p>vf_date_create=20070122 154603</p>
<p>vf_file_size=0</p>
<p>vf_protocol=HTTP</p>
<p>vf_access_right=---------</p>
<p>vf_direction=O</p>
<p>vf_state=C</p>
<p>vf_originator=GFL660</p>
<p>vf_destination=THTTP</p>
<p>vf_remote_agent=THTTP</p>
<p>vf_file_name=DEFAULT_B</p>
<p>vf_xfer_ident=14</p>
<p>vf_route_state=</p>
<p>vf_user_state=</p>
<p>vf_permanent=N</p>
<p>vf_appli=default_b</p>
<p>vf_param1=</p>
<p>vf_param2=</p>
<p>vf_user_msg=Dummy Message</p>
<p>vf_data_code=B</p>
<p>vf_route_from_xfer=0</p>
<p>vf_route_to_xfer=0</p>
<p>vf_duplicate_from_xfer=0</p>
<p>vf_type=0</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Exporting_and_Importing"></span>

## Exporting and Importing VFDs

This section describes Gateway commands you can use to move VFDs between Gateways.

<span id="vfdbase_export"></span>

### vfdbase export

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfdbase export {-output}</strong></span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>When Gateway is running, use this command to export Virtual File Directories (VFDs) to an output file. By default, the resulting file is created in the <span class="code">&lt;Gateway installation directory&gt;/run_time/tmp</span> directory. You can then edit the file and import the file to Gateway using the <span class="code" style="font-weight: bold;">vfdbase import</span> command.</p>
<p><strong>Note:</strong> During the export process, VFD items are lost.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-output (-f)</span>: Enter the name of the resulting file on your host machine.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the command:</p>
<p>vfdbase export  -f VFDMove</p>
<p>Gateway creates an output file named <span class="code">VFDMove</span> that contains descriptions of all VFD files on your Gateway:</p>
<p>[Overall]</p>
<p>Version      = 110</p>
<p>[Directory]</p>
<p>Type         = VIRTUAL_DIR</p>
<p>NodeIdent    = 1000</p>
<p>...</p>
<p>UserData     =</p>         </td>
      </tr>
   </tbody>
</table>

<span id="vfdbase_import"></span>

### vfdbase import

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code"><strong>vfdbase import {-input}</strong> [-discard_mount_points] [-directories] [-transfers] [-ignore_warnings]</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>Use this command to import the complete set of Virtual File Directories into the Gateway database. The VFDs are described in a file you created using the <span class="code" style="font-weight: bold;">vfdbase export</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p><span class="code">-input (-if)</span>: Enter the name of the file containing VFDs for import.</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-discard_mount_points (-dmp)</span>: Enter a value to indicate whether or not the mount points are to be discarded on import:</p>
<ul>
<li><strong>Y</strong> = Directories are virtual and do not direct to physical directories. In that case, you must mount them manually.</li>
<li><strong>N</strong> = Links are kept between directories (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-directories (dir)</span>: Enter a value to indicate whether or not the directory is to be imported:</p>
<ul>
<li><strong>Y</strong> (default)</li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-transfers (-tr)</span>: Enter a value to indicate whether or not you want Gateway to retrieve and import transfer records from the Mailbox:</p>
<ul>
<li><strong>Y</strong> (default)</li>
<li><strong>N</strong></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span class="code">-ignore_warnings (-iw)</span>: Enter a value to indicate whether or not you want to ignore warnings generated during the import process:</p>
<ul>
<li><strong>Y</strong></li>
<li><strong>N</strong> (default)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Details for use</p>         </td>
         <td><p>Before importing VFDs:</p>
<ol>
<li>Shut down the target Gateway.</li>
<li>On the target Gateway machine, manually delete the data files in the VFD library (<span class="code">p_runtime_dir/vfd</span>). If you do not do this, the import procedure will not succeed and the message "VFD files already exist, delete all files before importing" will be displayed.</li>
<li>Create a VFD output file on the originating Gateway, using the <span class="code" style="font-weight: bold;">vfdbase export</span> command.</li>
</ol>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter the following command (assuming the file containing the importable VFDs is named <span class="code">VFDMove</span>):</p>
<p><strong>vfdbase import  -if VFDMove</strong></p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Overview: Virtual File Directories](../../../ov_gateway/ov_vfd)

[Virtual File Directories: Parameters List](vfd_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
