{
    "title": "Working with Virtual File Directories",
    "linkTitle": "Working with VFDs",
    "weight": "130"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[Creating a new VFD](#Creating_a_new_VFD)

[Viewing VFD properties](#Viewing_VFD_properties)

[Modifying VFD properties](#Modifying_VFD_properties)

[Deleting a VFD](#Deleting_a_VFD)

[Renaming a VFD](#Renaming_a_VFD)

[Mounting a VFD](#Mounting_a_VFD)

[Unmounting a VFD](#Unmounting_a_VFD)

<span id="Creating_a_new_VFD"></span>

## Creating a new VFD

To create a new VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click <span style="font-weight: bold;">VFD</span>, and then select <span style="font-weight: bold;">New</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New Virtual File Directory</span> window.
3.  Complete the fields of the <span style="font-style: italic;">New Virtual File Directory</span> window:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Field</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PathName</p>         </td>
         <td><p>When you create a new directory, Gateway automatically completes the path name field with the path of the parent directory. The absolute path of the root directory is "<span class="code">/</span>".</p>
<p>The total length of this parameter is limited to 255 characters (or slightly lower in some cases). Individual directory nodes in the path are limited to 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Name</p>         </td>
         <td><p>Enter the name of the directory.</p>
<p>Maximum: 255 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Alias</p>         </td>
         <td><p>Optional</p>
<p>Enter a VFD directory alias. Use the alias to designate a specific directory within the VFD, regardless of whether it was moved or renamed. You can either reference the VFD via the alias name or via the path name.</p>
<p>The value that you enter in this field must be unique in the whole VFD.<br />
Maximum: 24 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Comments</p>         </td>
         <td><p>Enter a free-text description of the directory.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Monitoring</p>         </td>
         <td><p>Only used in RFD mode.</p>
<p>Check this option to record Transfer operations on this directory in the Gateway Mailbox.</p>         </td>
      </tr>
      <tr>
         <td><p>Mount name</p>         </td>
         <td><p>Enter the absolute path of the physical directory to be mounted.<br />
</p>
<p>The total length of this parameter is limited to 255 characters. Individual directory nodes in the path are limited to 127 characters.</p>         </td>
      </tr>
      <tr>
         <td><p>User data</p>         </td>
         <td><p>Enter a user message associated with the current VFD Item.<br />
Maximum: 80 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>File name display option</p>         </td>
         <td><p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Gateway specific</span>: Display VFD file names in the format: <span class="code">s.XferIdent.filename</span></li>
<li><span style="font-weight: bold;">Standard</span>: Display the VFD file name only</li>
</ul>
<p>Refer to <a href="../#VFD_file_name_display_option">VFD file name display option</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>File name duplication policy</p>         </td>
         <td><p>Only available if <span style="font-weight: bold;">File name display option</span> is set to <span style="font-style: italic;">Standard</span>.</p>
<p>Select one of the following:</p>
<ul>
<li><span style="font-weight: bold;">Duplicate</span>: Allow duplicate file names</li>
<li><span style="font-weight: bold;">Forbid</span>: Forbid duplicate file names. If the file name already exists, the new transfer request is not accepted.</li>
<li><span style="font-weight: bold;">Override</span>: Override the old file name. If the file name already exists, the old transfer is canceled and the new one is added.</li>
</ul>
<p>Refer to <a href="../#VFD_file_name_duplication_policy">VFD file name duplication policy</a>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Viewing_VFD_properties"></span>

## Viewing VFD properties

To view the properties of an existing VFD in a read-only window:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  When you click a VFD, in the right frame Gateway displays any sub-directories that comprise that VFD.
4.  In the right frame, right-click the VFD for which you want to view the properties. Then select <span style="font-weight: bold;">View...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">VFD Directory</span> window, containing a read-only display of the VFD properties.
5.  After viewing the VFD properties, click <span style="font-weight: bold;">Close...</span>.

<span id="Modifying_VFD_properties"></span>

## Modifying VFD properties

To modify the properties of an existing VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  Right-click the VFD you for which you want to modify the properties, then select <span style="font-weight: bold;">Properties...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">VFD Properties</span> window. This window contains the same fields as the <span style="font-style: italic;">New Virtual File Directory</span> window described above. The properties that you cannot modify in this window are grayed out.
4.  Modify the VFD properties as required.
5.  Select <span style="font-weight: bold;">OK</span> to confirm and complete the modification procedure.
6.  To refresh the display and view the changes, press <span style="font-weight: bold;">F5</span>.

<span id="Deleting_a_VFD"></span>

## Deleting a VFD

To delete an existing VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  Right-click the VFD node you want to delete. Then select <span style="font-weight: bold;">Delete...</span> from the context menu.  
    Gateway displays a confirmation dialog box.  
    <span style="font-weight: bold;">Note:</span> You cannot delete a VFD node that contains any sub-directories. To delete a node or a directory that contains sub-directories, first delete all directories it contains.
4.  In the confirmation dialog box, select <span style="font-weight: bold;">OK</span> to confirm and complete the delete process.  
    Alternately, select <span style="font-weight: bold;">NO</span> or <span style="font-weight: bold;">Cancel</span> to abandon the process without deleting the selected directory.  
    When you select <span style="font-weight: bold;">OK</span>, Gateway deletes the selected VFD and updates the display to take into account the change.

<span id="Renaming_a_VFD"></span>

## Renaming a VFD

To rename an existing VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  When you click a VFD in the left frame, in the right frame Gateway displays any sub-directories that comprise that VFD.
4.  In the right frame, right-click the VFD that you want to rename. Then select <span style="font-weight: bold;">Rename...</span> from the context menu.  
    Gateway highlights the current name of the VFD in an editable text frame.
5.  Enter a new name for the VFD, and then click outside of the text frame, anywhere in the Gateway main window.  
    Gateway updates the displayed name of the VFD.

<span id="Mounting_a_VFD"></span>

## Mounting a VFD

When you <span style="font-style: italic;">mount a VFD</span>, you link it to a Real File Directory.

To mount an existing VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  When you click a VFD in the left frame, in the right frame Gateway displays any sub-directories that comprise that VFD.
4.  In the right frame, right-click the VFD that you want to mount. Then select <span style="font-weight: bold;">Mount...</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">VFD mount directory</span> window.
5.  In the <span style="font-weight: bold;">Directory</span> frame, enter the path to the Real File Directory you want to link to your VFD.
6.  Select <span style="font-weight: bold;">OK</span> to confirm and complete the mount procedure.  
    Gateway mounts the VFD. In the right frame, the icon accompanying the VFD entry contains a yellow square to indicate that the VFD is mounted.

<span id="Unmounting_a_VFD"></span>

## Unmounting a VFD

A <span style="font-style: italic;">mounted VFD</span> is a VFD that is linked to a Real File Directory.

To unmount a mounted VFD:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  At the <span style="font-weight: bold;">VFD</span> node, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand and display the existing VFD structure.
3.  When you click a VFD in the left frame, in the right frame Gateway displays any sub-directories that comprise that VFD.
4.  In the right frame, right-click the VFD that you want to mount. Then select <span style="font-weight: bold;">Unmount...</span> from the context menu.  
    Gateway unmounts the VFD.

Related topics

[Overview: Virtual File Directories](../../../ov_gateway/ov_vfd)

[About Virtual File Directories](../)

[Working with Virtual File Directories (command line)](../working_with_vfds_cli)

[Virtual File Directories: Parameters List](../working_with_vfds_cli/vfd_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
