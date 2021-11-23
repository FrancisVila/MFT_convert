{
    "title": " Transfer CFT messages: CFTW",
    "linkTitle": "CFTW messages",
    "weight": "380"
}This topic lists the CFTWxx and CFTXxx messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: `CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started`

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW01W"></span>CFTW01W PART=&amp;part
IDF=&amp;idf IDT=&amp;idt Temporary
file &amp;file deleted</p>
<p>CFTW01W File &amp;fname deleted &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;file temporary file was deleted at the end of
the transfer. The name of this file is declared in the WFNAME parameter
of the CFTSEND and CFTRECV commands.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW02W"></span>CFTW02W CFTSEND &amp;idsend override SEND parameters</p>
<p>CFTW02W CFTSEND &amp;id override SEND parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The parameters of the SEND command are overridden by the parameters
in the associated CFTSEND command.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW03W"></span>CFTW03W _ Send command: Unauthorized usage of IDF =
&amp;idf</p>
<p>CFTW03W _ Send Command : Unauthorized usage on IDF = &amp;id</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;idf IDF is not authorized for the SEND command. Check your software key restrictions.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW04W"></span>CFTW04W _ Recv command: Unauthorized usage on IDF =
&amp;idf</p>
<p>CFTW04W _ Recv Command : Unauthorized usage on IDF = &amp;id</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The &amp;idf IDF is not authorized for the RECV command. See
the restrictions concerning the value of your software key.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW05W"></span>CFTW05W PART=&amp;part IDF = &amp;idf Temporary file
unknown, WFNAME not defined in SEND</p>
<p>CFTW05W PART=&amp;part IDF=&amp;idf Temporary file unknown, WFNAME not defined in SEND</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The WFNAME was not set in the CFTSEND command when preparing
a transfer requiring additional processing
and sending a group of files.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Modify the parameter settings using a different IDF for this
type of transfer.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW07W"></span>CFTW07W PART=&amp;part IDF = &amp;idf _ SELFNAME not
authorized for COPY</p>
<p>CFTW07W PART=&amp;par IDF=&amp;idf _ SELFNAME not authorized for COPY\n</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>You cannot use a selection file when implementing additional
processing prior to a transfer (IEBCOPY with MVS for example).</p>         </td>
      </tr>
      <tr>
         <td><p>Consequence</p>         </td>
         <td><p>The transfer is not triggered.</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Do not use a selection file; you can, however, specify a generic
file name (FNAME= #FIL1*, FNAME= #TFILM*).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Warning</p>         </td>
         <td><p><span id="CFTW08W"></span>CFTW08W CFTRECV &amp;idrecv override RECV parameters</p>
<p>CFTW08W CFTRECV &amp;id override RECV parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>The RECV command parameters are overridden by the parameters
set in the associated CFTRECV command.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p> </p>
<p>V24 format</p>
<p> </p>
<p>Information</p>         </td>
         <td><p><span id="CFTW09I"></span>CFTW09I PART=&amp;part IDF=&amp;idf IDT=&amp;idt CFTSEND &amp;idf NIDF=&amp;nidf XLATE=&amp;xlate</p>
<p>CFTW09I PART=&amp;part IDF=&amp;idf IDT=&amp;idt CFTRECV &amp;idf NIDF=&amp;nidf XLATE=&amp;xlate</p>
<p>CFTW09I CFTSEND &amp;idf &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt NIDF=&amp;nidf XLATE=&amp;xlate&gt;</p>
<p>CFTW09I CFTRECV &amp;idf &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt NIDF=&amp;nidf XLATE=&amp;xlate&gt;</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Indicates the ID of the CFTSEND or CFTRECV that was actually
used.</p>
<p><strong>Example</strong></p>
<p>CFTW09I CFTSEND TRTR &lt;IDTU=A0000024 PART=SERVER IDF=TRTR IDT=I0714504 NIDF=TRTR XLATE=CONV1&gt;</p>         </td>
      </tr>
   </tbody>
</table>
