{
    "title": "PeSIT parameter summary",
    "linkTitle": "PeSIT parameter summary",
    "weight": "170"
}The following table shows the correspondence between
standardized PI codes and Transfer CFT defined values.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>PI</th>
<th>Description</th>
<th> Transfer CFT value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>Use of a CRC  (deprecated)</p></td>
<td><p>PAD </p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>Diagnostic </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>Requester identifier</p></td>
<td><p>NSPART(length &lt; 24) </p></td>
</tr>
<tr class="even">
<td><p> </p></td>
<td><p>Sending application’s name </p></td>
<td><p>SAPPL </p></td>
</tr>
<tr class="odd">
<td><p> </p></td>
<td><p>Sending user’s name </p></td>
<td><p>SUSER </p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>Server identifier </p></td>
<td><p>NRPART<br />
(length &lt; 24) </p></td>
</tr>
<tr class="odd">
<td><p> </p></td>
<td><p>Receiver application name </p></td>
<td><p>RAPPL </p></td>
</tr>
<tr class="even">
<td><p> </p></td>
<td><p>Receiver user name </p></td>
<td><p>RUSER </p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>Access control </p></td>
<td><p>NSPASSW<br />
NRPASSW </p></td>
</tr>
<tr class="even">
<td><p> </p></td>
<td><p>New password </p></td>
<td><p>( / ) </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>Version number </p></td>
<td><p>2  </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>Interval between synchronization points  </p></td>
<td><p>SPACING<br />
RPACING </p></td>
</tr>
<tr class="odd">
<td><p> </p></td>
<td><p>Acknowledgement window </p></td>
<td><p>SCHKW<br />
RCHKW </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>File type </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>File name </p></td>
<td><p>NIDF (length &lt; 76)<br />
(possibility of generic selection) </p></td>
</tr>
<tr class="even">
<td><p> </p></td>
<td><p>Message name  </p></td>
<td><p>IDM </p></td>
</tr>
<tr class="odd">
<td><p>13 </p></td>
<td><p>Transfer identifier </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="even">
<td><p>14 </p></td>
<td><p>Requested attributes </p></td>
<td><p>0xE0 (all)  </p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>Restarted transfer </p></td>
<td><p>0 (no), 1 (yes) </p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>Data code </p></td>
<td><p>NCODE </p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>Transfer priority </p></td>
<td><p>PRI </p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
<td><p>Restart point </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="odd">
<td><p>19 </p></td>
<td><p>End-of-transfer code </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="even">
<td><p>20 </p></td>
<td><p>Synchron. point no. </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="odd">
<td><p>21 </p></td>
<td><p>Compression </p></td>
<td><p>NCOMP<br />
RCOMP SCOMP  </p></td>
</tr>
<tr class="even">
<td><p>22 </p></td>
<td><p>Access type </p></td>
<td><p>SROUT (read, write, mixed) </p></td>
</tr>
<tr class="odd">
<td><p>23 </p></td>
<td><p>Resynchronization </p></td>
<td><p>RESYNC </p></td>
</tr>
<tr class="even">
<td><p>25 </p></td>
<td><p>Data entity maximum size </p></td>
<td><p>SRUSIZE<br />
RRUSIZE  </p></td>
</tr>
<tr class="odd">
<td><p>27 </p></td>
<td><p>Number of data bytes </p></td>
<td><p>(T) </p></td>
</tr>
<tr class="even">
<td><p>28 </p></td>
<td><p>Number of articles </p></td>
<td><p>(T)  </p></td>
</tr>
<tr class="odd">
<td><p>29 </p></td>
<td><p>Diagnostic complement </p></td>
<td><p>( / ) </p></td>
</tr>
<tr class="even">
<td><p>31 </p></td>
<td><p>Article format </p></td>
<td><p>NRECFM </p></td>
</tr>
<tr class="odd">
<td><p>32 </p></td>
<td><p>Article length  </p></td>
<td><p>NLRECL </p></td>
</tr>
<tr class="even">
<td><p>33 </p></td>
<td><p>File organization </p></td>
<td><p>NORG </p></td>
</tr>
<tr class="odd">
<td><p>37 </p></td>
<td><p>File label </p></td>
<td><p>NFNAME (length &lt; 512) </p></td>
</tr>
<tr class="even">
<td><p>38 </p></td>
<td><p>Key length </p></td>
<td><p>NKEYLEN </p></td>
</tr>
<tr class="odd">
<td><p>39 </p></td>
<td><p>Key offset </p></td>
<td><p>NKEYPOS </p></td>
</tr>
<tr class="even">
<td><p>41 </p></td>
<td><p>Space reservation unit </p></td>
<td><p>0 (kilo-bytes)  </p></td>
</tr>
<tr class="odd">
<td><p>42 </p></td>
<td><p>Space reservation<br />
maximum value </p></td>
<td><p>NSPACE  </p></td>
</tr>
<tr class="even">
<td><p>51 </p></td>
<td><p>Creation date </p></td>
<td><p>FDATE  </p></td>
</tr>
<tr class="odd">
<td><p> </p></td>
<td><p>Creation time </p></td>
<td><p>FTIME </p></td>
</tr>
<tr class="even">
<td><p>52 </p></td>
<td><p>Date and time of last extraction </p></td>
<td><p>PI 51 </p></td>
</tr>
<tr class="odd">
<td><p>61 </p></td>
<td><p>Client identifier</p></td>
<td><p>NSPART of initial sender </p></td>
</tr>
<tr class="even">
<td><p>62 </p></td>
<td><p>Bank identifier</p></td>
<td><p>NRPART of final recipient </p></td>
</tr>
<tr class="odd">
<td><p>91 </p></td>
<td><p>Message </p></td>
<td><p>New parameter  </p></td>
</tr>
<tr class="even">
<td><p>99 </p></td>
<td><p>Free message </p></td>
<td></td>
</tr>
</tbody>
</table>

In this table:

-   T: defined by Transfer
    CFT during transfer
-   (/): not used by
    Transfer CFT
-   (-): PI not supported
    by this version of the protocol
