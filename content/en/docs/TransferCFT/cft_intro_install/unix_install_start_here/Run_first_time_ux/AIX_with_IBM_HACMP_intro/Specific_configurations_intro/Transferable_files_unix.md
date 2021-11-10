{
    "title": "Transferable files ",
    "linkTitle": "Transferable files",
    "weight": "250"
}This
topic describes the Transfer
CFT parameters that are specific to UNIX concerning the characteristics of a transferable file.

-   Characteristics of files automatically detected (or not) on transmission
-   FTYPE and FCODE values implicitly
    associated during transmission
-   FTYPE and FRECFM values on receipt

#### Characteristics of files automatically detected on transmission

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Parameter         </th>
<th class="HeadD-Column1-Header1">Automatically detected on transmission         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>FSPACE </p>         </td>
         <td><p>YES </p>         </td>
      </tr>
      <tr>
         <td><p>FLRECL </p>         </td>
         <td><p>NO</p>         </td>
      </tr>
      <tr>
         <td><p>FBLKSIZE </p>         </td>
         <td><p>NO </p>         </td>
      </tr>
      <tr>
         <td><p>FRECFM </p>         </td>
         <td><p>NO</p>         </td>
      </tr>
      <tr>
         <td><p>FTYPE </p>         </td>
         <td><p>NO</p>         </td>
      </tr>
   </tbody>
</table>

#### FTYPE values and FCODE values implicitly associated during transmission

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FTYPE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">FCODE         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Type of sent file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>‘ ‘ </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>B </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td><p>V </p>         </td>
         <td><p>BINARY </p>         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td><p>T </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>O </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>X </p>         </td>
         <td><p>ASCII </p>         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>ASCII          </td>
         <td><p>Stream text</p>
<p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
<p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>         </td>
      </tr>
   </tbody>
</table>

FTYPE = J refers to stream text. The stream text type allows sending a text file that contains records that are larger than 32 KB. Unlike classical text types (T, O, X) the stream text type does not add an EOL sequence (LF or CRLF) at the end of the received file.

> **Note:**
>
> FTYPE J is available in Transfer CFT Transfer CFT 3.0.1 SP7 (UNIX and Windows) and higher.

#### FTYPE and FRECFM values on receipt

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">FTYPE         </th>
<th class="HeadE-Column1-Header1">FRECFM         </th>
<th class="HeadD-Column1-Header1">Type of received file         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>B </p>         </td>
         <td><p>F </p>         </td>
         <td><p>Binary fixed-length sequential file  </p>         </td>
      </tr>
      <tr>
         <td><p>B </p>         </td>
         <td><p>U /V</p>         </td>
         <td>Binary sequential file         </td>
      </tr>
      <tr>
         <td><p>V </p>         </td>
         <td><p>V </p>         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td>T         </td>
         <td>F         </td>
         <td>Fixed-length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>T         </td>
         <td>U /V         </td>
         <td>Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>O         </td>
         <td>F         </td>
         <td>Fixed-length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>O </p>         </td>
         <td><p>U/V </p>         </td>
         <td>Variable length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>X         </td>
         <td>F         </td>
         <td>Fixed-length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td><p>X </p>         </td>
         <td><p>U/V </p>         </td>
         <td>Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>J         </td>
         <td>U/V         </td>
         <td>Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
   </tbody>
</table>

These values are either given explicitly in the CFTRECV command or deduced
from the protocol values received.

-   On request Transfer CFT performs an access control on the files transferred.
    It determines, for example, if the initiator of the send request has read
    access rights on the file to be sent.
-   On receipt, Transfer CFT creates the file if it does not exist.
-   The organization, FORG, of the files sent or received by Transfer CFT
    is sequential.
