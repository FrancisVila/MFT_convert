{
    "title": "disctd",
    "linkTitle": "disctd",
    "weight": "750"
}### <span id="disctd"></span>disctd

#### **CFTPROT**

\[DISCTD = { <u>see table below</u> | n} {0..3600}
\]

Wait timeout in seconds before disconnection, in the absence of a new
transfer request to the partner, in requester mode.

The session established for a transfer remains active for DISCTD seconds
after the completion of this transfer.

If the value is 0, the wait timeout is infinite.

The default value, in seconds, depends on the protocol and is
indicated in the table below.

Default values are:

<table data-border="1" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Protocol </p></th>
         <th>            <p>Default value</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="33%">            <p>PeSIT ANY profile</p>         </td>
         <td data-valign="top" width="67%">            <p>10 </p>         </td>
      </tr>
      <tr class="even" data-mc-conditions="" data-valign="middle">
         <td data-valign="top" width="33%">            <p>ODETTE </p>         </td>
         <td data-valign="top" width="67%">            <p>20 </p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
