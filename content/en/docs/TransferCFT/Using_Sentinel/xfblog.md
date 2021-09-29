{
    "title": "XFBLog Tracked Object",
    "linkTitle": "XFBLog Tracked Object",
    "weight": "230"
}When you configure Sentinel to monitor Transfer CFT, you can import
the XFBLog Tracked Object. The XFBLog is a Tracked Object that describes
the contents of an Transfer CFT log file. This log stores traces of the
events and errors that occur on Transfer CFT. This topic describes the XFBLog attributes.

## XFBLog attributes

The XFBLog includes the following attributes.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Attribute</th>
<th>Description</th>
<th>Type</th>
<th>Length</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ApplicationName</td>
<td><p>Application name</p>
<p>CFT: PART (CFTPARM)</p></td>
<td>Variable string</td>
<td>40</td>
</tr>
<tr class="even">
<td>CodeMsg</td>
<td>Message code</td>
<td>Variable string</td>
<td>10</td>
</tr>
<tr class="odd">
<td>IdentMsg</td>
<td>Message identifier CFTxYYz</td>
<td>Variable string</td>
<td>10</td>
</tr>
<tr class="even">
<td>Monitor</td>
<td>Hardcoded value to: XFB</td>
<td>Variable string</td>
<td>10</td>
</tr>
<tr class="odd">
<td>Product</td>
<td>Product name:</td>
<td>Variable string</td>
<td>10</td>
</tr>
<tr class="even">
<td>RecDate</td>
<td>Recorded date in local log file</td>
<td>Date</td>
<td> </td>
</tr>
<tr class="odd">
<td>RecTime</td>
<td>Recorded time in local log file</td>
<td>Time</td>
<td> </td>
</tr>
<tr class="even">
<td>SeverityClass</td>
<td><p>Severity class:</p>
<p>ES – System Error</p>
<p>EC – Component Error</p>
<p>EM – Message Error</p>
<p>AV – Error and Warning</p>
<p>IG – General Information</p>
<p>IP – Program Information</p></td>
<td>Variable string</td>
<td>10</td>
</tr>
<tr class="odd">
<td>SessionTag</td>
<td>Session tag</td>
<td>Variable string</td>
<td>20</td>
</tr>
<tr class="even">
<td>TransferTag</td>
<td>Transfer tag</td>
<td>Variable string</td>
<td>20</td>
</tr>
</tbody>
</table>

Related topics

[XFBTransfer requests](../xfbtransfer_request)
