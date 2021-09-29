{
    "title": "Catalog query services in COBOL",
    "linkTitle": "Catalog query services in COBOL",
    "weight": "360"
}# <span id="CFT_catalog_query_services_in_COBOL"></span> <span>Transfer CFT</span> catalog query services



This service provides access to the <span>Transfer CFT</span> catalog entries, for

querying and modification, and enables you to sort the selected catalog

entries. Additionally, you can sort the current selection in memory.



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The communication structure

in Transfer CFT enables you to recuperate catalog fields, such

as an identifier, that exceed 8 to 32 characters.</td>
</tr>
</tbody>
</table>
<table data-cellspacing="0">
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr>
<th><p>Function</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr data-valign="top">
<td width="28.255%"><p>OPEN</p></td>
<td width="71.745%"><p>Open catalog file</p>
<p>This function:</p>
<ul>
<li>Allocates

the catalog file</li>
<li>Opens

the file</li>
<li>Reserves

an internal control block</li>
<li>Initializes

the internal block parameter</li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SELECT</p></td>
<td width="71.745%"><p>Specify the selection criteria</p>
<p>This function:</p>
<ul>
<li>Checks

the syntax used</li>
<li>Stores

the selection criteria in the internal control block</li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SELECT240</p></td>
<td width="71.745%"><p>Specify the selection criteria</p>
<p>This function:</p>
<ul>
<li>Is available

in CFT v2.4 and higher</li>
<li>Retrieves

identifiers that are longer than 8 to 32 characters</li>
<li>Checks

the syntax used</li>
<li>Stores

the selection criteria in the internal control block</li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>NEXT</p></td>
<td width="71.745%"><p>Read next entry in the catalog</p>
<p>This function:</p>
<ul>
<li>Reads

the next entry</li>
<li>Sets

the "catalog entry data" area</li>
</ul>
<p>The first call to this function must be preceded by a SELECT.</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>NEXT240</p></td>
<td width="71.745%"><p>Read next entry in the catalog</p>
<p>This function:</p>
<ul>
<li>Is available

in CFT v2.4 and higher</li>
<li>Retrieves

identifiers that are longer than 8 to 32 characters</li>
<li>Reads

the next entry</li>
<li>Sets

the "catalog entry data" area</li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>MODIFY</p></td>
<td width="71.745%"><p>Modify the state of the current catalog entry or delete

this entry from the catalog</p>
<p>This function:</p>
<ul>
<li>Retrieves

the last entry read from the internal control block</li>
<li>Checks

the state of this entry</li>
<li>Sends

the modification request to <span>Transfer CFT</span></li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>SORT</p></td>
<td width="71.745%"><p>Sort the selected catalog entries</p>
<p>This function:</p>
<ul>
<li>Close

the catalog file</li>
<li>De-allocates

the file</li>
<li>Frees

the internal control block</li>
<li>Resets

the internal control block parameter</li>
</ul></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>DO</p></td>
<td width="71.745%"><p>Execute the current selection and the requested sort in

memory</p></td>
</tr>
<tr data-valign="top">
<td width="28.255%"><p>CLOSE</p></td>
<td width="71.745%"><p>Close catalog file</p></td>
</tr>
</tbody>
</table>



## <span id="Call Syntax"></span>Call syntax



<table data-cellspacing="0">
<tbody>
<tr>
<td>CALL     "CFTI"    

USING     &lt;verb&gt;       &lt;blk&gt;    

  &lt;param&gt;    

&lt;rc&gt;</td>
</tr>
</tbody>
</table>



Where:



-   &lt;verb&gt; is

    the command that you want to process

-   &lt;blk&gt; is

    a **<span> <span>Transfer CFT</span> specific field that

    must not be changed by the application</span>**

-   &lt;param&gt; is

    a character string of variable length that contains the command parameters.

    The end of the field is defined by a character initially set to low-value

-   &lt;rc&gt; is the

    return code



The available &lt;verbs&gt; are listed in the following table.



<table data-bgcolor="#FFFFFF" data-cellspacing="0">
<colgroup>
<col/>
<col/>
<col/>
</colgroup>
<thead>
<tr>
<th><p>&lt;verb&gt;</p></th>
<th><p>Value</p></th>
<th><p>Service</p></th>
</tr>
</thead>
<tbody>
<tr>
<td data-valign="top" width="20.005%"><p>F-OPEN</p></td>
<td data-valign="top" width="18.644%"><p>OPEN</p></td>
<td data-valign="top" width="61.351%"><p>Open catalog</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-SELECT</p></td>
<td data-valign="top" width="18.644%"><p>SELECT</p></td>
<td data-valign="top" width="61.351%"><p>Define selection criteria</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-NEXT</p></td>
<td data-valign="top" width="18.644%"><p>NEXT</p></td>
<td data-valign="top" width="61.351%"><p>Read next entry</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-MODIFY</p></td>
<td data-valign="top" width="18.644%"><p>MODIFY</p></td>
<td data-valign="top" width="61.351%"><p>Modify catalog entry state</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-CLOSE</p></td>
<td data-valign="top" width="18.644%"><p>CLOSE</p></td>
<td data-valign="top" width="61.351%"><p>Close catalog</p></td>
</tr>
</tbody>
</table>



The available &lt;param&gt; are listed in the following table.



<table data-bgcolor="#FFFFFF" data-cellspacing="0">
<colgroup>
<col/>
<col/>
<col/>
</colgroup>
<thead>
<tr>
<th><p>&lt;verb&gt;</p></th>
<th><p>&lt;param&gt;</p></th>
<th><p>Explanation</p></th>
</tr>
</thead>
<tbody>
<tr>
<td data-valign="top" width="20.005%"><p>F-OPEN</p></td>
<td data-valign="top" width="18.644%"><p>D-CAT</p></td>
<td data-valign="top" width="61.351%"><p>Path name or logical name of the catalog file. If the name

is blank, Transfer CFTI uses a default name.</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-SELECT</p></td>
<td data-valign="top" width="18.644%"><p>Z-SEL</p></td>
<td data-valign="top" width="61.351%"><p>Selection criteria according to the format

described in the "S<span>election data

description"</span> in the <span>cft.apicop</span>

file. If a field is blank or equal to binary zeros, it is considered not

selective.</p>
<p>This field can contain:</p>
<ul>
<li>the size

of the selection criteria field (SLENTGTH) and the size of the field supporting

the catalog entry (CLENGTH) in order to avoid recompiling the application

program if these two fields are extended.</li>
<li>the transfer

start and end date (BDATE and EDATE) to select transfers performed between

these two dates.</li>
<li>a mask

with the special characters "?" and *". The "?"

character replaces any character. The "*" character replaces

a character string of any length.<br/>
<br/>

Examples:<br/>

A*D replaces ABCD, ABCED or AID<br/>

A??D replaces ABCD, AXYD or AQZD<br/>

*CD replaces ABECD, YXZCDor TYUICD<br/>

?CD replaces ACD, XCD or ZCD<br/>

?B* replaces ABCDEF, XBZWEO or *KBWXCV<br/>

???? replaces ABCD, XYZW or HGFD</li>
</ul></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-NEXT</p></td>
<td data-valign="top" width="18.644%"><p>Z-CAT</p></td>
<td data-valign="top" width="61.351%"><p>Next catalog entry according to the format described in

the "S<span>election data description</span>"

in the <span>cft.apicop</span> file.</p>
<p>The length of this field is defined by the SELECT service.

See the CLENGTH field in the Selection data description.</p></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-MODIFY</p></td>
<td data-valign="top" width="18.644%"><p>M-STATE</p></td>
<td data-valign="top" width="61.351%"><p>New state of a transfer to be placed in the catalog entry

previously read:</p>
<ul>
<li>‘D’ at

Disposal: only valid if the former state is H or K</li>
<li>‘H’ Hold:

only valid if the former state is D, C

or K</li>
<li>‘K’ Keep:

only valid if the former state is D, C or H</li>
<li>‘X’ eXecuted:

only valid if the former state is T</li>
<li>‘P’ Purge:

 deletes

the catalog entry</li>
</ul></td>
</tr>
<tr>
<td data-valign="top" width="20.005%"><p>F-CLOSE</p></td>
<td data-valign="top" width="18.644%"><p> </p></td>
<td data-valign="top" width="61.351%"><p>No &lt;param&gt; needed</p></td>
</tr>
</tbody>
</table>



## Return codes



The return codes listed below apply to all services.



<table data-bgcolor="#FFFFFF" data-cellspacing="0">
<colgroup>
<col/>
<col/>
</colgroup>
<thead>
<tr>
<th><p>Mnemonic</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-NOERR</p></td>
<td data-valign="top" width="71.863%"><p>No error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-FUNC-UNDEF</p></td>
<td data-valign="top" width="71.863%"><p>Command not valid</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-INT-BLK</p></td>
<td data-valign="top" width="71.863%"><p>&lt;blk&gt; parameter invalid</p></td>
</tr>
<tr>
<td colspan="2" data-valign="top" width="28.137%"><p>OPEN code only</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-MEM-GET</p></td>
<td data-valign="top" width="71.863%"><p>Memory allocation error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-ALLOC</p></td>
<td data-valign="top" width="71.863%"><p>Catalog file allocation error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-OPEN</p></td>
<td data-valign="top" width="71.863%"><p>Catalog file opening problem</p></td>
</tr>
<tr>
<td colspan="2" data-valign="top" width="28.137%"><p>SELECT code only</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-DIRECT</p></td>
<td data-valign="top" width="71.863%"><p>DIRECTION criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-TYPE</p></td>
<td data-valign="top" width="71.863%"><p>TYPE criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-STATE</p></td>
<td data-valign="top" width="71.863%"><p>STATE criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-EMPTY</p></td>
<td data-valign="top" width="71.863%"><p>Catalog empty</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-DATE</p></td>
<td data-valign="top" width="71.863%"><p>EDATE value &lt; BDATE value</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-FDATE</p></td>
<td data-valign="top" width="71.863%"><p>FDATE criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-CDATE</p></td>
<td data-valign="top" width="71.863%"><p>CDATE criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-BDATE</p></td>
<td data-valign="top" width="71.863%"><p>BDATE criterion incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-SEL-DATE</p></td>
<td data-valign="top" width="71.863%"><p><span>EDATE

criterion incorrect</span></p></td>
</tr>
<tr>
<td colspan="2" data-valign="top" width="28.137%"><p>NEXT code only</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-EOF</p></td>
<td data-valign="top" width="71.863%"><p>End of catalog file</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-READ</p></td>
<td data-valign="top" width="71.863%"><p>Catalog file read error</p></td>
</tr>
<tr>
<td colspan="2" data-valign="top" width="28.137%"><p>MODIFY code only</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-MOD-OSTATE</p></td>
<td data-valign="top" width="71.863%"><p>State invalid</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-MOD-NSTATE</p></td>
<td data-valign="top" width="71.863%"><p>Requested new state incorrect</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-INT-ERR2</p></td>
<td data-valign="top" width="71.863%"><p>Internal error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPIO-COM-OPEN</p></td>
<td data-valign="top" width="71.863%"><p>Communication medium opening error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-COM-WRITE</p></td>
<td data-valign="top" width="71.863%"><p>Communication medium write error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-COM-CLOSE</p></td>
<td data-valign="top" width="71.863%"><p>Communication medium closing problem</p></td>
</tr>
<tr>
<td colspan="2" data-valign="top" width="28.137%"><p>CLOSE code only</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-MEM-FREE</p></td>
<td data-valign="top" width="71.863%"><p>Memory de-allocation error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-FREE</p></td>
<td data-valign="top" width="71.863%"><p>Catalog file de-allocation error</p></td>
</tr>
<tr>
<td data-valign="top" width="28.137%"><p>CAPI-CAT-CLOSE</p></td>
<td data-valign="top" width="71.863%"><p>Catalog file closing error</p></td>
</tr>
</tbody>
</table>
