{
    "title": " Configure receive mode (native)",
    "linkTitle": "Configure receive mode (native)",
    "weight": "220"
}## File type

The behavior of the values ‘’ and ‘ ’, for FTYPE and FRECFM respectively, are not detailed in the following tables. These values correspond to undefined, which means that the transfer in reception takes the value sent through the network. 

File type when the file does not exist

The following table lists the different types of files that can be created on an IBM i system if the file to receive does not already exist:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
<th rowspan="2">FTYPE</th>
<th rowspan="2">FRECFM</th>
<th colspan="2">Created file</th>
      </tr>
      <tr class="odd">
         <th>Type</th>
         <th>Max record length</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td rowspan="2">            <p>‘D’</p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p>PF-DTA </p>         </td>
         <td>            <p>FLRECL</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>PF-DTA</p>         </td>
         <td>            <p>FLRECL + 5 bytes <sup>1</sup></p>         </td>
      </tr>
      <tr class="odd">
         <td rowspan="2">            <p>‘S’</p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p>PF-SRC</p>         </td>
         <td>            <p>FLRECL</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>PF-SRC</p>         </td>
         <td>            <p>FLRECL</p>         </td>
      </tr>
      <tr class="odd">
         <td rowspan="2">            <p>‘E’</p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p>PF-SRC</p>         </td>
         <td>            <p>FLRECL  +12  bytes <sup>2</sup></p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>PF-SRC</p>         </td>
         <td>            <p>FLRECL  +12  bytes <sup>2</sup></p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>‘Z’</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>SAVF</p>         </td>
         <td>            <p>NA</p>         </td>
      </tr>
   </tbody>
</table>

File type when the file already exists

The following table describes the Transfer CFT behavior when trying to receive data in an existing file on the native side of an IBM i system.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Bold  values indicate a recommended combination. For example, when <strong>FTYPE=D</strong> and <strong>FRECFM=V</strong> then <strong><strong>FLRECL+5 / 5</strong></strong> is the recommended PF-SRC.         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0">
   <thead>
      <tr class="header">
<th rowspan="2">  FTYPE</th>
<th rowspan="2">  FRECFM</th>
<th colspan="3">Existing file</th>
      </tr>
      <tr class="odd">
         <th>            <p>PF-DTA</p>
            <p>Record length / member header</p></th>
         <th>            <p>PF-SRC</p>
            <p>Record length / member header</p></th>
         <th>            <p>Overwriting on a SAVF</p>
            <p>with FACTION=ERASE</p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td rowspan="2">            <p>‘D’</p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p><strong>FLRECL / No</strong></p>         </td>
         <td>            <p>FLRECL / No</p>         </td>
         <td>            <p>Yes <sup>3</sup></p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>FLRECL+5 / 5</p>         </td>
         <td>            <p><strong>FLRECL+5 / 5</strong></p>         </td>
         <td>            <p>Yes <sup>3</sup></p>         </td>
      </tr>
      <tr class="odd">
         <td rowspan="2">            <p>‘S’</p>
            <p> </p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p>FLRECL / 0  OK</p>         </td>
         <td>            <p><strong>FLRECL / 12</strong></p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 102</p>
            <p>DIAGP: 1140850696</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>FLRECL+17 /  17</p>         </td>
         <td>            <p>FLRECL+17 /  17</p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 102</p>
            <p>DIAGP: 1140850696</p>         </td>
      </tr>
      <tr class="odd">
         <td rowspan="2">            <p>‘E’</p>         </td>
         <td>            <p>‘F’</p>         </td>
         <td>            <p>FLRECL +12 / 0</p>         </td>
         <td>            <p><strong>FLRECL +12 / 12</strong></p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 102</p>
            <p>DIAGP: 1140850696</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>‘V’</p>         </td>
         <td>            <p>FLRECL+17 /17</p>
            <p> </p>         </td>
         <td>            <p>FLRECL+17 /  5</p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 102</p>
            <p>DIAGP: 1140850696</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>‘Z’</p>         </td>
         <td>            <p>-</p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 102</p>
            <p>DIAGP: 1140850696</p>         </td>
         <td>            <p>Error</p>
            <p>DIAGI: 101</p>
            <p>DIAGP: 11409169</p>         </td>
         <td>            <p>Yes <sup>3</sup></p>         </td>
      </tr>
   </tbody>
</table>

<sup>1</sup> The file is created with a record length corresponding to the record length of the original file, plus 5 bytes corresponding to five header bytes in each record. These 5 bytes indicate the length of useful data.

<sup>2</sup> The file is created with a record length corresponding to the record length of the original file, plus 12 bytes corresponding to five header bytes in each record. These 12 bytes indicate the date and the sequence number.

<sup>3</sup> You must set FACTION to ERASE for the transfer. Otherwise, the transfer fails to overwrite the existing file, and ends in error.
