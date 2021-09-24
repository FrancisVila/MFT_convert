{
    "title": "scomp",
    "linkTitle": "scomp",
    "weight": "3100"
}### <span id="scomp"></span>scomp

#### CFTPROT

**\[SCOMP = { <u>0</u> | 15 } \]** 

The maximum authorized compression for sending a file.

-   rcomp//scomp
    = 0 (no compression)
-   rcomp//scomp
    = 1 (compression of a string of
    blanks)
-   rcomp//scomp
    = 2 (compression of a string of
    identical characters)
-   rcomp//scomp
    = 4 (character compression)
-   rcomp//scomp
    = 8 (vertical compression)
-   rcomp//scomp
    = 15 (all compressions)

This compression is negotiated between the sender and the receiver.

Default values are:

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Protocol </p>
</th>
         <th>
            <p>Default value </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td valign="top" width="36%">
            <p>PeSIT ANY profile</p>
         </td>
         <td valign="top" width="64%">
            <p>0</p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="36%">
            <p>ODETTE </p>
         </td>
         <td valign="top" width="64%">
            <p>1 </p>
         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)
