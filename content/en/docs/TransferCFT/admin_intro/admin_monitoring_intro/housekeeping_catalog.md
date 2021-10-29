{
    "title": "Housekeeping for  catalog and output files",
    "linkTitle": "Housekeeping for catalog and output files",
    "weight": "280"
}Transfer CFT provides a set of services to track activity related to transfers and their status as well as evaluating the system health.

This section describes how to manage the log, catalog, and output files to keep your system running smoothly.

## Catalog management

Transfer CFT records all file transfers in its local database, the catalog. The size of the Catalog is defined to store a maximum number of file transfer records.

### Automatic catalog expansion

The auto-expand catalog option lets you enlarge the catalog by a preset percentage when an alert is sent that the catalog is reaching its threshold. Additionally you can indicate a script to execute if this expanded limit is exceeded.

#### Overview

Once the catalog exceeds the minimum alert level, it can be expanded to the amount defined in the auto-expand option. For example, if you set the auto-expand to 100%, then the catalog doubles. If you define it as 50%, the catalog resizes to 1.5 times the original number of records. After the auto-expand limit is reached, a predefined script can be executed.

If you defined a limit for catalog alerts, TLVCLEAR, once the usage surpasses the allotted value one of the following occurs:

-   The catalog is expanded and a message sent to the log, but no script is executed
-   The catalog is expanded, a message is sent to the log, and the TLVCEXEC script executes.

#### Steps

To enable the auto-expand option, with Transfer CFT running:

1.  Set the uconf values for:
    -   cft.cftcat.auto\_expand\_percent
    -   cft.cftcat.auto\_expand\_max\_size
2.  To activate the new values, run the command: CFTUTIL reconfig type = uconf
    -   If Transfer CFT is stopped when setting uconf values, you do not need to execute the reconfig command.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Parameter</th>
         <th>Default</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>cft.cftcat.auto_expand_percent         </td>
         <td>0         </td>
         <td>            <p>This value indicates the factor increase, as a percentage, that the catalog will automatically expand.</p>
            <p>The value 0 disables the automatic expansion feature.</p>
<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Tip  </strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Tip  &lt;/b&gt;" data-valign="top">We recommend that you set this to a relatively high value, at least 50. When repeatedly expanded, the catalog's internal structure may become fragmented and, consequently, catalog access less efficient.         </td>
      </tr>
   </tbody>
</table>         </td>
      </tr>
      <tr class="even">
         <td>cft.cftcat.auto_expand_max_size         </td>
         <td>1M         </td>
         <td>            <p>The maximum number of records for the automatic catalog expansion option.</p>         </td>
      </tr>
   </tbody>
</table>

Related parameters:

-   TLVCLEAR: Level below which the alert stops.
-   TLVCEXEC: Batch to execute when the alert ends.
-   TLVWRATE: The minimum amount of time, in seconds, to wait before resending an alert.
-   TLVWEXEC: Batch to execute when CFTCAT/TLVWARN is reached.
-   TLVWARN: Catalog usage limit before issuing an alert. When this limit is reached, the CFTCAT/TLVWEXEC is executed.

Example

The example is based on the following settings:

-   catalog size = 100
-   cft.cftcat.auto\_expand\_percent = 20
-   cft.cftcat.auto\_expand\_max\_size = 140
-   TLVCLEAR = 70
-   TLVWARN = 80

When you reach the TLVWARN (level=80%), the following messages are sent to the log:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>12/10/17 17:53:30  CFTC29W Catalog Alert fill threshold reached: <span>level=80%</span> ID=CAT0</p>
            <p>12/10/17 17:53:30  CFTC13I Catalog resize (100 --&gt; 120) done</p>
            <p>12/10/17 17:54:16  CFTT17I _ STATE=HOLD &lt;IDTU=A0000029 PART=PARIS IDF=TXT IDT=J1718064&gt;</p>
            <p>12/10/17 17:54:16  CFTR12I SEND Treated for USER Nougat  &lt;IDTU=A0000029 PART=PARIS IDF=TXT&gt;</p>
            <p>12/10/17 17:54:16  CFTS20I Communication file row number deleted: 00000252   </p>         </td>
      </tr>
   </tbody>
</table>

The new fill rate is now 80/120 = ~67%, which is below TLVCLEAR (70), so the alerts stop at the next update.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>   12/10/17 17:54:16  CFTC30W Catalog Alert cleared : level=67% ID=CAT0</p>         </td>
      </tr>
   </tbody>
</table>

The message CFTC30W Catalog Alert cleared : **level=67%** indicates that the catalog is sufficient. If it were not, the catalog would be extended again at next alert in TLVWRATE seconds.

The catalog continues to fill until it reaches 80%. Expanding 20% more would resize the catalog to 144 records, which exceeds the limit (140). If you exceed the limit the following log messages display:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>12/10/17 18:06:57  CFTC29W Catalog Alert fill threshold reached: level=80% ID=CAT0</p>
            <p>12/10/17 18:06:57  CFTC13I Catalog resize (120 --&gt; 144) too much</p>
            <p>12/10/17 18:06:57  CFTC13I Catalog resize (120 --&gt; 140) done</p>
            <p>12/10/17 18:06:57  CFTT17I _ STATE=HOLD &lt;IDTU=A000002P PART=PARIS IDF=TXT IDT=J1718092&gt;</p>
            <p>12/10/17 18:06:57  CFTR12I SEND Treated for USER Nougat &lt;IDTU=A000002P PART=PARIS IDF=TXT&gt;</p>
            <p>12/10/17 18:06:57  CFTS20I Communication file row number deleted: 00000269                               </p>
            <p>12/10/17 18:06:57  CFTC30W Catalog Alert cleared : level=69% ID=CAT0</p>         </td>
      </tr>
   </tbody>
</table>

The next time the catalog limit is reached, it can no longer expand. Here, the log displays 210, which is the theoretical number computed by the auto-expand feature, but in reality it is an error (CFTC13E):

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>12/10/19 15:53:21  CFTC29W Catalog Alert fill threshold reached: level=80% ID=CAT0</p>
            <p>12/10/19 15:53:21  <strong>CFTC13E</strong> Catalog resize (140 --&gt; 210) reached max before expansion</p>
            <p>12/10/19 15:53:21  CFTC08I Purge Treated : no record found to delete.</p>         </td>
      </tr>
   </tbody>
</table>

#### Auto-expand option on z/OS

If you are using the cft.cftcat.auto\_expand parameter in a z/OS environment, refer to the SHARECAT parameter in the *Installation and Operation Guide* for OS specific details.

### Catalog purge policies

#### Purge using the CFTCAT command

The local file transfer internal datafile rules include standard purge rules that you can modify using the catalog command CFTCAT.

There are 6 parameters that manage the purge, depending on the transfer status and direction. For each of the following you can set the number, in days, for the purge to occur. In our example, the purge is set for 10 days.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTCAT ID = 'CAT0',</p>
<div>
            <p>FNAME = '$CFTCATA',</p>
            <p>WSCAN = '1',</p>
            <p>TIMEP = '23595999',</p>
            <p>UPDAT = '1',</p>
            <p>SH = '10',</p>
            <p>ST = '10',</p>
            <p>SX = '10',</p>
            <p>RH = '10',</p>
            <p>RT = '10',</p>
            <p>RX = '10',</p>
</div>         </td>
      </tr>
   </tbody>
</table>

The first letter indicates the transfer direction (S for SEND or R for receive ).

The second letter refers to the state (CFTSTATE).

**Normal mode**

-   \(H\) Transfer phase and hold phasestep, or Transfer phase and kill phasestep
-   \(T\) Ack phase and all phasesteps
-   \(X\) Done phase and Done phasestep

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Transfers in phase (Y) and phasestep (D) are not purged when purging the catalog. To purge these records, you must execute an END command that modifies the state to (X).         </td>
      </tr>
   </tbody>
</table>

**Compatibility mode**

-   \(H\) Hold, keep, or preprocessing status
-   \(T\) Completed status
-   \(X\) Executed status

#### Purge using UCONF settings

You can use the unified configuration to perform the same sort of purges as with the CFTCAT command, except that UCONF offers a more granular scheduling, i.e. hours, minutes, or seconds.

For example, set the following where the sx represents 10 days (where a day equals a 24 hour interval) for an executed SEND transfer:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>UCONFSET id=cft.purge.sx, value=10D</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The amount of time is entered in days (x or xD), in hours (xH) or in minutes (xM). If set to -1, the CFTCAT value is used.         </td>
      </tr>
   </tbody>
</table>

To schedule a periodic purge every 30 minutes:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL uconfset id=cft.purge.periodicity,value=30M         </td>
      </tr>
   </tbody>
</table>

To apply the dynamic configuration parameters change:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTUTIL reconfig type=UCONF         </td>
      </tr>
   </tbody>
</table>

For information on the RECONFIG command, please see [Manage configuration updates - RECONFIG](../admin_commands_intro/reconfig).

#### Purge per template definitions

When defining CFTSEND or CFTRECV templates you can set a parameter to purge the records after the transfer completes.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTSEND DELETE=YES</p>         </td>
      </tr>
   </tbody>
</table>

#### Purge records with the keep status

Delete all file transfer records in keep status (K) due to a file creation error.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>CFTRECV RKERROR=YES</p>         </td>
      </tr>
   </tbody>
</table>

#### Manually delete catalog records

The DELETE command is used to <span id="delete_command"></span>delete one
or more catalog entries. A transfer in process is interrupted and its
transfer request disappears from the catalog.

This file is automatically deleted for an R, Receive, type request in
non terminated state, a state other than T and X, if the receive file
is a temporary file.

For any selected set of transfers, transfers are processed in batches
of 20 transfers every 5 seconds.

For example, delete all executed transfers from the catalog.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>DELETE STATE=X</p>         </td>
      </tr>
   </tbody>
</table>

#### Manage transfer events sent to Sentinel

A file transfer event is sent as an XFB.Transfer event to the Sentinel server each time the file transfer status is updated.

You can set filters to reduce the number of messages (more than a 50% reduction) sent to Sentinel, for example:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>UCONFSET id=sentinel.xfb.transfer,value=SUMMARY         </td>
      </tr>
   </tbody>
</table>

## Archive Transfer CFT standard output files

All output files are stored in the &lt;runtime/run> directory. Among these are the standard output files for Transfer CFT and the Copilot processes. The copui.trc is the standard output for the Transfer CFT Copilot server, which continues to grow in size but cannot be rotated.

However, Transfer CFT processes use a standard output file &lt;runtime/run>/cft.out to log internal system messages. You can define the number of archive files you want to rotate using the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>UCONFSET id=cft.output.backup_count,value=n         </td>
      </tr>
   </tbody>
</table>

## Delete completed transfer files

There are multiple ways to clear out completed transfer files. Let's begin with a simple example of deleting files that have successfully been sent.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSEND ID=CLEANUP,FNAME=&lt;FILENAME&gt;,FACTION=DELETE         </td>
      </tr>
   </tbody>
</table>

If you would additionally like to delete the catalog records, as well as the file after it's transfer (defined according to the transfer state).

-   The FDELETE option removes the file once the catalog record is deleted.
-   You can use the DELETE=YES option in conjunction with FDELETE to remove both the file and the record.

For example, to remove both the file and the record when sending a file.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTSEND ID=CLEANUP,FNAME=&lt;FILENAME&gt;,DELETE=YES,FDELETE=CDKHTX         </td>
      </tr>
   </tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The DELETE/FDELETE options are also valid for a CFTRECV, but note that setting FDELETE=CDKHTX deletes the file regardless of the state at the end of the transfer.         </td>
      </tr>
   </tbody>
</table>
