{
    "title": "Advanced Routing fails with the sandbox and user home folders on the same CIFS share ",
    "linkTitle": "Advanced Routing fails with the sandbox and user home folders on the same CIFS share ",
    "weight": "300"
}**Problem summary:** With SecureTransport deployments on Linux, Advanced Routing fails when the sandbox is located on the same CIFS share as the user's home folder.

**Problem details:**

1.  You set the user's home folder to be on a CIFS share.
2.  You set an absolute path value for the sandbox location in the '`AdvancedRouting.sandboxFolderLocation`' server configuration option to point to the same CIFS share.
3.  When you attempt to execute an Advanced Routing configuration, you get errors in the Server Log.

**Solution:**

1.  Make sure symbolic links are enabled.

2.  Mount the CIFS share following the example:  
    Enter the following command to run the Axway Installer:

    <table cellspacing="0">   <col/>   <tbody>      <tr>         <td><pre><code>mount -t cifs -o username=&lt;Administrator&gt;,password=&lt;password&gt;,file_mode=0777,dir_mode=0777,mfsymlinks //&lt;IP_address&gt;/Shared/&lt;user&gt;/&lt;home_folder&gt;</code></pre>         </td>      </tr>   </tbody></table>
