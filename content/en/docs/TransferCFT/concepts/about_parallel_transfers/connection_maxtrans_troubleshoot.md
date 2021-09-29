{
    "title": "Connection / maximum transfer troubleshooting",
    "linkTitle": "Connection / maximum transfer troubleshooting",
    "weight": "270"
}This section provides transfer examples that demonstrate parameter dependencies and typical log outputs, including errors, which you may encounter when using similar values. The goal is to understand the effect of parameter combinations, and be able to adapt settings to your particular needs.

The following examples show the output from both the server and requester sides.

-   [Example: the number of transfers exceeds the CNXINOUT](#example:4)
-   [Example: MAXCNX is greater than MAXTRANS](#example:3)
-   [Example: the number of transfers exceeds the CNXINOUT](#example:4)
-   [Example: MAXCNX greater than MAXTRANS with session limit](#example:5)

See [Session related troubleshooting](../session_troubleshooting) for session related output.

See the [Frequently asked questions](../faq) for common questions and answers on parameter usage, license keys, and so on.

## Remote (partner) diagnostic codes

When troubleshooting, remember that if the [DIAG](../../../troubleshoot_intro/messages_and_error_codes_start_here/diagi_diagnostic_codes) is greater than 500, it refers to a remote issue. To find the actual DIAG, subtract 500 from the displayed code. If the DIAG is 962, for example, the issue is a remote problem corresponding to DIAG 462 (no data sent on network).

## <span id="Example:"></span>Examples

### <span id="Example:4"></span>Example: the number of transfers exceeds the CNXINOUT

##### **Scenario 1 - Requester configuration**

In this example, the number of transfers exceeds the CNXINOUT value defined on the requester side.

**Requester output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTT09E _ Maximum cv Affected &lt;IDTU=A00000FL PART=SUN35 IDF=T2 IDT=D2918112 PROT=PESIT&gt;</p></td>
</tr>
</tbody>
</table>

**Server output**

No message on server side.

##### **Scenario 2**

Here the number of transfers exceeds the CNXINOUT value defined on the server side.

**Server output**

<table data-cellspacing="0">
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>CFTT94I &lt;IDTU=A00000FM PART=SUN35 IDF=T1 IDT=D2918192 FCHARSET= NCHARSET=&gt;</p>
<p>CFTH13E FPDU Remote reject &lt;PART=SUN35 DIAGI=916 DIAGP=RCO 309&gt;</p>
<p>CFTT75E connect reject &lt;IDTU=A00000FN PART=SUN35 IDF=T2</p>
<p>IDT=D2918193 916 RCO 309&gt;</p></td>
</tr>
</tbody>
</table>

**Requester output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTT09E _ Maximum cv Affected &lt;IDTU= PART=WINZZ PROT=PESITANY&gt;</p>
<p>CFTH22E NPART=WINZZ rejected DIAGI=418</p></td>
</tr>
</tbody>
</table>

### <span id="Example:3"></span>Example: MAXCNX is greater than MAXTRANS

MAXCNX is greater than MAXTRANS on the requester side, and there are more than MAXTRANS transfers to be processed.

**Incoming session**

For the server's incoming session the extra transfer(s) is rejected with an error.

**Server output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTH22E NPART=NEWYORK rejected DIAGI=416</p></td>
</tr>
</tbody>
</table>

**Requester output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTH13E FPDU Remote reject &lt;PART=PARIS DIAGI=916 DIAGP=RCO 201&gt;</p></td>
</tr>
</tbody>
</table>

**Outgoing session**

When the requester wants to perform more than MAXTRANS transfers:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>The extra transfer(s) is set to an available state (D), but there is no error message in LOG.</p></td>
</tr>
</tbody>
</table>

### <span id="Example:4"></span>Example: MAXCNX is less than MAXTRANS

MAXCNX is less than the MAXTRANS value on the requester side, and you want to perform more than MAXCNX transfers (for example MAXCNX = 2, MAXTRANS= 5).

**Scenario 1**

**Requester output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTH09E Network connect request local error &lt;PART=SUN35-5 NCR=416 NCS=MAXCNX NET=TCP&gt;</p>
<p>CFTT75E connect reject &lt;IDTU=A00000GE PART=SUN35-5 IDF=T1 IDT=D3011193 416 MAXCNX&gt;</p></td>
</tr>
</tbody>
</table>

**Server output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>No message.</p></td>
</tr>
</tbody>
</table>

**Scenario 2**

MAXCNX is less than the MAXTRANS value on the server side, and you want to perform more than MAXCNX transfers on the requester side (for example MAXCNX = 2, MAXTRANS= 5).

**Requester output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>CFTH11E Error Opening session &lt;PART=WINZZ-4 EV=VNRELI ST=CN0022&gt;</p>
<p>CFTT75E connect reject &lt;IDTU=A000007D PART=WINZZ-4 IDF=T2 IDT=D3011264 302 R 0 2f2&gt;</p></td>
</tr>
</tbody>
</table>

**Server output**

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>No notification on server side.</td>
</tr>
</tbody>
</table>

### <span id="Example:5"></span>Example: MAXCNX greater than MAXTRANS with session limit

In this example, we have a distribution list with 5 partners, which shows an example of when you may want to have a MAXCNX greater than the MAXTRANS value.

**Scenario 1**

The transfers are executed quickly, in rapid succession because Transfer CFT is not limited by the session. As soon as the first 3 transfers are completed, the 2 remaining are executed immediately.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Remember one session is kept for incoming connections, so in this case only two sessions were used.</td>
</tr>
</tbody>
</table>

MAXTRANS=3, MAXCNX=6, DISCTD=120 (seconds session is still open)

<table data-cellspacing="0">
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>...</p>
<p>15/06/23 <u>17:40:46</u> CFTT53I Requester file selected &lt;IDTU=A0000VKQ PART=SUN35-1 IDF=BIN IDT=F2402472&gt;</p>
<p>15/06/23 17:40:46 CFTT55I Requester file opened &lt;IDTU=A0000VKQ PART=SUN35-1 IDF=BIN IDT=F2402472&gt;</p>
<p>...</p>
<p>15/06/23 17:40:47 CFTH56I PESIT Requester session opened &lt;PART=SUN35-2 IDS=00004 pi7=03:10240 HOST=127.0.0.1&gt;</p>
<p>15/06/23 17:40:47 CFTH56I PESIT Requester session opened &lt;PART=SUN35-1 IDS=00003 pi7=03:10240 HOST=127.0.0.1&gt;</p>
<p>15/06/23 17:40:47 CFTT57I Requester transfer started &lt;IDTU=A0000VKR PART=SUN35-2 IDF=BIN IDT=F2402473 &gt;</p>
<p>...</p>
<p>15/06/23 17:40:47 CFTT56I Requester file closed &lt;IDTU=A0000VKQ PART=SUN35-1 IDF=BIN IDT=F2402472&gt;</p>
<p>15/06/23 17:40:47 CFTT54I Requester file deselected &lt;IDTU=A0000VKQ PART=SUN35-1 IDF=BIN IDT=F2402472&gt;</p>
<p>...</p>
<p> </p>
<p>15/06/23 <u>17:40:47</u> CFTH56I PESIT Requester session opened &lt;PART=SUN35-3 IDS=00006 pi7=03:10240 HOST=127.0.0.1&gt;</p>
<p>15/06/23 17:40:47 CFTH56I PESIT Requester session opened &lt;PART=SUN35-4 IDS=00005 pi7=03:10240 HOST=127.0.0.1&gt;</p>
<p>15/06/23 17:40:47 CFTT57I Requester transfer started &lt;IDTU=A0000VKS PART=SUN35-3 IDF=BIN IDT=F2402474 &gt;</p>
<p>...</p>
<p>15/06/23 17:40:47 CFTT56I Requester file closed &lt;IDTU=A0000VKU PART=SUN35-5 IDF=BIN IDT=F2402480&gt;</p>
<p>15/06/23 17:40:47 CFTT54I Requester file deselected &lt;IDTU=A0000VKU PART=SUN35-5 IDF=BIN IDT=F2402480&gt;</p>
<p>15/06/23 <u>17:40:47</u> CFTT88I+&lt;IDTU=A0000VKU WORKINGDIR= FNAME=pub/FTEST NBC=7104&gt;</p></td>
</tr>
</tbody>
</table>

**Scenario 2**

In Scenario 2 Transfer CFT is limited by the session, meaning that the same 5 partner transfers as in Scenario 1 now take over 120 seconds (the DISCTD time defined to keep the session open).

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">DISCTD has an effect on latency.</td>
</tr>
</tbody>
</table>

MAXTRANS=6, MAXCNX=3, DISCTD=120 (seconds session is still open)

<table data-cellspacing="0">
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>...</p>
<p>15/06/23 <u>17:58:21</u> CFTI34I PID=10956 CFTTFIL Task started successfully</p>
<p>15/06/23 17:58:21 CFTT53I Requester file selected &lt;IDTU=A0000VL2 PART=SUN35-1 IDF=T1 IDT=F2402492&gt;</p>
<p>15/06/23 17:58:21 CFTT55I Requester file opened &lt;IDTU=A0000VL2 PART=SUN35-1 IDF=T1 IDT=F2402492&gt;</p>
<p>...</p>
<p>15/06/23 17:58:21 CFTT13I Session parameters &lt;IDTU=A0000VL3 PART=SUN35-2 IDF=T1 IDT=F2402493 _ PROT=PESIT SAP=21761 HOST=sun35.lab1.lab.ptx.axway.int&gt;</p>
<p>15/06/23 17:58:21 CFTI34I PID=6160 CFTTFIL Task started successfully</p>
<p>...</p>
<p>15/06/23 17:58:51 CFTH09E Network connect request local error &lt;PART=SUN35-4 NCR=416 NCS=MAXCNX NET=TCP&gt;</p>
<p>15/06/23 17:58:51 CFTT75E connect reject &lt;IDTU=A0000VL5 PART=SUN35-4 IDF=T1 IDT=F2402495 416 MAXCNX&gt;</p>
<p>...</p>
<p>15/06/23 18:00:43 CFTT56I Requester file closed &lt;IDTU=A0000VL6 PART=SUN35-5 IDF=T1 IDT=F2402500&gt;</p>
<p>15/06/23 18:00:43 CFTT54I Requester file deselected &lt;IDTU=A0000VL6 PART=SUN35-5 IDF=T1 IDT=F2402500&gt;</p>
<p>15/06/23 <u>18:00:48</u> CFTH61I PESIT Server session closed &lt;PART=SUN35-5 IDS=00012&gt;</p></td>
</tr>
</tbody>
</table>

Related topics

-   [About parallel transfers](..//transfercft/concepts/about_parallel_transfers)
-   [FAQ and troubleshooting](../faq)
