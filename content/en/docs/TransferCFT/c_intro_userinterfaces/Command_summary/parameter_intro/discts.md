{
    "title": "discts",
    "linkTitle": "discts",
    "weight": "770"
}### <span id="discts"></span>discts

#### CFTPROT

\[DISCTS =
{ <u>see the table</u> | n} \] {0..3600}  

The synchronous connection time as managed by Transfer CFT. If Transfer CFT does not receive requests to communicate in discts (the number of seconds), Transfer CFT closes the session.

The session established for a transfer remains active for DISCTS seconds
after the completion of this transfer. If at the end of this timeout,
no new transfer has been received, the connection is freed by the ABORT
FPDU.

If the value is 0, the wait time-out is infinite.

The default value (in seconds) depends on the protocol and is indicated
in the following table.

Default values are:

<table border="1" cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Protocol </th>
         <th>Default value </th>
      </tr>
   </thead>
      <tr valign="middle">
         <td valign="top" width="33%">
            <p>PeSIT  ANY profile</p>
         </td>
         <td valign="top" width="67%">
            <p>60</p>
         </td>
      </tr>
      <tr valign="middle">
         <td valign="top" width="33%">
            <p>ODETTE </p>
         </td>
         <td valign="top" width="67%">
            <p>65 </p>
         </td>
      </tr>
</table>

[Return to Command index](../../)
