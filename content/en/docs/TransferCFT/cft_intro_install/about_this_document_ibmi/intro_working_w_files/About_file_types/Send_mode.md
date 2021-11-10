{
    "title": "Configure send mode (native)",
    "linkTitle": "Configure send mode (native)",
    "weight": "210"
}## Native file type definitions

The following table lists the different types of files that can be used according to the type of data to be sent.

> **Note:**
>
> Bold  values indicate a recommended combination. For example, when FTYPE=D and FRECFM=V then RCDLEN-5 is the recommended PF-DTA with variable data.

<table>
   <tbody>
      <tr>
         <td>FTYPE         </td>
         <td>FRECFM         </td>
         <td><p>PF-DTA</p>
<p>Fixed data</p>         </td>
         <td><p>PF-DTA</p>
<p>Variable data</p>         </td>
         <td>PF-SRC         </td>
         <td>SAVF         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>FRECFL         </td>
         <td>FRECFL         </td>
         <td>FRECFL         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>‘D’</p>         </td>
         <td><p> ‘F’</p>         </td>
         <td><p><strong>RCDLEN</strong></p>         </td>
         <td><p>RCDLEN <sup>1</sup></p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>528</p>         </td>
      </tr>
      <tr>
         <td><p>‘V’</p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p><strong>RCDLEN-5</strong> <sup>2</sup></p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>528</p>         </td>
      </tr>
      <tr>
         <td><p>‘S’</p>         </td>
         <td><p> ‘F’</p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>RCDLEN <sup>1</sup></p>         </td>
         <td><p><strong>RCDLEN</strong></p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
      </tr>
      <tr>
         <td><p>‘V’</p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>RCDLEN-5 <sup>2</sup></p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
      </tr>
      <tr>
         <td><p>‘E’</p>         </td>
         <td><p> ‘F’</p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>RCDLEN <sup>1</sup></p>         </td>
         <td><p><strong>RCDLEN-12</strong> <sup>3</sup></p>         </td>
         <td><p> Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
      </tr>
      <tr>
         <td><p>‘V’</p>         </td>
         <td><p>RCDLEN</p>         </td>
         <td><p>RCDLEN-5 <sup>2</sup></p>         </td>
         <td><p>RCDLEN-12 <sup>3</sup></p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
      </tr>
      <tr>
         <td><p>‘Z’</p>
<p> </p>         </td>
         <td><p> ‘F’</p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696 </p>         </td>
         <td><p> Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696 </p>         </td>
         <td><p> <strong>528</strong></p>         </td>
      </tr>
      <tr>
         <td><p> ‘V’</p>         </td>
         <td><p>Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
         <td><p> Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
         <td><p> Error<br />
DIAGI: 102<br />
DIAGP: 1140850696</p>         </td>
         <td><p> 528</p>         </td>
      </tr>
   </tbody>
</table>

Key

<sup>1</sup> Truncates the 5 bytes variable header, preserving the original record length.

<sup>2</sup> Truncates the 5 bytes variable header, adjusting the record length accordingly.

<sup>3</sup> Truncates the 12 bytes, adjusting the record length accordingly.

Default FTYPE or FRECFM value

The behavior of the values ‘’ and ‘ ’, for FTYPE and FRECFM respectively, are not detailed in the following table. These values correspond to <span class="code">undefined</span>, meaning that the transfer in emission takes the value of both the file type and the member content.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FTYPE</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>FRECFM</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Supported files and data organizations (if applicable).</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>‘D’         </td>
         <td>‘F’         </td>
         <td><p>PF-DTA Member containing fixed data</p>         </td>
      </tr>
      <tr>
         <td>‘D’         </td>
         <td>‘V’         </td>
         <td><p>PF-DTA Member containing variable data</p>         </td>
      </tr>
      <tr>
         <td>‘D’         </td>
         <td>‘F’         </td>
         <td>PF-SRC         </td>
      </tr>
      <tr>
         <td>‘Z’         </td>
         <td>‘F’         </td>
         <td>SAVF         </td>
      </tr>
   </tbody>
</table>
