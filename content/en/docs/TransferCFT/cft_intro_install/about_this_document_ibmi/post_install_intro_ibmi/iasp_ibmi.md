{
    "title": "How to use ASP (Auxiliary storage pools) disk",
    "linkTitle": "How to use ASP (Auxiliary storage pools) disk",
    "weight": "240"
}{
"title": "Viewing transfer messages",
"linkTitle": "Viewing transfer messages",
"weight": "230"
}After depositing a transfer command, such as the loop-back test, the following messages are displayed.
## Example
SEND PART=LOOP,IDF=TEST,FNAME=CFTPROD/TEST

<table data-cellspacing="0">
   <colgroup>      
         <col style="width: 100%" />
   </colgroup>
   <tbody>
      <tr class="odd">
         <td>            <p>From . . . : CFT 04/02/15 17:12:45</p>
            <p>CFTR12I SEND PART=LOOP IDF=TEST Treated for USER CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:45</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:45</p>
            <p>CFTS20I Communication file row number deleted: 00000030</p>
            <p>From . . . : CFT 04/02/15 17:12:45</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:46</p>
            <p>CFTW09I PART=LOOP IDF=TEST IDT=D0217124 CFTSEND IDFDEFT NIDF=TEST</p>
            <p>From . . . : CFT 04/02/15 17:12:46</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:46</p>
            <p>CFTT13I PART=LOOP IDF=TEST IDT=D0217124 _ Session parameters</p>
            <p>From . . . : CFT 04/02/15 17:12:46</p>
            <p>+ PROT=PESITANY SAP=65535 HOST=127.0.0.1</p>
            <p>From . . . : CFT 04/02/15 17:12:46</p>
            <p>CFTI34I PID=9 CFTTFIL Task started successfully</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT53I PART=LOOP IDF=TEST IDT=D0217124 Requester file selected</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT55I PART=LOOP IDF=TEST IDT=D0217124 Requester file opened</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTH56I PART=LOOP IDS=00003 PESIT Server session opened</p>
            <p>pi7=02:00512</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTH56I PART=LOOP IDS=00002 PESIT Requester session opened</p>
            <p>pi7=02:00512</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTW09I PART=LOOP IDF=TEST IDT=D0217124 CFTRECV IDFDEFT NIDF=TEST</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT53I PART=LOOP IDF=TEST IDT=D0217124 Server file created</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT55I PART=LOOP IDF=TEST IDT=D0217124 Server file opened</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT57I PART=LOOP IDF=TEST IDT=D0217124 Server transfer started</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT57I PART=LOOP IDF=TEST IDT=D0217124 Requester transfer started</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT58I PART=LOOP IDF=TEST IDT=D0217124 Server transfer ended</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT58I PART=LOOP IDF=TEST IDT=D0217124 Requester transfer ended</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT56I PART=LOOP IDF=TEST IDT=D0217124 Server file closed</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTH58I PART=LOOP IDS=00003 IDF=TEST NIDT=9317124 transfer</p>
            <p>deselected</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>+ T=400</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT54I PART=LOOP IDF=TEST IDT=D0217124 Server file deselected</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT88I+IDT=D0217124 WORKINGDIR= FNAME=CFTPROD/R_A000000L NBC=160</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTH58I PART=LOOP IDS=00002 IDF=TEST NIDT=9317124 transfer</p>
            <p>deselected</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>+ T=200</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT56I PART=LOOP IDF=TEST IDT=D0217124 Requester file closed</p>
            <p>From . . . : CFT 04/02/15 17:12:47</p>
            <p>CFTT54I PART=LOOP IDF=TEST IDT=D0217124 Requester file deselected</p>
            <p>From . . . : CFT 04/02/15 17:12:48</p>
            <p>CFTT88I+IDT=D0217124 WORKINGDIR= FNAME=CFTPROD/TEST NBC=160</p>
            <p>From . . . : CFT 04/02/15 17:12:48</p>
            <p>CFTS03I PART=LOOP IDF=TEST IDT=D0217124 _ *LIBL/CFTSRC(B_EXECRF)</p>
            <p>From . . . : CFT 04/02/15 17:12:48</p>
            <p>+ executed</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTS03I PART=LOOP IDF=TEST IDT=D0217124 _ *LIBL/CFTSRC(B_EXECSF)</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+ executed</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTR17I END PART=LOOP IDF=* IDTU=A000000L In progress for USER</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+ CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTR12I END PART=LOOP IDF=* IDTU=A000000L Treated for USER</p>
            <p>CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTS20I Communication file row number deleted: 00000031</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTR12I SEND PART=LOOP IDM=REP Treated for USER CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTS20I Communication file row number deleted: 00000032</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTT13I PART=LOOP IDM=REP IDT=D0217125 _ Session parameters</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>+ PROT=PESITANY SAP=65535 HOST=127.0.0.1</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTT59I PART=LOOP IDM=TEST IDT=D0217124 Server reply</p>
            <p>transfered</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTH60I PART=LOOP IDS=00002 IDM=TEST NIDT=9317124 reply</p>
            <p>transfered</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTT59I PART=LOOP IDM=REP IDT=D0217125 Requester reply</p>
            <p>transfered</p>
            <p>From . . . : CFT 04/02/15 17:12:50</p>
            <p>CFTH62I+ REF=9317124.LOOP.LOOP.0.TEST..</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>
            <p>CFTR17I END PART=LOOP IDF=* IDTU=A000000K In progress for USER</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>
            <p>+ CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>
            <p>CFTR12I END PART=LOOP IDF=* IDTU=A000000K Treated for USER</p>
            <p>CFT</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>
            <p>+</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>
            <p>CFTS20I Communication file row number deleted: 00000033</p>
            <p>From . . . : CFT 04/02/15 17:12:51</p>         </td>
      </tr>
   </tbody>
</table>
