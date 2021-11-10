{
    "title": "LISTCAT - List catalog  contents",
    "linkTitle": "LISTCAT - List catalog contents",
    "weight": "300"
}This page describes how to list the catalog contents using command
line operations. The LISTCAT command is used to query the information
associated with the selected transfers, recorded in the Transfer CFT catalog.

Depending on the value of the CONTENT parameter, the information is
displayed in the form of:

-   Lists in which
    only the most important features of transfers appear CONTENT = BRIEF default
    value
-   Pages in which
    all the features of transfers appear CONTENT = FULL

See also, [LISTCAT - Brief/Full catalog listings](../brief_catalog_listing).

In the absence of a previous command CONFIG TYPE = OUTPUT, this information
or the execution report for a syntax error, no associated information,
and so on, is written on the standard output of the task.

This command is used to display output for:

-   Static transfer
    information associated with the parameters of the SEND and RECV commands
-   Dynamic transfer
    information such as the:

<!-- -->

-   Transfer status
-   Number of items
    transferred
-   Compression
    factor, etc.

The command parameters are selection criteria. See also, [LISTCAT/DISPLAY - Statistical variables](../listcat_filter_variables).

## Parameter descriptions

Command syntax: LISTCAT

For the definition of the states of a transfer,
refer to [Transfer control commands](../../../../concepts/transfer_command_overview/transfer_control_commands).

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Use this command to query the information associated with
the selected transfers, recorded in the Transfer CFT catalog.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/content">CONTENT</a> </p>         </td>
         <td><p>Used to obtain part or all of the information of a catalog
entry.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/datetimemax">DATETIMEMAX</a>         </td>
         <td>Use to display catalog transfers that happened on or before this end date and time according to the transfer record creation (DATEK, TIMEK).         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/datetimemin">DATETIMEMIN</a>         </td>
         <td>Use to display catalog transfers that happened on or after this start date and time according to the transfer record creation (DATEK, TIMEK).         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/diagi">DIAGI</a>         </td>
         <td>Define the diagi catalog transfer field display.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/direct">DIRECT</a> </p>         </td>
         <td><p>Transfer direction.</p>
<p>The possible values are:</p>
<ul>
<li>BOTH <em>or</em> *</li>
<li>SEND</li>
<li>RECV</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>FILE = see the comment</p>         </td>
         <td><p>Complete name or logical name of the catalog file.</p>
<p>The default value for this parameter is fixed. </p>
<p>To designate the current catalog of the monitor, this parameter
should be defined with the filename set in the FNAME parameter of the
CFTCAT command.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/ida#ida">IDA</a> </p>         </td>
         <td><p>Local identifier of the transfer assigned by the user or
the user application.</p>
<p>Several catalog entries may be associated with a given
IDA.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/idf#idf_CFTCAT">IDF</a> </p>         </td>
         <td><p>Model file identifier.</p>
<p>Several catalog entries may be associated with a given
IDF.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/idu#idt">IDT</a> </p>         </td>
         <td><p>Transfer identifier.</p>
<p>Identifies a transfer for a given partner and transfer
direction.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/idtu">IDTU</a> </p>         </td>
         <td><p>Unique local transfer reference identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/npart">NPART</a> </p>         </td>
         <td><p>Network identifier of the partner(s) for the selected transfers.</p>
<p>The information displayed for LISTCAT CONTENT = BRIEF is
different, according to whether the NPART parameter is defined or not
(see the paragraphs below).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>         </td>
         <td><p>Partner identifier for the selected transfers.</p>
<p>The value of this parameter may be:</p>
<ul>
<li>An identifier</li>
<li>A mask</li>
<li>Omitted*</li>
</ul>
<p>If the NPART parameter is defined, the PART parameter is
ignored.</p>         </td>
      </tr>
      <tr>
         <td><a href="../../../command_summary/parameter_intro/sortby">SORTBY</a>         </td>
         <td>Sorts the LISTCAT command information in an alphabetical/alphanumberic order.         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/state">STATE</a></p>         </td>
         <td><p>Possible states of a catalog entry.</p>
<p>The catalog entries in the state indicated by this parameter
are selected. Any combination of the various states (D,C,H,K,T,X) is authorized.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>         </td>
         <td><p>Type of catalog entry.</p>
<p>If TYPE = * <em>or</em> ALL, no selection is made: all transfers present
in the catalog (files, messages, reply messages) are displayed if they
fulfill the selection criteria which may be defined by other parameters.</p>         </td>
      </tr>
   </tbody>
</table>

### Examples

Example 1


    LISTCAT TYPE = ALL, PART = HQ, STATE = DC

Displays the most important information (CONTENT=BRIEF by default) concerning
all transfers (TYPE=ALL) sent to or received from (DIRECT=BOTH by default)
the partner (PART = HQ), the states of which are "Available"
or "in Process" (STATE=DC).

Example 2


    LISTCAT TYPE = FILE, DIRECT = SEND, PART = PARIS5

Displays the most important information (CONTENT=BRIEF by default) concerning
the file transfers (TYPE=FILE) sent (DIRECT=SEND) to the partner (PART)
PARIS5, all states included (STATE=\* by default).

<span id="sortby_example"></span>Example 3


    LISTCAT SORTBY=IDTU

Displays the records by IDTU. This can be useful because the catalog's compact behavior takes advantage of unused records meaning the IDTU may not display in order.

## LISTCAT CONTENT = COMMUT

LISTCAT CONTENT = COMMUT

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Heading         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1 </p>         </td>
         <td><p>Intermediate transfer (IPART) </p>         </td>
      </tr>
      <tr>
         <td><p>2 </p>         </td>
         <td><p>State transfer<br />
The DTSA characters represent:</p>
<ul>
<li>Direction
     =     S/R    
(Send/Receive)</li>
<li>Type    
=     F/M/R     (File/Message/Reply)</li>
<li>State    
=     D/C/H/K/T/X     (Disp/Current/Hold/Keep/Terminated/eXecuted)</li>
<li>Ack    
=     A     (Acknowledge)</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>If the UCONF compatibility option is set to the default value (no), the format is DTSAPP to include Phase and PhaseStep. For more information, see Backward compatibility.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>3 </p>         </td>
         <td><p>File network identifier (NFNAME) </p>         </td>
      </tr>
      <tr>
         <td><p>4 </p>         </td>
         <td><p>Transfer protocol identifier (NIDT) </p>         </td>
      </tr>
      <tr>
         <td><p>5 </p>         </td>
         <td><p>Local transfer identifier (IDTU) </p>         </td>
      </tr>
      <tr>
         <td><p>6 </p>         </td>
         <td><p>Transfer CFT internal diagnostic code (DIAGI) </p>         </td>
      </tr>
   </tbody>
</table>

## LISTCAT CONTENT = EXTEND

LISTCAT CONTENT = EXTEND 

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Heading         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Meaning         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>1 </p>         </td>
         <td><p>Local partner identifier described in the CFTPART (ID)
or CFTDEST command (one of the PARTS of the broadcasting list) </p>         </td>
      </tr>
      <tr>
         <td><p>2 </p>         </td>
         <td><p>Transfer state<br />
The DTSA characters mean:</p>
<ul>
<li>Direction
     =     S/R    
(Send/Receive)</li>
<li>Type    
=     F/M/R     (File/Message/Reply)</li>
<li>State    
=     D/C/H/K/T/X     (Disp/Current/Hold/Keep/Terminated/eXecuted)</li>
<li>Ack    
=     A     (Acknowledge)</li>
</ul>
<blockquote>
<p><strong>Note:</strong></p>
<p>If the UCONF compatibility option is set to the default value (no), the format is DTSAPP to include Phase and PhaseStep. For more information, see Backward compatibility.</p>
</blockquote>         </td>
      </tr>
      <tr>
         <td><p>3 </p>         </td>
         <td><p>File identifier (IDF) </p>         </td>
      </tr>
      <tr>
         <td><p>4 </p>         </td>
         <td><p>Transfer identifier (IDT) </p>         </td>
      </tr>
      <tr>
         <td><p>5 </p>         </td>
         <td><p>Identifier of the application associated to the transfer
(IDA) </p>         </td>
      </tr>
      <tr>
         <td><p>6 </p>         </td>
         <td><p>Requester ("R") or server ("S") mode </p>         </td>
      </tr>
      <tr>
         <td><p>7 </p>         </td>
         <td><p>Client security mode ("C") or server ("S")
mode </p>         </td>
      </tr>
      <tr>
         <td><p>8 </p>         </td>
         <td><p>Exits used<br />
The characters FAT represent:</p>
<ul>
<li>F: file exit ("x" if present)</li>
<li>A: directory
exit ("x" if present)</li>
<li>T: end
of transfer exit ("x" if present)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>9 </p>         </td>
         <td><p>Use of an end of transfer procedure ("x" if
present) </p>         </td>
      </tr>
      <tr>
         <td><p>10 </p>         </td>
         <td><p>Transfer CFT internal diagnostic (DIAGI) </p>         </td>
      </tr>
   </tbody>
</table>
