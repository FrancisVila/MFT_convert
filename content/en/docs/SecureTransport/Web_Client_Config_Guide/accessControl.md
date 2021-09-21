{
    "title": "Access Control",
    "linkTitle": "Access Control",
    "weight": "170"
}Use the `"fileOperations"` section to control the end-users' ability to create, move, rename, or delete files and folders.

All options are of type Boolean with default value `true` (no restrictions).

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{
    ...
    "accessControl": {
        "fileOperations": {
            "createFolder": {
                "enabled": true
            },
            "moveFile": {
                "enabled": true
            },
            "renameFileOrFolder": {
                "enabled": true
            },
            "deleteFileOrFolder": {
                "enabled": true
            }
        }
    },
    ...
}</pre>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The above section duplicates server settings and must be maintained together with all related settings in the <span>SecureTransport</span> Administration Tool. The restrictions target only the <span>ST Web Client</span> user interface - the users have other channels to bypass them if the server has more permissive settings.         </td>
      </tr>
</table>

 
