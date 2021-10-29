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

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">If you begin a password with an indirection character (Unix @, Windows #) when using SFTP, it is considered a reference to a file and not part of the password. Please see the SFTP pages for more information.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
