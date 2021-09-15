{
    "title": "nspassw",
    "linkTitle": "nspassw",
    "weight": "2370"
}### <span id="nspassw"></span>nspassw

#### CFTPART

**\[NSPASSW =
*string*\]**

*string32* SFTP

*string8* ODETTE, PeSIT E

The remote partner checks that the value received equals the value of
the NRPASSW parameter documented in the description of the corresponding
CFTPART.

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
