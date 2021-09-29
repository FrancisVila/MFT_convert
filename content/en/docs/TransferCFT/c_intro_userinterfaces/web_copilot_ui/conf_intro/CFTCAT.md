{
    "title": "Catalog - CFTCAT ",
    "linkTitle": "Catalog - CFTCAT ",
    "weight": "190"
}The catalog logs all information relative to transfer requests. Use this command to describe the way the catalog is
managed: file, scanning mode, retention time before purge, and so on.

<span id="About_the_CFTCAT_Command"></span>The Catalog (CFTCAT) object is used to describe
the Transfer CFT transfer catalog access for:

-   File
-   Scanning mode
-   Retention time,
    before the purge, of associated information

The catalog purge can be initiated at midnight (default value) or at
a specific time indicated in the TIMEP parameter.

The catalog is purged in batches of 10 entries. Between each batch, Transfer CFT handles all pending transfer events. As a result, if the transfer
activity is intense, the catalog purge action may be extended but does
not significantly disrupt transfers.

## User interface options

In the user interface, you can customize the catalog columns and filters. From the Catalog - CFTCAT page in the user interface, you can create, clone, modify, or delete catalog objects.

## Parameter descriptions

Related
topics

-   Command syntax
    [CFTCAT](../../../command_summary)
-   Object concepts
    [Catalog attributes](../../../../admin_intro/admin_config_commands/catalog_parameter_concepts)

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/id">ID</a> </p></td>
<td><p>Name identifying the CFTCAT command.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/fname">FNAME</a></p></td>
<td><p>Catalog file name.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/cache">CACHE</a> </p></td>
<td><p>Size parameter for the monitor cache memory buffer
size, containing the transfers waiting for resources.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/rh">RH</a></p></td>
<td><p>Number of days (where a day equals a 24-hour interval) after which the catalog entries of "unterminated"
receive requests ( H or K state) are automatically purged.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/rkerror">RKERROR</a></p></td>
<td><p>Action to be taken if a transfer aborts during the
selection phase in server mode.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/rt">RT</a> </p></td>
<td><p>Number of days (where a day equals a 24-hour interval) after which the catalog entries of terminated
receive transfers (RT state) are automatically purged.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/rx">RX</a> </p></td>
<td><p>Number of days after which the catalog entries of receive
transfers for which the end of reception procedure is correctly executed
(RX state) are automatically purged.</p></td>
</tr>
<tr class="even">
<td><a href="ry.htm">RY</a></td>
<td>Number of days after which the catalog entries of receive transfers that are the in post-processing phase (RY state) are automatically purged.</td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/sh">SH</a> </p></td>
<td><p>Number of days (where a day equals a 24-hour interval) after which the catalog entries for
"unterminated" send requests (H or K state) are automatically purged.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/st">ST</a> </p></td>
<td><p>Number of days (where a day equals a 24-hour interval) after which the catalog entries of terminated
send transfers (ST state) are automatically purged.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/sx">SX</a></p></td>
<td><p>Number of days (where a day equals a 24-hour interval) after which the catalog entries of terminated
send transfers, for which the end-of-send transfer procedure was correctly
executed (SX state), are automatically purged.</p></td>
</tr>
<tr class="even">
<td><a href="sy.htm">SY</a></td>
<td>Number of days (where a day equals a 24-hour interval) after which the catalog entries of send transfers that are in the post-processing phase (SY state), are automatically purged.</td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/tlvclear">TLVCLEAR</a></p></td>
<td><p>Level below which the alert ceases, as a percentage of filling, where 0% indicates the file is empty and 100% that it is full.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/tlvcexec">TLVCEXEC</a></p></td>
<td><p>Batch to execute when the alert ends.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/tlvwrate">TLVWRATE</a></p></td>
<td><p>The minimum amount of time, in seconds, to wait before
resending an alert.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/tlvwexec">TLVWEXEC</a></p></td>
<td><p>Batch to execute when CFTCAT/TLVWARN is reached.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/tlvwarn">TLVWARN</a></p></td>
<td><p>Catalog usage limit before issuing an alert, as is a percentage of filling, where 0% indicates the file is empty, and 100% that it is full.</p>
<p>When this
limit is reached, the CFTCAT/TLVWEXEC is executed.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/timep">TIMEP</a> </p></td>
<td><p>Daily purge time chosen by the user.</p>
<p>The user can program an automatic, cyclic catalog purge.
The default purge time is midnight.</p>
<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To completely deactivate purging, set TIMEP = 00000000. Use this option with caution as no automatic
purging is performed (at a selected time or at midnight).</td>
</tr>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><p><a href="../../../command_summary/parameter_intro/updat">UPDAT</a> </p></td>
<td><p>Number of synchronization points between two consecutive
updates of the catalog file during a transfer.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../command_summary/parameter_intro/wscan">WSCAN</a> </p></td>
<td>Enter the frequency (in minutes) with which <span>Transfer CFT</span> scans the catalog file when restarting a transfer:
<ul>
<li>5 (default value)</li>
<li>1 to 60</li>
</ul></td>
</tr>
</tbody>
</table>

Example

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTCAT ID = IDCAT,</p>
<p>FNAME = filename,</p>
<p>RH = 7,</p>
<p>RT  = 3,</p>
<p>RX = 3,</p>
<p>SH = 7,</p>
<p>ST = 3,</p>
<p>SX = 3</p></td>
</tr>
</tbody>
</table>

-   Non-terminated send requests (SH state) and interrupted receive
    transfers are automatically purged after seven days (RH state).
-   Terminated send transfer entries (ST state) and terminated receive
    transfer entries (RT state) are automatically purged after three days.
    The entries of terminated send transfers and receive transfers for which
    the end procedure was correctly executed, SX and RX state, are automatically
    purged after three days.
-   The UPDAT parameter is not mentioned; it takes the default value
    1, which results in the catalog file being updated at each synchronization
    point of each transfer.

Related topics

-   [PURGE - Purging the catalog](../../../../admin_intro/admin_commands_intro/purge_catalog)
