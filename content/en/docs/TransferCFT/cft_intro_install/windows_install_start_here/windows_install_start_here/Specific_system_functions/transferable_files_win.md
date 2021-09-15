{
    "title": "Transferable files",
    "linkTitle": "Transferable files",
    "weight": "260"
}This
topic describes the Transfer
CFT parameters that are specific to Windows concerning the characteristics of the transferable file.

-   Characteristics
    of files automatically detected on transmission
-   FTYPE
    values and FCODE values implicitly associated during transmission
-   FTYPE
    and FRECFM values on receipt

#### Characteristics of files automatically detected on transmission

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameter </p>
</th>
         <th>
            <p>Automatically detected on 
 transmission </p>
</th>
      </tr>
   </thead>
   <tbody>
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
            <p>NO </p>
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
            <p>NO </p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="21%">
            <p>FTYPE </p>
         </td>
         <td valign="top" width="79%">
            <p>NO </p>
         </td>
      </tr>
   </tbody>
</table>

#### FTYPE values and FCODE values implicitly associated during transmission

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>FTYPE </p>
</th>
         <th>
            <p>FCODE </p>
</th>
         <th>Type of sent file</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>' '         </td>
         <td>BINARY          </td>
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
         <td>F         </td>
         <td>ASCII         </td>
         <td>Text file where the last character '1A' is transmitted (is not
   considered an EOF character)         </td>
      </tr>
      <tr>
         <td>O         </td>
         <td>ASCII         </td>
         <td>Text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr>
         <td>X         </td>
         <td>ASCII         </td>
         <td>Text file with LF as end-of-line separator         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>J         </td>
         <td>ASCII         </td>
         <td>
            <p>Stream text</p>
            <p>Using stream text (J) allows a text type file to be sent that contains records that exceed 32 KB. As opposed to text type (FTYPE=T), stream text does not add an EOL sequence (LF or CRLF) to the received file.</p>
            <p>When using stream text (FTYPE=J), the sender and the receiver must both have the FTYPE set to J. Setting only the sender or receiver to FTYPE=J results in unexpected content for the transferred file.</p>
         </td>
      </tr>
   </tbody>
</table>

FTYPE = J refers to stream text.The stream text type allows sending a text file that contains records that are larger than 32 KB. Unlike classical text types (T, O, X) the stream text type does not add an EOL sequence (LF or CRLF) at the end of the received file.

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

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>FTYPE </p>
</th>
         <th>
            <p>FRECFM </p>
</th>
         <th>
            <p>Type of received file </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="middle">
         <td>B         </td>
         <td>F         </td>
         <td>Binary fixed-length sequential file           </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>B</p>
         </td>
         <td valign="top" width="18%">
            <p>U/V</p>
         </td>
         <td valign="top" width="69%">Binary sequential file         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>V </p>
         </td>
         <td valign="top" width="18%">
            <p>V</p>
         </td>
         <td valign="top" width="69%">Binary file emulating locally a variable file format         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>T </p>
         </td>
         <td valign="top" width="18%">
            <p>F </p>
         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>T </p>
         </td>
         <td valign="top" width="18%">
            <p>U/V</p>
         </td>
         <td valign="top" width="69%">Variable length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">O         </td>
         <td valign="top" width="18%">F         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">O         </td>
         <td valign="top" width="18%">U/V         </td>
         <td valign="top" width="69%">Variable length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">
            <p>X</p>
         </td>
         <td valign="top" width="18%">
            <p>F </p>
         </td>
         <td valign="top" width="69%">Fixed-length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="13%">X         </td>
         <td valign="top" width="18%">U/V         </td>
         <td valign="top" width="69%">Variable length sequential text file with LF as end-of-line separator         </td>
      </tr>
      <tr data-mc-conditions="" valign="middle">
         <td valign="top" width="13%">J         </td>
         <td valign="top" width="18%">U/V         </td>
         <td valign="top" width="69%">Variable length sequential text file with CRLF as end-of-line separator         </td>
      </tr>
   </tbody>
</table>
