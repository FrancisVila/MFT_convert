{
    "title": "Broadcast lists - CFTDEST ",
    "linkTitle": "Broadcast lists - CFTDEST",
    "weight": "200"
}This topic describes how to manages the list of partners for distribute/collect
operations using the CFTDEST object.

Related
topics

-   Command syntax
    [CFTDEST](../../../command_summary#CFTDEST)
-   Object concepts
    Defining
    broadcasting lists

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/exec#exec_CFTDEST">EXEC</a></p>         </td>
         <td><p>End of transfer procedure submit mode type.</p>
<p>When all transfers are terminated, an end of transfer procedure
is submitted. The symbolic variables are submitted in line with the generic
record. For example, the &amp;PART variable is substituted with the CFTDEST
command identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/fname#fname_CFTDEST">FNAME</a> </p>         </td>
         <td><p>Name of the file in which the list of the identifiers of
the various partners, each corresponding to one value of the ID parameter
of a CFTPART command, is defined.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/for">FOR</a></p>         </td>
         <td><p>Control of the use of the partner list.</p>
<p>The value defined can be:</p>
<ul>
<li>LOCAL:
the list of partners is used locally for broadcasting (send transfers)
or collecting (receive transfers) the file (or message) concerned</li>
<li>COMMUT:
the local Transfer CFT monitor performs the broadcasting as an intermediate
site</li>
</ul>
<ul>
<li>BOTH:
includes both the LOCAL and COMMUT facilities</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>         </td>
         <td><p>Identifier of the list of partners.</p>
<p>This identifier must be unique. You cannot have several
CFTDEST with the same ID.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/nopart">NOPART</a></p>         </td>
         <td><p>Do
not complete this field if you completed the fname field.</p>
<p>Select the action to perform when one of the partners is
not defined. Abort is the default
value.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../command_summary/parameter_intro/part">PART</a> </p>         </td>
         <td><p>Explicit list of the identifiers of the various partners
(each corresponding to one value of the ID parameter of a CFTPART command).</p>
<p>If no partner is defined (CFTPART) no transfer (broadcasting
or collection) can be performed.</p>         </td>
      </tr>
   </tbody>
</table>
