{
    "title": "Operating system specific parameters",
    "linkTitle": "OS specific parameters",
    "weight": "250"
}## Platform specific characters

<span class="autonumber"></span><span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> Guardian specific values

<table>
   <th>
      <tr>
<th><p>Notation</p>         </th>
<th><p>Object</p>         </th>
<th><p>Value</p>         </th>
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

<span class="autonumber"></span>File properties automatically retrieved for send operations

<table>
   <th>
      <tr>
<th><p>Notation</p>         </th>
<th><p>Object</p>         </th>
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

<span class="autonumber"></span>FTYPE values and associated implicit FCODE default values for send operations

<table>
   <th>
      <tr>
<th><p>FTYPE</p>         </th>
<th><p>FCODE</p>         </th>
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

<span class="autonumber"></span>FTYPE, FRECFM, and FORG combinations for send operations

<table>
   <th>
      <tr>
<th> 
<p>Guardian<br />
type</p>         </th>
<th> 
<p>Guardian<br />
code</p>         </th>
<th> 
<p>File type</p>         </th>
<th>Implicit value for...         </th>
      </tr>
      <tr>
<th><p>FTYPE<br />
</p>         </th>
<th><p>FRECFM<br />
</p>         </th>
<th>FORG         </th>
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

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Empty cells indicate that the information is not significant.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span style="vertical-align: super;">[1]</span> You can also send variable length record files by setting FRECFM = V.         </td>
      </tr>
   </tbody>
</table>

<span class="autonumber"></span>FTYPE, FRECFM, and FORG values for receive operations

<table>
   <th>
      <tr>
<th><p>FTYPE</p>         </th>
<th><p>FRECFM</p>         </th>
<th>FORG         </th>
<th><p>File Type</p>         </th>
<th><p>Guardian Type</p>         </th>
<th><p>Guardian Code</p>         </th>
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

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Empty cells indicate that the information is not significant.         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span style="vertical-align: super;">[2]</span> Read the file organization from the network, explicitly set FORG to FORG= ‘ ‘. Otherwise, FORG is always sequential (FORG = SEQ).         </td>
      </tr>
   </tbody>
</table>

## Platform specific parameters and values

ATTSUSER

Use the ATTSUSER parameter to set specific attributes for receiving native files. This parameter can take three values, FCODE, FORMAT, and BUFFERED.

FCODE

Forces the file CODE attribute. This value should be consistent with the file structure and the restrictions of the system. If FCODE is not specified, Transfer CFT sets the code per the table iah,n Figure 5.

<span class="bold_in_para">Example</span>: <span class="code">ATTSUSER = 'FCODE=180'</span>

The received file is created with 180 as the code.

FORMAT

Forces the file FORMAT attribute. This value is either 1 or 2. If FORMAT is not specified, Transfer CFT sets the format according to the estimated size of the received file. A file whose size is greater than 2GB has the format 2, while a file having a size less than 2GB has the format 1.

<span class="bold_in_para">Example</span>: <span class="code">ATTSUSER = 'FORMAT=2'</span>

The received file is created with the format 2.

Use multiple values

Additionally, you can use multiple values:

<span class="bold_in_para">Example</span>: <span class="code">ATTSUSER = ' FCODE=180,FORMAT=1'</span>

The received file is created with the format 1, and 180 as the code.

BUFFERED

If specified, this parameter forces the BUFFERED attribute for the Guardian file. The possible values are 0 (NO BUFFERED) and 1 (BUFFERED). If not specified, Transfer CFT does not force the attribute. You can find more information on this attribute in the *File Utility Program (FUP) Reference Manual*.

**Example**: <span class="code">ATTSUSER = 'BUFFERED=1'</span>

The received file is created with a BUFFERED attribute set.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>If a received file has the BUFFERED option, the file write cache is flushed while the PeSIT synchronization points are set. This means that there is no data loss (the file is not altered) if the file transfer is restarted. This applies whether BUFFERED is set on Transfer CFT or by an explicit file creation operation.         </td>
      </tr>
   </tbody>
</table>
