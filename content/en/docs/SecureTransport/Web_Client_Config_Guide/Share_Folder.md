{
    "title": "Manage folder sharing",
    "linkTitle": "Manage folder sharing",
    "weight": "180"
}*Share Folder* is a feature. Its availability for end-users is controlled by the `SharedFolders.AllowCollaboration` configuration option in the Administration tool. When it is set to `true`, *Share Folder* is enabled. When set to false, *Share Folder* is disabled and the **Share** button is not visible.

## Disable Folder sharing from ST Web Client

Folder sharing can be disabled from the ST Web Client using the `shareAction` parameter. To do so, add the following section in the custom [configuration file](../config_files):

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{
   "features": {
   ...
	"shareAction": {
	"enabled": false
	}
   ...
}							</pre>
         </td>
      </tr>
   </tbody>
</table>

## Set the default folder sharing options

The *Share* dialog gives end-users the ability to share their folders with other people and perform the following operations:

-   set the collaborators access level
-   control collaborators' visibility to each other
-   configure notification criteria for the shared folder.

As an administrator, you can customize the default setting of the drop-down and the default states of the checkboxes located under **Options** and **Notifications**.

The following code snippet shows their default values in the ST Web Client configuration file; the defaults are applied when a folder is shared for the first time. For already shared folders, the *Share* dialog opens with the existing sharing settings pre-selected.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre xml:space="preserve">{ 
"shareAction": {					
    "default": {
	"access": {
	   "shareRights": "download",
	   "showCollaboratorsToAll": false
	},
	"notifications": {
	   "collaborators": false,
	   "owner": false
	}
  }
}					</pre>
         </td>
      </tr>
   </tbody>
</table>

To change a default setting, in the custom configuration file, add a "shareAction" section and change the value of the corresponding key.

Listed below are all the accepted properties and what they affect.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
<th colspan="4">
<p colspan="4">  Property</p>
<p colspan="4"><em>(type)</em>
</p>
</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="4">  <strong>shareAction</strong>            <p><em>(object)</em></p>         </td>
         <td>Controls the availability and the default option settings for the Share Folder feature          </td>
      </tr>
      <tr>
         <td colspan="4">  <strong>default</strong>            <p><em>(object)</em></p>         </td>
         <td>
            <p> Specifies the default settings for the shared folder's options</p>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td colspan="3">
<p colspan="3"> <strong>access</strong>            <p><em>(object)</em></p></p>
         </td>
         <td>
            <p>Controls the collaborator's access level</p>
         </td>
      </tr>
      <tr>
         <td colspan="2">          </td>
         <td colspan="2">
<p colspan="2"><strong>shareRights</strong>
            <p><em>(enumeration)</em>
</p>
</p>
         </td>
         <td>
            <p>Sets the default value of the <strong>Access</strong> drop-down</p>
            <p>Default value: <code>download</code>;</p>
            <p>Enumeration values: <code>download</code>, <code>upload</code>, <code>overwrite</code></p>
         </td>
      </tr>
      <tr>
         <td colspan="2">          </td>
         <td colspan="2">
<p colspan="2"><strong>showCollaboratorsToAll</strong>
            <p><em>(Boolean)</em>
</p>
</p>
         </td>
         <td>
            <p>Sets the default state of the <strong>Allow people to view collaborators</strong> checkbox;</p>
            <p>Default value: <code>false </code>(the check-box is not selected)</p>
         </td>
      </tr>
      <tr>
         <td>          </td>
         <td colspan="3">
<p colspan="3"><b>notifications</b>
            <p><em>(<b>object</b>)</em>
</p>
</p>
         </td>
         <td>
            <p>Controls user notifications for the shared folder</p>
         </td>
      </tr>
      <tr>
         <td colspan="2">          </td>
         <td colspan="2">
<p colspan="2"><strong>collaborators</strong>
            <p><em>(Boolean)</em>
</p>
</p>
         </td>
         <td>
            <p>Sets the default state of the <b>Send notifications to collaborators</b> checkbox</p>
            <p>Default value: <code>false </code>(the check-box is not selected)</p>
         </td>
      </tr>
      <tr>
         <td colspan="2">          </td>
         <td colspan="2">
<p colspan="2"><strong>owner</strong>
            <p><em>(Boolean)</em>
</p>
</p>
         </td>
         <td>
            <p>Sets the default state of the <strong>Notify me when a file is uploaded</strong> checkbox</p>
            <p>Default value: <code>false </code>(the check-box is not selected)</p>
         </td>
      </tr>
   </tbody>
</table>
