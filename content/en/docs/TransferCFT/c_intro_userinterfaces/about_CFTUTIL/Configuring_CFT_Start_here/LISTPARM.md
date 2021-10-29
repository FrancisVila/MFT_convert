{
    "title": "Listing parameters - LISTPARM ",
    "linkTitle": "LISTPARM - List parameters",
    "weight": "500"
}This page describes the LISTPARM command. You can use this command
to query Transfer CFT parameters.

Command syntax: [LISTPARM](../../command_summary)

Use this command to query Transfer CFT parameters. The TYPE parameter selects the object type.

In the absence of a previous CONFIG TYPE = OUTPUT command,
the execution report is written on the standard CFTUTIL program output.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../Parameter_index/id.htm">ID</a> </p>         </td>
         <td width="52.108%">            <p>Identifier of the Transfer CFT command selected using the
TYPE parameter.</p>
            <p>Used to limit the query to this identifier.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../Parameter_index/part.htm">PART</a> </p>
            <p>For TYPE = IDF</p>         </td>
         <td width="52.108%">            <p>Partner identifier.</p>
            <p>Used to limit the search to the IDFs defined in the CFTIDF
objects, relative to this partner.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../Parameter_index/type.htm">TYPE</a></p>         </td>
         <td width="52.108%">            <p>Defines the type of object to be selected.</p>
            <p>TYPE can take the predefined values indicated in the <a href="#Type_table">Type table</a>.</p>         </td>
      </tr>
   </tbody>
</table>

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>LISTPARM       TYPE
= ALL</p>         </td>
      </tr>
   </tbody>
</table>

Displays all the parameters contained in the PARAMETER file.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>LISTPARM         TYPE
= SEND</p>         </td>
      </tr>
   </tbody>
</table>

Displays the parameters of all the CFTSEND objects configured.

#### <span id="Type_table"></span>Type table

TYPE can take the predefined values indicated in the table below.

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>            <p>ACCNT </p>         </td>
         <td>            <p>Used to query statistical file parameters.<br />
These parameters are submitted when CFTACCNT objects are entered.</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ALL </p>         </td>
         <td>            <p>Used to query all the parameters indicated in the PARAMETER
file .</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>AUTH </p>         </td>
         <td>            <p>Used to query file authorization lists.<br />
These lists are customized by the CFTAUTH objects. </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>CAT </p>         </td>
         <td>            <p>Used to query catalog parameters.<br />
These parameters are submitted when CFTCAT objects are entered.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>COM </p>         </td>
         <td>            <p>Used to query communication media parameters.<br />
These parameters are submitted when CFTCOM objects are entered </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>IDF </p>         </td>
         <td>            <p>Used to query file "network" identifiers.<br />
Identifiers are customized by the CFTIDF objects. </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>LOG </p>         </td>
         <td>            <p>Used to query log file parameters.<br />
These parameters are submitted when CFTLOG objects are entered. </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>NET </p>         </td>
         <td>            <p>Used to query network characteristic parameters.<br />
These parameters are submitted when CFTNET objects are entered and differ
according to the type of network configured. </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>PARM </p>         </td>
         <td>            <p>Used to query general parameters.<br />
These parameters are submitted when CFTPARM objects are entered. </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>PROT </p>         </td>
         <td>            <p>Used to query protocol parameters.<br />
These parameters are submitted when CFTPROT objects are entered and differ
according to the protocol configured. </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>RECV </p>         </td>
         <td>            <p>Used to query the parameters of the files to be received.<br />
These parameters are submitted when CFTRECV objects are entered. </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>SEND </p>         </td>
         <td>            <p>Used to query the parameters of the files to be sent.<br />
These parameters are submitted when CFTSEND objects are entered.</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>XLATE </p>         </td>
         <td>            <p>Used to query translation tables.<br />
Translation tables are customized by the CFTXLATE objects. </p>         </td>
      </tr>
   </tbody>
</table>
