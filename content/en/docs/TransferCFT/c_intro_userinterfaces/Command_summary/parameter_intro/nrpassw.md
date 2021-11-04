{
    "title": "nrpassw",
    "linkTitle": "nrpassw",
    "weight": "2290"
}<span id="nrpassw"></span>

### nrpassw

#### CFTPART

**\[NRPASSW = string\]**

*string32*     SFTP

*string8*     ODETTE, PeSIT E

Partner sign-on password, authorizing a local site access right check.

The remote partner must submit this password to the local <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>, during the connection phase. On the remote partner end, you must declare this
password as the NSPASSW parameter of the CFTPART object
used in the transfer.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If you begin a password with an indirection character (Unix @, Windows #) when using SFTP, it is considered a reference to a file and not part of the password. Please see the SFTP pages for more information.         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../../)