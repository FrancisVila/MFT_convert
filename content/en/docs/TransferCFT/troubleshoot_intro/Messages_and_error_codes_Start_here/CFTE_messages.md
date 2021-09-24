{
    "title": "CFTE messages",
    "linkTitle": "CFTE messages",
    "weight": "310"
}# Transfer CFT messages:  CFTE

This topic lists the CFTExx (CFT xnnx) messages and provides the type, a description, consequence, and corrective actions when applicable.

**Message format**

Earlier versions of Transfer CFT used a different message format than version 3.1.3 and higher. This document displays both formats when applicable and available, otherwise only the v23 is used. Using the CFTLOG Format = V24 setting, the log displays as shown:

CFTXXX: fixed text message &lt;variables>

**Example**

CFTLOG FORMAT=\[V23,V24\]

For V23: CFTT57I PART=&part IDF=&idf IDT=&idt &str transfer started

For V24: `CFTT57I &str transfer started   <IDTU=&idtu PART=&part IDF=&idf IDT=&idt>`

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
            <p><a name="CFTE09I"></a>CFTE09I CFT Stop complete</p>
            <p>CFTE09I CFT stop complete _ &amp;str</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Transfer 
 CFT has been shut down (following an error or request).</p>
         </td>
      </tr>
</table>

 

<table border="1" cellspacing="0">
   <col/>
   <col/>
      <tr valign="top">
         <td width="20%">
            <p>V23 format</p>
            <p>V24 format</p>
            <p>Information</p>
         </td>
         <td width="80%">
            <p><a name="CFTE09I"></a>CFTE11I Node &amp;node state set to DISABLED, Shutting the Monitor</p>
            <p>CFTE11I Node &amp;node state set to DISABLED, Shutting the Monitor</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="20%">
            <p>Explanation</p>
         </td>
         <td width="80%">
            <p>Transfer 
 CFT is shutting down.</p>
         </td>
      </tr>
</table>
