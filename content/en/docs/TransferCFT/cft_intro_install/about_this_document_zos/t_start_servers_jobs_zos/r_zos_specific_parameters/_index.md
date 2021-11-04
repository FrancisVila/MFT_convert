{
    "title": "Working with files and coding",
    "linkTitle": "About files and coding",
    "weight": "260"
}## Specific parameters for z/OS

This section describes the parameters and values that are specific to Transfer CFT z/OS and information about:

-   Transferable files
-   Filename coding

## Transferable files

File characteristics that are found automatically for sending are listed in the following table.

**File characteristics**

<table>
   <th>
      <tr>
<th>Parameter         </th>
<th>Found automatically for sending         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FSPACE</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
      <tr>
         <td><p>FLRECL</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
      <tr>
         <td><p>FBLKSIZE</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
      <tr>
         <td><p>FRECFM</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
      <tr>
         <td><p>FTYPE</p>         </td>
         <td><p>YES</p>         </td>
      </tr>
   </tbody>
</table>

**FTYPE and FRECFM combinations for sending**

<table>
   <th>
      <tr>
<th>Type of file to be sent         </th>
<th>Implicit value of FTYPE         </th>
<th>Implicit value of FRECFMz         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Disk sequential files</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
      </tr>
      <tr>
         <td><p>Members of PDS files (1 transfer per member)</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
      </tr>
      <tr>
         <td><p>Designated version of a file in GDG</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
      </tr>
      <tr>
         <td><p>Multivolume disk file</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
      </tr>
      <tr>
         <td><p>VSAM KSDS or ESDS file</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V</p>         </td>
      </tr>
      <tr>
         <td><p>Print file with ASA jump codes (z/OS to z/OS)</p>         </td>
         <td><p>A</p>         </td>
         <td><p>F/V/U</p>         </td>
      </tr>
      <tr>
         <td><p>Print file with machine jump codes (z/OS to z/OS)</p>         </td>
         <td><p>M</p>         </td>
         <td><p>F/V</p>         </td>
      </tr>
      <tr>
         <td><p>Spanned variable format file (z/OS to z/OS)</p>         </td>
         <td><p>S</p>         </td>
         <td><p>V</p>         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Variable SPANNED files can be routed through an intermediary Transfer CFT for the PeSIT protocol only (ANY profile). In this case, the file received on Transfer CFT z/OS is always in the ‘U’ format.         </td>
      </tr>
   </tbody>
</table>

The PDS files copied by IEBCOPY are also received in the ‘U’ format, which is compatible with IEBCOPY.

**Receiving values for FORG, FTYPE and FRECFM**

<table>
   <th>
      <tr>
<th>FORG         </th>
<th>FTYPE         </th>
<th>FRECFM         </th>
<th>  Type of receive file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Disk sequential file</p>         </td>
      </tr>
      <tr>
         <td><p>PART</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Member of PDS files (1 transfer per member)</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Version designated -1 to 0 of a file in GDG</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Multivolume disk file</p>         </td>
      </tr>
      <tr>
         <td><p>DIRECT</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V</p>         </td>
         <td><p>VSAM ESDS file</p>         </td>
      </tr>
      <tr>
         <td><p>INDEXED</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V</p>         </td>
         <td><p>VSAM KSDS file (already exists but empty)</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p>A</p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Print file with ASA jump code (z/OS to z/OS)</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p>M</p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Print file with machine jump code (z/OS to z/OS)</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p>S</p>         </td>
         <td><p>V</p>         </td>
         <td><p>File in spanned variable format (z/OS to z/OS)</p>         </td>
      </tr>
      <tr>
         <td><p>SEQ</p>         </td>
         <td><p> </p>         </td>
         <td><p>F/V/U</p>         </td>
         <td><p>Magnetic tape or cartridge file in position 1 (with STANDARD LABELS)</p>         </td>
      </tr>
   </tbody>
</table>

These values are explicit in CFTRECV or are deduced from the received protocol values.