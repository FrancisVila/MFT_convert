{
    "title": "Manage folder sharing",
    "linkTitle": "Manage folder sharing",
    "weight": "180"
}*Share Folder* is a feature. Its availability for end-users is controlled by the `SharedFolders.AllowCollaboration` configuration option in the {{< SecureTransport/adminconsole  >}} tool. When it is set to `true`, *Share Folder* is enabled. When set to false, *Share Folder* is disabled and the **Share** button is not visible.

## Disable Folder sharing from ST Web Client

Folder sharing can be disabled from the ST Web Client using the `shareAction` parameter. To do so, add the following section in the custom [configuration file](../config_files):


    {
       "features": {
       ...
        "shareAction": {
        "enabled": false
        }
       ...
    }                           

## Set the default folder sharing options

The *Share* dialog gives end-users the ability to share their folders with other people and perform the following operations:

-   set the collaborators access level
-   control collaborators' visibility to each other
-   configure notification criteria for the shared folder.

As an administrator, you can customize the default setting of the drop-down and the default states of the checkboxes located under **Options** and **Notifications**.

The following code snippet shows their default values in the ST Web Client configuration file; the defaults are applied when a folder is shared for the first time. For already shared folders, the *Share* dialog opens with the existing sharing settings pre-selected.


    { 
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
    }                   

To change a default setting, in the custom configuration file, add a "shareAction" section and change the value of the corresponding key.

Listed below are all the accepted properties and what they affect.

<table>
   <thead>
      <tr>
<th colspan="4" class="HeadE-Column1-Header1"><p>  Property</p>
<p><em>(type)</em></p>         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>  <strong>shareAction</strong>
<p><em>(object)</em></p>         </td>
         <td>Controls the availability and the default option settings for the Share Folder feature         </td>
      </tr>
      <tr>
         <td>  <strong>default</strong>
<p><em>(object)</em></p>         </td>
         <td><p>Specifies the default settings for the shared folder's options</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p> <strong>access</strong></p>
<p><em>(object)</em></p>         </td>
         <td><p>Controls the collaborator's access level</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><strong>shareRights</strong></p>
<p><em>(enumeration)</em></p>         </td>
         <td><p>Sets the default value of the <strong>Access</strong> drop-down</p>
<p>Default value: <code>download</code>;</p>
<p>Enumeration values: <code>download</code>, <code>upload</code>, <code>overwrite</code></p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><strong>showCollaboratorsToAll</strong></p>
<p><em>(Boolean)</em></p>         </td>
         <td><p>Sets the default state of the <strong>Allow people to view collaborators</strong> checkbox;</p>
<p>Default value: <code>false </code>(the check-box is not selected)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><strong>notifications</strong></p>
<p><em>(<strong>object</strong>)</em></p>         </td>
         <td><p>Controls user notifications for the shared folder</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><strong>collaborators</strong></p>
<p><em>(Boolean)</em></p>         </td>
         <td><p>Sets the default state of the <strong>Send notifications to collaborators</strong> checkbox</p>
<p>Default value: <code>false </code>(the check-box is not selected)</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><strong>owner</strong></p>
<p><em>(Boolean)</em></p>         </td>
         <td><p>Sets the default state of the <strong>Notify me when a file is uploaded</strong> checkbox</p>
<p>Default value: <code>false </code>(the check-box is not selected)</p>         </td>
      </tr>
   </tbody>
</table>
