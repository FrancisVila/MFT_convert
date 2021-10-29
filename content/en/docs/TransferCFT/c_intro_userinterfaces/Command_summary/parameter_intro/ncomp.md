{
    "title": "ncomp",
    "linkTitle": "ncomp",
    "weight": "2150"
}### <span id="ncomp"></span>ncomp

#### CFTSEND, CFTRECV, SEND, RECV

\[NCOMP = { 0 | 15 }\]

PeSIT D CFT profile, PeSIT E

Compression of on-line data requested.

This parameter is used when the value of the SCOMP or RCOMP parameter
of the CFTPROT object is too high for the file type.

The authorized values and the default values for the NCOMP parameter
are the same as for the SCOMP or RCOMP parameter of the CFTPROT object.
For a transfer, the combination of the values taken for these two parameters
is used as a basis for the on-line data compression protocol negotiation.

<table data-cellspacing="0" width="90%">
   <tbody>
      <tr class="odd" data-valign="top">
         <td width="26%">            <p>PeSIT D CFT profile<br />
<br />
PeSIT E</p>         </td>
         <td width="74%">            <p>This parameter should only be used for transfers in PeSIT
(with the profile or version indicated when the value of the SCOMP parameter
of the CFTPROT command is too high for the model file in question).</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td width="26%">            <p>ODETTE</p>         </td>
         <td width="74%">            <p>This parameter is used to inhibit compression
for a send transfer following a connection phase in which compression
has been negotiated to 1 (SCOMP and/or RCOMP parameters of CFTPROT
set to 1).</p>         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../)
