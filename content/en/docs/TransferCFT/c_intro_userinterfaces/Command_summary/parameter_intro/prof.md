{
    "title": "prof",
    "linkTitle": "prof",
    "weight": "2730"
}### <span id="prof"></span>prof

#### CFTPROT

TYPE = PeSIT

\[PROF = {SIT | CFT | EXTERN | ANY | DMZ }\]

PeSIT
D or E protocol profile

The profile options are:

SIT profile: the
PeSIT is then used in the SIT network context. This is the same in PeSIT version D and version E. It provides synchronization point management but does
not manage:

-   segmentation:
    the value of the SEGMENT parameter must be set to NO (SEGMENT = NO), or
-   multi-records:
    the value of the MULTART parameter must be set to NO (MULTART = NO), or
-   compression:
    the RCOMP and SCOMP parameters are not applicable, or receive
    transfer requests

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">A sender
in the PeSIT SIT profile cannot segment a record sent in several data
FPDUs or group several records sent in the same data FPDU.</td>
</tr>
</tbody>
</table>

EXTERN profile:
Corresponds to the “non-SIT” (external to SIT network) standardized definition
of the PeSIT version D protocol.

CFT profile: The
PeSIT version D protocol is used outside the context of the SIT network,
the partner also having a Transfer CFT. Its functionality level is greater than the PeSIT
D EXTERN profile specifications.

ANY profile: Corresponds
to the “non-SIT” (external to SIT network) standardized definition of
the PeSIT version E protocol. This profile includes Transfer CFT profile facilities
as standard.

Additional facilities are provided between two Transfer
CFTs, while conforming with the PeSIT E standard.
These facilities are based on the use of the PI 99 (free PI).

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In server mode, the PROF parameter
can take either the EXTERN, CFT, or ANY values (corresponding to the “non-SIT”
profiles): indeed, in server mode, the <span>Transfer CFT</span> automatically
adapts itself to the “non-SIT” profile proposed by the requesting partner.</td>
</tr>
</tbody>
</table>

[Return to Command index](../../)
