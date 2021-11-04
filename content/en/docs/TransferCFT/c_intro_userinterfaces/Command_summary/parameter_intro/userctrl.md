{
    "title": "userctrl",
    "linkTitle": "userctrl",
    "weight": "3670"
}<span id="userctrl"></span>

### userctrl

#### CFTPARM

\[USERCTRL = { <span style="text-decoration: underline;">NO</span>
| YES }\]

Use this field to define the file access control. You can use the UserCtrl parameter to define access to files under another credential (UserId parameter) other than the user who started Transfer CFT.

-   YES:
    <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> checks the user access rights on the file to be transferred.
-   NO: No check is performed.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><em>Windows only</em> - You cannot use a UNC or mapped drive (as opposed to files on a local disk) when USERCTRL=YES. Note though that even when USERCTRL=NO, you cannot access files on a local or remote disk under another account.         </td>
      </tr>
   </tbody>
</table>

-   For details in UNIX, please see <a href="##Manually" class="MCXref xref">Enable the file user rights (USERCTRL)</a>
-   For details in Windows, please see <a href="##Enable3" class="MCXref xref">Enable the file user rights (USERCTRL)</a>

 

[Return to Command index](../../)