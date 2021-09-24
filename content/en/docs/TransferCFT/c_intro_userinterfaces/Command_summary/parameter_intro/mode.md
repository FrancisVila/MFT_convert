{
    "title": "mode",
    "linkTitle": "mode",
    "weight": "2030"
}### <span id="mode"></span>mode

#### All Transfer CFT commands  

\[MODE = { <u>REPLACE</u> | CREATE | DELETE }\]

Action to do in the parameter or partner database. This parameter applies
to all commands that affect Transfer CFT databases. Possible values:

-   REPLACE
    (Default value)
-   CREATE
-   DELETE

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"><span>Applicable for CFTACCNT, CFTAUTH, CFTCAT, CFTCOM, CFTDEST, CFTEXIT, CFTFILE, CFTIDF, 
 CFTLOG,  CFTNET, CFTPARM, CFTPART, CFTPROT, CFTRECV, CFTSEND, 
 CFTTCP, CFTTRACE,  CFTXLATE.</span>
         </td>
      </tr>
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

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The MODE parameter is absolute. If you run ACT MODE=SERVER followed by 
 ACT MODE=REQUESTER, the partner is not reactivated in both modes, 
 only in REQUESTER mode (corresponding to the most recent command).         </td>
      </tr>
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
    (Default)
-   CREATE
-   DELETE

[Return to Command index](../../)
