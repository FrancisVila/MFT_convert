{
    "title": "RESUME - Retrieving a blocked request",
    "linkTitle": "RESUME - Retrieving a blocked request",
    "weight": "360"
}# <span id="kanchor53"></span><span id="Title"></span>RESUME - Retrieve a blocked transfer

This topic describes the <span id="About_the_RESUME_Command"></span>RESUME
command. This command retrieves, in server mode, a blocked send request
that has a *hold* phasestep, and has a diagnostic codes other than zero.

The requester may either:

-   Restart the receive
    operation, or
-   Start a new receive
    operation

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td colspan="2" rowspan="1">
            <p>Use this command to retrieve, in server mode, a blocked 
 send request with the hold phasestep, the diagnostic codes of which 
 are not null.</p>
            <p>This command resets the diagnostic code to 0 and the diagnostic 
 code to HOLD. </p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p><a href="../../../command_summary/parameter_intro/blknum">BLKNUM</a> </p>
         </td>
         <td>
            <p>Catalog block number. If the values '*' or ' ' are used 
 then all transfers are selected regardless of the block that they belong 
 to.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer direction for the requests in question.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/ida">IDA</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Local identifier of the transfer assigned by the user or 
 user application.</p>
            <p>Several catalog entries may be associated with a given 
 IDA. There is no default value.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Model file identifier.</p>
            <p>Several catalog entries may be associated with a given 
 IDF. There is no default value.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idu">IDT</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer identifier.</p>
            <p>This identifies a transfer for a given partner. The value 
 ‘<b>*</b>’ means that no selection is required using the IDT parameter 
 (default value).</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer local counter identifier. </p>
         </td>
      </tr>
      <tr valign="top">
         <td><a href="kdate.htm">KDATE</a>
         </td>
         <td> Command deposit date.         </td>
      </tr>
      <tr valign="top">
         <td><a href="ktime.htm">KTIME</a>
         </td>
         <td>Command deposit time.         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>
            <p>(Mandatory)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Partner identifier.</p>
            <p>The associated value of this parameter may be:</p>
            <ul>
               <li><i>identifier</i>: 
 the command only concerns the transfers with this partner,               </li>
               <li><i>mask</i>: 
 the command concerns the transfers with the partners, whose identifiers 
 correspond to this mask.               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td><a href="phase.htm">PHASE</a>
         </td>
         <td> Phase of a catalog entry.         </td>
      </tr>
      <tr valign="top">
         <td><a href="phasestep.htm">PHASESTEP</a>
         </td>
         <td>Phase step of a catalog entry.         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/scope">SCOPE</a>
         </td>
         <td>Scope &lt;PARENT&gt;  ('PARENT','ALL','CHILDREN').         </td>
      </tr>
      <tr valign="top">
         <td><a href="../../../command_summary/parameter_intro/state">STATE</a>
         </td>
         <td>Transfer request state.         </td>
      </tr>
   </tbody>
</table>

#### Example 1

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>RESUME</p>
            <p>PART = NEW_YORK5</p>
         </td>
      </tr>
   </tbody>
</table>

Retrieval of all the transfers in server mode with partner NEW\_YORK5.

#### Example 2

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>RESUME</p>
            <p>PART = NEW_YORK5,</p>
            <p>IDF = PAY</p>
         </td>
      </tr>
   </tbody>
</table>

Retrieval of the transfers in server mode with partner NEW\_YORK5 for
the PAYs IDF.
