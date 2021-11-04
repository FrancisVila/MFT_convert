{
    "title": "mode",
    "linkTitle": "mode",
    "weight": "2000"
}<span id="mode"></span>

### mode

#### All <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> commands <span style="font-weight: normal;"> </span>

\[MODE = { <u>REPLACE</u> | CREATE | DELETE }\]

Action to do in the parameter or partner database. This parameter applies
to all commands that affect <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> databases. Possible values:

-   REPLACE
    <span style="font-weight: normal;">(Default value)</span>
-   CREATE
-   DELETE

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td><span style="font-weight: normal;">Applicable for CFTACCNT, CFTAUTH, CFTCAT, CFTCOM, CFTDEST, CFTEXIT, CFTFILE, CFTIDF,
CFTLOG, CFTNET, CFTPARM, CFTPART, CFTPROT, CFTRECV, CFTSEND,
CFTTCP, CFTTRACE, CFTXLATE.</span>         </td>
      </tr>
   </tbody>
</table>

#### DISPLAY

\[MODE = { ANY | COLUMN | LINE } \]

-   ANY / COLUMN: Displays in a column format
-   Line: Displays in a more horizontal and spaced format

 

#### TURN

\[MODE = { START | CREATE | ACT | INACT }
\]

-   INACT: temporarily stops automated calls to a given site
-   ACT: reactivates automated calls after the INACT command
-   START: manually triggers a single connection for changing direction
-   CREATE: triggers an automatic, cyclic TURN

#### INACT, ACT

**\[MODE =
{<u>BOTH</u> | REQUESTER | SERVER} \]**

Mode to be reactivated:

-   BOTH
-   REQUESTER
-   SERVER

You can use the shortcuts B, R, and S in place of the keywords.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The MODE parameter is absolute. If you run ACT MODE=SERVER followed by
ACT MODE=REQUESTER, the partner is not reactivated in both modes,
only in REQUESTER mode (corresponding to the most recent command).         </td>
      </tr>
   </tbody>
</table>

The CFTPART command’s STATE parameter is set to:

-   ACTIVEBOTH after
    execution of ACT MODE=BOTH
-   ACTIVESERV after
    execution of ACT MODE=REQUESTER
-   ACTIVEREQ after
    execution of ACT MODE=SERVER

#### PKIENTITY

\[MODE = { <u>REPLACE</u> | CREATE | DELETE }\]

Action to do in the PKI database. Possible values:

-   REPLACE
    <span style="font-weight: normal;">(Default)</span>
-   CREATE
-   DELETE

[Return to Command index](../../)