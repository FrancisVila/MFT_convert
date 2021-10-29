{
    "title": "rcomp",
    "linkTitle": "rcomp",
    "weight": "2820"
}### <span id="rcomp"></span>rcomp

#### CFTPROT

\[RCOMP = { <u>see the table</u> | 15 } \]

Maximum authorized compression for receiving a file.
This compression is negotiated between the sender and the receiver.

A zero value corresponds to no compression (default).

Default values are:

<table data-border="1" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Protocol</th>
         <th>Default value</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="31%">            <p>PeSIT ANY profile</p>         </td>
         <td data-valign="top" width="69%">            <p>0</p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="31%">            <p>ODETTE </p>         </td>
         <td data-valign="top" width="69%">            <p>1 </p>         </td>
      </tr>
   </tbody>
</table>

See also [scomp](scomp).

For more information (usable values etc.), refer to the *Compression*
topic.

[Return to Command index](../)
