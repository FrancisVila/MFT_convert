{
    "title": "Transfer CFT messages:  CFTE ",
    "linkTitle": "CFTE messages",
    "weight": "290"
}This topic lists the CFTExx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: <span class="code">CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started</span>

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTE09I"></span>CFTE09I CFT Stop complete</p>
<p>CFTE09I CFT stop complete _ &amp;str</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Transfer
CFT has been shut down (following an error or request).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
   <tbody>
      <tr>
         <td><p>V23 format</p>
<p>V24 format</p>
<p>Information</p>         </td>
         <td><p><span id="CFTE09I"></span>CFTE11I Node &amp;node state set to DISABLED, Shutting the Monitor</p>
<p>CFTE11I Node &amp;node state set to DISABLED, Shutting the Monitor</p>         </td>
      </tr>
      <tr>
         <td><p>Explanation</p>         </td>
         <td><p>Transfer
CFT is shutting down.</p>         </td>
      </tr>
   </tbody>
</table>