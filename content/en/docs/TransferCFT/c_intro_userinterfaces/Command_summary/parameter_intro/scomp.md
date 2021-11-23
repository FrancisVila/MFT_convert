{
    "title": "scomp",
    "linkTitle": "scomp",
    "weight": "3070"
}<span id="scomp"></span>

### scomp

#### CFTPROT

**\[SCOMP = { <u>0</u> | 15 } \]** 

The maximum authorized compression for sending a file.

-   rcomp//scomp
    = **0** (no compression)
-   rcomp//scomp
    = <span style="font-weight: bold;">1</span> (compression of a string of
    blanks)
-   rcomp//scomp
    = <span style="font-weight: bold;">2</span> (compression of a string of
    identical characters)
-   rcomp//scomp
    = <span style="font-weight: bold;">4</span> (character compression)
-   rcomp//scomp
    = <span style="font-weight: bold;">8</span> (vertical compression)
-   rcomp//scomp
    = <span style="font-weight: bold;">15</span> (all compressions)

This compression is negotiated between the sender and the receiver.

Default values are:

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Protocol </p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Default value</p>         </th>
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

[Return to Command index](../../)
