{
    "title": "prof",
    "linkTitle": "prof",
    "weight": "2700"
}<span id="prof"></span>

### <span class="mc-variable System.Title variable">prof</span>

#### CFTPROT

TYPE = PeSIT

\[PROF = {SIT | CFT | EXTERN | ANY | DMZ }\]

PeSIT
D or E protocol profile

The profile options are:

<span class="bold_in_para">SIT profile</span>: the
PeSIT is then used in the SIT network context. This is the same in PeSIT version D and version E. It provides synchronization point management but does
not manage:

-   segmentation:
    the value of the SEGMENT parameter must be set to NO (SEGMENT = NO), or
-   multi-records:
    the value of the MULTART parameter must be set to NO (MULTART = NO), or
-   compression:
    the RCOMP and SCOMP parameters are not applicable, or receive
    transfer requests

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>A sender
in the PeSIT SIT profile cannot segment a record sent in several data
FPDUs or group several records sent in the same data FPDU.         </td>
      </tr>
   </tbody>
</table>

<span class="bold_in_para">EXTERN profile</span>:
Corresponds to the “non-SIT” (external to SIT network) standardized definition
of the PeSIT version D protocol.

<span class="bold_in_para">CFT profile</span>: The
PeSIT version D protocol is used outside the context of the SIT network,
the partner also having a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. Its functionality level is greater than the PeSIT
D EXTERN profile specifications.

<span class="bold_in_para">ANY profile</span>: Corresponds
to the “non-SIT” (external to SIT network) standardized definition of
the PeSIT version E protocol. This profile includes <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> profile facilities
as standard.

Additional facilities are provided between two Transfer
CFTs, while conforming with the PeSIT E standard.
These facilities are based on the use of the PI 99 (free PI).

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>In server mode, the PROF parameter
can take either the EXTERN, CFT, or ANY values (corresponding to the “non-SIT”
profiles): indeed, in server mode, the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> automatically
adapts itself to the “non-SIT” profile proposed by the requesting partner.         </td>
      </tr>
   </tbody>
</table>

[Return to Command index](../../)