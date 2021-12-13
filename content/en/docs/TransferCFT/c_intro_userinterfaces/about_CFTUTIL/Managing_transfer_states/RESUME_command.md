{
    "title": "RESUME  - Retrieve a blocked transfer",
    "linkTitle": "RESUME &#45; Retrieving a blocked request",
    "weight": "350"
}This topic describes the <span id="About_the_RESUME_Command"></span>RESUME
command. This command retrieves, in server mode, a blocked send request
that has a *hold* phasestep, and has a diagnostic codes other than zero.

The *requester* may either:

-   Restart the receive
    operation, or
-   Start a new receive
    operation

<table>
         
         
         
   
   <thead>
      <tr>
<th >Parameter         </th>
<th >Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2" ><p>Use this command to retrieve, in server mode, a blocked
send request with the hold phasestep, the diagnostic codes of which
are not null.</p>
<p>This command resets the diagnostic code to 0 and the diagnostic
code to HOLD.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/blknum">BLKNUM</a> </p>         </td>
         <td  ><p>Catalog block number. If the values '*' or ' ' are used
then all transfers are selected regardless of the block that they belong
to.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p>         </td>
         <td  ><p>Transfer direction for the requests in question.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/ida">IDA</a> </p>         </td>
         <td  ><p>Local identifier of the transfer assigned by the user or
user application.</p>
<p>Several catalog entries may be associated with a given
IDA. There is no default value.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/idf">IDF</a> </p>         </td>
         <td  ><p>Model file identifier.</p>
<p>Several catalog entries may be associated with a given
IDF. There is no default value.</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/idu">IDT</a> </p>         </td>
         <td  ><p>Transfer identifier.</p>
<p>This identifies a transfer for a given partner. The value
‘<strong>*</strong>’ means that no selection is required using the IDT parameter
(default value).</p>         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p>         </td>
         <td  ><p>Transfer local counter identifier.</p>         </td>
      </tr>
      <tr>
         <td >KDATE         </td>
         <td  >Command deposit date.         </td>
      </tr>
      <tr>
         <td >KTIME         </td>
         <td  >Command deposit time.         </td>
      </tr>
      <tr>
         <td ><p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>
<p>(Mandatory)</p>         </td>
         <td  ><p>Partner identifier.</p>
<p>The associated value of this parameter may be:</p>
<ul>
<li><em>identifier</em>:
the command only concerns the transfers with this partner,</li>
<li><em>mask</em>:
the command concerns the transfers with the partners, whose identifiers
correspond to this mask.</li>
</ul>         </td>
      </tr>
      <tr>
         <td >PHASE         </td>
         <td  >Phase of a catalog entry.         </td>
      </tr>
      <tr>
         <td >PHASESTEP         </td>
         <td  >Phase step of a catalog entry.         </td>
      </tr>
      <tr>
         <td ><a href="../../../command_summary/parameter_intro/scope">SCOPE</a>         </td>
         <td  >Scope &lt;PARENT&gt;  ('PARENT','ALL','CHILDREN').         </td>
      </tr>
      <tr>
         <td ><a href="../../../command_summary/parameter_intro/state">STATE</a>         </td>
         <td  >Transfer request state.         </td>
      </tr>
   </tbody>
</table>

#### Example 1

```
RESUME
PART = NEW_YORK5
```

Retrieval of all the transfers in server mode with partner NEW\_YORK5.

#### Example 2

```
RESUME
PART = NEW_YORK5,
IDF = PAY
```

Retrieval of the transfers in server mode with partner NEW\_YORK5 for
the PAYs IDF.
