{
    "title": "Operating system specific parameters",
    "linkTitle": "OS specific parameters",
    "weight": "250"
}## Platform specific characters

{{< TransferCFT/componentlongname  >}} Guardian specific values

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Notation</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Object</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Value</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>char_file</p>         </td>
         <td><p>Prefix for logical names</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>char_mask</p>         </td>
         <td><p>Wildcard character</p>         </td>
         <td><p>?</p>         </td>
      </tr>
      <tr>
         <td><p>char_symb</p>         </td>
         <td><p>Prefix for symbolic variables</p>         </td>
         <td><p>^</p>         </td>
      </tr>
      <tr>
         <td><p>file_symb</p>         </td>
         <td><p>Prefix for a file name passed to CFTUTIL as a parameter</p>         </td>
         <td><p>@</p>         </td>
      </tr>
   </tbody>
</table>

File properties automatically retrieved for send operations

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Notation</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Object</p>         </th>
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

FTYPE values and associated implicit FCODE default values for send operations

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>FCODE</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>' '</p>         </td>
         <td><p>BINARY</p>         </td>
      </tr>
      <tr>
         <td><p>E</p>         </td>
         <td><p>ASCII</p>         </td>
      </tr>
   </tbody>
</table>

FTYPE, FRECFM, and FORG combinations for send operations

<table>
   <thead>
      <tr>
<th rowspan="2" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"> 
<p>Guardian<br />
type</p>         </th>
<th rowspan="2" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"> 
<p>Guardian<br />
code</p>         </th>
<th rowspan="2" class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"> 
<p>File type</p>         </th>
<th colspan="3" class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Implicit value for...         </th>
      </tr>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE<br />
</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FRECFM<br />
</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">FORG         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>U</p>         </td>
         <td><p># 101</p>         </td>
         <td><p>Binary stream</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>U</p>         </td>
         <td>SEQ         </td>
      </tr>
      <tr>
         <td><p>U</p>         </td>
         <td><p>= 101</p>         </td>
         <td><p>Edit file</p>         </td>
         <td><p>E</p>         </td>
         <td><p>U</p>         </td>
         <td>SEQ         </td>
      </tr>
      <tr>
         <td><p>E</p>         </td>
         <td><p># 1</p>         </td>
         <td><p>Fixed sequential</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>F</p>         </td>
         <td>SEQ         </td>
      </tr>
      <tr>
         <td><p>E</p>         </td>
         <td><p>= 1</p>         </td>
         <td><p>Sequential, variable emulation</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>V</p>         </td>
         <td>SEQ         </td>
      </tr>
      <tr>
         <td><p>R</p>         </td>
         <td><p> </p>         </td>
         <td><p>Direct fixed</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>F [1]</p>         </td>
         <td>DIR         </td>
      </tr>
      <tr>
         <td><p>K</p>         </td>
         <td><p> </p>         </td>
         <td><p>Fixed indexed sequential</p>         </td>
         <td><p>' '</p>         </td>
         <td><p>F [1]</p>         </td>
         <td>IDX         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Empty cells indicate that the information is not significant.

> **Note:**
>
> \[1\] You can also send variable length record files by setting FRECFM = V.

FTYPE, FRECFM, and FORG values for receive operations

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FRECFM</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FORG         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>File Type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Guardian Type</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Guardian Code</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p>U</p>         </td>
         <td>          </td>
         <td><p>Binary stream</p>         </td>
         <td><p>U</p>         </td>
         <td><p>0</p>         </td>
      </tr>
      <tr>
         <td><p>E</p>         </td>
         <td><p> </p>         </td>
         <td>          </td>
         <td><p>Edit file</p>         </td>
         <td><p>U</p>         </td>
         <td><p>101</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>F</p>         </td>
         <td>SEQ         </td>
         <td><p>Fixed sequential</p>         </td>
         <td><p>E</p>         </td>
         <td><p>0</p>         </td>
      </tr>
      <tr>
         <td><p> </p>         </td>
         <td><p>V</p>         </td>
         <td>          </td>
         <td><p>Sequential, variable emulation</p>         </td>
         <td><p>E</p>         </td>
         <td><p>1</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>F         </td>
         <td>DIR[2]         </td>
         <td>Direct fixed         </td>
         <td>R         </td>
         <td>0         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>V         </td>
         <td>DIR [2]         </td>
         <td>Direct fixed, variable emulation         </td>
         <td>R         </td>
         <td>1         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>F         </td>
         <td>IDX [2]         </td>
         <td>Fixed indexed sequential         </td>
         <td>K         </td>
         <td>0         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>V         </td>
         <td>IDX [2]         </td>
         <td>Indexed sequential, variable emulation         </td>
         <td>K         </td>
         <td>1         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> Empty cells indicate that the information is not significant.

> **Note:**
>
> \[2\] Read the file organization from the network, explicitly set FORG to FORG= ‘ ‘. Otherwise, FORG is always sequential (FORG = SEQ).

## Platform specific parameters and values

ATTSUSER

Use the ATTSUSER parameter to set specific attributes for receiving native files. This parameter can take three values, FCODE, FORMAT, and BUFFERED.

FCODE

Forces the file CODE attribute. This value should be consistent with the file structure and the restrictions of the system. If FCODE is not specified, Transfer CFT sets the code per the table iah,n Figure 5.

**Example**: `ATTSUSER    = 'FCODE=180'`

The received file is created with 180 as the code.

FORMAT

Forces the file FORMAT attribute. This value is either 1 or 2. If FORMAT is not specified, Transfer CFT sets the format according to the estimated size of the received file. A file whose size is greater than 2GB has the format 2, while a file having a size less than 2GB has the format 1.

**Example**: `ATTSUSER    = 'FORMAT=2'`

The received file is created with the format 2.

Use multiple values

Additionally, you can use multiple values:

**Example**: `ATTSUSER    = ' FCODE=180,FORMAT=1'`

The received file is created with the format 1, and 180 as the code.

BUFFERED

If specified, this parameter forces the BUFFERED attribute for the Guardian file. The possible values are 0 (NO BUFFERED) and 1 (BUFFERED). If not specified, Transfer CFT does not force the attribute. You can find more information on this attribute in the *File Utility Program (FUP) Reference Manual*.

**Example**: `ATTSUSER = 'BUFFERED=1'`

The received file is created with a BUFFERED attribute set.

> **Note:**
>
> If a received file has the BUFFERED option, the file write cache is flushed while the PeSIT synchronization points are set. This means that there is no data loss (the file is not altered) if the file transfer is restarted. This applies whether BUFFERED is set on Transfer CFT or by an explicit file creation operation.
