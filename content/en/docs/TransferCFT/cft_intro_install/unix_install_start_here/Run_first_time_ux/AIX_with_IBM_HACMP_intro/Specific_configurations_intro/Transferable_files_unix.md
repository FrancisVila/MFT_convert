{
    "title": "Transferable files",
    "linkTitle": "Transferable files",
    "weight": "270"
}This
topic describes the Transfer
CFT parameters that are specific to UNIX concerning the characteristics of a transferable file.

-   Characteristics of files automatically detected (or not) on transmission
-   FTYPE and FCODE values implicitly
    associated during transmission
-   FTYPE and FRECFM values on receipt

#### Characteristics of files automatically detected on transmission

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter </th>
         <th>Automatically detected on transmission</th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FSPACE </p>
         </td>
         <td valign="top" width="79%">
            <p>YES </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FLRECL </p>
         </td>
         <td valign="top" width="79%">
            <p>NO</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FBLKSIZE </p>
         </td>
         <td valign="top" width="79%">
            <p>NO </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FRECFM </p>
         </td>
         <td valign="top" width="79%">
            <p>NO</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FTYPE </p>
         </td>
         <td valign="top" width="79%">
            <p>NO</p>
         </td>
      </tr>
</table>

#### FTYPE values and FCODE values implicitly associated during transmission

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FCODE</th>
         <th>Type of sent file </th>
      </tr>
   </thead>
      <tr>
         <td>
            <p>‘ ‘ </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>B </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary         </td>
      </tr>
      <tr>
         <td>
            <p>V </p>
         </td>
         <td>
            <p>BINARY </p>
         </td>
         <td>Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td>
            <p>T </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with LF or CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>
            <p>O </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>
            <p>X </p>
         </td>
         <td>
            <p>ASCII </p>
         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>J          </td>
         <td>ASCII          </td>
         <td>
            <p>Stream text</p>
            <p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
         </td>
      </tr>
</table>

FTYPE = J refers to stream text. The stream text type allows sending a text file that contains records that are larger than 32 KB. Unlike classical text types (T, O, X) the stream text type does not add an EOL sequence (LF or CRLF) at the end of the received file.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">FTYPE J  is available in <span>Transfer CFT</span> <span>Transfer CFT</span> 3.0.1 SP7 (UNIX and Windows) and higher.         </td>
      </tr>
</table>

#### FTYPE and FRECFM values on receipt

<table border="1" cellspacing="0" width="90%">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>FTYPE</th>
         <th>FRECFM</th>
         <th>Type of received file</th>
      </tr>
   </thead>
      <tr>
         <td valign="top" width="13%">
            <p>B </p>
         </td>
         <td valign="top" width="18%">
            <p>F </p>
         </td>
         <td valign="top" width="69%">
            <p>Binary fixed-length sequential file  </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">
            <p>B </p>
         </td>
         <td valign="top" width="18%">
            <p>U /V</p>
         </td>
         <td valign="top" width="69%">Binary sequential file         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">
            <p>V </p>
         </td>
         <td valign="top" width="18%">
            <p>V </p>
         </td>
         <td valign="top" width="69%">Binary file emulating locally a variable file format         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">T	         </td>
         <td valign="top" width="18%">F 	         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">T         </td>
         <td valign="top" width="18%">U /V         </td>
         <td valign="top" width="69%">Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">O         </td>
         <td valign="top" width="18%">F         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">
            <p>O </p>
         </td>
         <td valign="top" width="18%">
            <p>U/V </p>
         </td>
         <td valign="top" width="69%">Variable length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">X         </td>
         <td valign="top" width="18%">F         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr>
         <td valign="top" width="13%">
            <p>X </p>
         </td>
         <td valign="top" width="18%">
            <p>U/V </p>
         </td>
         <td valign="top" width="69%">Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr data-mc-conditions="">
         <td valign="top" width="13%">J         </td>
         <td valign="top" width="18%">U/V         </td>
         <td valign="top" width="69%">Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
</table>

These values are either given explicitly in the CFTRECV command or deduced
from the protocol values received.

-   On request Transfer CFT performs an access control on the files transferred.
    It determines, for example, if the initiator of the send request has read
    access rights on the file to be sent.
-   On receipt, Transfer CFT creates the file if it does not exist.
-   The organization, FORG, of the files sent or received by Transfer CFT
    is sequential.
