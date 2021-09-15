{
    "title": "nrpassw",
    "linkTitle": "nrpassw",
    "weight": "2320"
}### <span id="nrpassw"></span>nrpassw

#### CFTPART

**\[NRPASSW = string\]**

*string32*     SFTP

*string8*     ODETTE, PeSIT E

Partner sign-on password, authorizing a local site access right check.

The remote partner must submit this password to the local Transfer CFT, during the connection phase. On the remote partner end, you must declare this
password as the NSPASSW parameter of the CFTPART object
used in the transfer.

This parameter value is case sensitive in CFTUTIL commands if you enclose the value in " " quotes.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" valign="top">If you begin a password with an indirection character (Unix @, Windows #) when using SFTP, it is  considered a reference to a file and not part of the password. Please see the SFTP pages for more information.         </td>
      </tr>
</table>

 

[Return to Command index](../../)
