{
    "title": "rcomp",
    "linkTitle": "rcomp",
    "weight": "2790"
}<span id="rcomp"></span>

### rcomp

#### CFTPROT

\[RCOMP = { <u>see the table</u> | 15 } \]

Maximum authorized compression for receiving a file.
This compression is negotiated between the sender and the receiver.

A zero value corresponds to no compression (default).

Default values are:

<table>
   <th>
      <tr>
<th>Protocol         </th>
<th>Default value         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT ANY profile</p>         </td>
         <td><p>0</p>         </td>
      </tr>
      <tr>
         <td><p>ODETTE </p>         </td>
         <td><p>1 </p>         </td>
      </tr>
   </tbody>
</table>

See also <span style="font-weight: bold;">[scomp](../scomp)</span>.

For more information (usable values etc.), refer to the *Compression*
topic.

[Return to Command index](../../)
