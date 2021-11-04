{
    "title": "Exceptional case: absolute path to sandbox folder in EL expressions",
    "linkTitle": "Exceptional case: absolute path to sandbox folder in EL expressions",
    "weight": "300"
}**Problem summary:** With <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployments on Windows Server, attempts to use a configured absolute path to sandbox location in an EL expression may fail and return an error.

**Problem details:**

1.  You set an absolute path value for the sandbox location in the '`AdvancedRouting.sandboxFolderLocation`' server configuration option.
2.  You configure use of EL expressions: set the '`AdvancedRouting.sandboxFolderLocation.expressionLanguage`' configuration option to '`true`'.
3.  When you attempt to use an expression (for example'`\\<IP_address>\Shared\sandbox\${env['DXAGENT_ACCOUNT_TYPE']}`' ), you might get errors in the Server Log.

**Possible cause:** The issue is configuration based and relates to the allowed remote storage for 'Users' to create symbolic links (configurable in 'secpol.msc' where 'Users' must be added in - *Security Settings &gt; Local Policies &gt; User Rights Assignment &gt; 'Create symbolic links'*). The problem occurs only in the case when the user's home folder and the sandbox custom folders are both set to one or more remote storage machines.

**Solution:** This problem might occur because by default remote to remote symbolic links are disabled. You can enable it with `fsutil`.

<table>
   <tbody>
      <tr>
         <td><p>C:\Windows\system32&gt;fsutil behavior query SymlinkEvaluation</p>
<ul>
<li>Local to local symbolic links are enabled.<br />
Local to remote symbolic links are enabled.<br />
Remote to local symbolic links are disabled.<br />
Remote to remote symbolic links are disabled.</li>
</ul>
<p>C:\Windows\system32&gt;fsutil behavior set SymlinkEvaluation R2R:1
C:\Windows\system32&gt;fsutil behavior query SymlinkEvaluation</p>
<ul>
<li>Local to local symbolic links are enabled.<br />
Local to remote symbolic links are enabled.<br />
Remote to local symbolic links are disabled.<br />
Remote to remote symbolic links are enabled.</li>
</ul>
<p>Be sure to run fsutil from elevated command prompt.</p>         </td>
      </tr>
   </tbody>
</table>
