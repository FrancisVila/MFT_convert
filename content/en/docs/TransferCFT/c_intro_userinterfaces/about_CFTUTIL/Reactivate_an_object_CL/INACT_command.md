{
    "title": "INACT - Deactivating objects",
    "linkTitle": "INACT - Deactivating objects",
    "weight": "290"
}# <span id="INACT___Deactivate_objects"></span> INACT - Deactivate an object

<span id="kanchor67"></span>

This page describes the INACT command and its parameters. You can use the INACT command to deactivate:

-   One or more partners (CFTPART)
-   Sentinel notifications
-   CRON object (CFTCRON)
-   Folder object (CFTFOLDER)

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top"> 
 This command cannot be applied to partners whose definition was provided 
 or modified by a directory EXIT.         </td>
      </tr>
</table>

Command guide: [INACT](../../../command_summary)

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier for the object to be deactivated. To deactivate several objects with a single command, 
 use wildcard 
 characters or meta characters.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>
         </td>
         <td>
            <p>Object to be deactivated:</p>
            <ul>
               <li>PART               </li>
               <li>TRK               </li>
               <li>CRON               </li>
               <li>FOLDER               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/mode">MODE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Mode to be deactivated on partners (only when TYPE=PART object):</p>
            <ul>
               <li>BOTH (default)               </li>
               <li>REQUESTER               </li>
               <li>SERVER               </li>
            </ul>
            <p>You can use the shortcuts B, R and S in place of the keywords.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/force">FORCE</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <ul>
               <li>YES: Stops any transfers in progress involving the deactivated 
 partners.               </li>
               <li>NO: Default value, transfers progress normally.                </li>
            </ul>
         </td>
      </tr>
   </tbody>
</table>

## Using the INACT command

Using CFTUTIL you can perform the following commands.

### Deactivate a partner

Syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=PART,ID=&lt;CFTPART_ID&gt;,MODE=&lt;mode&gt;,FORCE=&lt;NO | YES&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

Where:

-   `CFTPART_ID` is the identifier of the partner to deactivate. To deactivate several partners with a single command, use wildcard characters or meta characters.
-   Mode is the mode to be deactivated, with values: "BOTH" , "B", "REQUESTER", "R" , "SERVER", "S"
-   When FORCE is set to YES, stops any transfers in progress involving the deactivated partners.

Example

to deactivate the partner called PARIS in requester mode, enter:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=PART, ID=PARIS, MODE=REQUESTER</p>
         </td>
      </tr>
   </tbody>
</table>

Returning the following output:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTU20I Part=PARIS : ACTIVEBOTH -&gt; ACTIVESERV</p>
            <p>CFTU00I INACT _ Correct (TYPE=PART,ID=PARIS,MODE=REQUESTER)</p>
         </td>
      </tr>
   </tbody>
</table>

When a partner is deactivated, transfers awaiting processing are:

-   Suspended in requester mode
-   Refused in server mode

The state of a transfer request awaiting execution in requester mode
for a deactivated partner remains D,
with a diagnostic code 430 and a protocol diagnostic INACT.

The state of a transfer request awaiting execution in server mode for
a deactivated partner remains D,
with a diagnostic code 930 and a protocol diagnostic RCO 312, or ABO 312
if the session is already open.

The state of transfers that are interrupted by an INACT command when
FORCE=YES is H, with a diagnostic
code 121 and a protocol diagnostic OPER.

### Deactivate Sentinel notifications

Syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=TRK</p>
         </td>
      </tr>
   </tbody>
</table>

All notifications to Sentinel are suspended.

### Deactivate cron object

Syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=CRON,ID=&lt;CFTCRON_ID&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

Where `CFTCRON_ID` is the identifier of the CRON object to deactivate. To deactivate several CRON objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the CRON referenced by CRON1, enter:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=CRON,ID=CRON1</p>
         </td>
      </tr>
   </tbody>
</table>

Returning the following output:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTU20I Cronjob=CRON1 : ACTIVE -&gt; NOACTIVE</p>
            <p>CFTU00I INACT _ Correct (id=cron1,type=cron)</p>
         </td>
      </tr>
   </tbody>
</table>

### Deactivate folder object

Syntax

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=FOLDER,ID=&lt;CFTFOLDER_ID&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

Where `CFTFOLDER_ID` is the identifier of the folder object to deactivate. To deactivate several folder objects with a single command, use wildcard characters or meta characters.

Example

To deactivate the folder referenced by USER1, enter:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INACT TYPE=FOLDER,ID=USER1</p>
         </td>
      </tr>
   </tbody>
</table>

Returning the following output:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTU20I Folder=USER1 : ACTIVE -&gt; NOACTIVE</p>
            <p>CFTU00I INACT _ Correct (TYPE=FOLDER,ID=USER1)</p>
         </td>
      </tr>
   </tbody>
</table>
