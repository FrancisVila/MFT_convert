{
    "title": "Manage commands",
    "linkTitle": "Manage commands",
    "weight": "180"
}This section describes all of the command available to manage your Transfer CFT product.

## Standard commands

<table data-border="1" data-cellpadding="0" data-cellspacing="0" data-xmlns="http://www.w3.org/TR/REC-html40">
<thead>
<tr class="header">
<th><p>Command</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CFTSTART</p></td>
<td><p>Start Transfer CFT</p></td>
</tr>
<tr class="even">
<td><p>CFTSTOP</p></td>
<td><p>Stop Transfer CFT</p></td>
</tr>
<tr class="odd">
<td><p>COPSTART</p></td>
<td><p>Start the UI server</p></td>
</tr>
<tr class="even">
<td><p>COPSTOP</p></td>
<td><p>Stop the UI server</p></td>
</tr>
<tr class="odd">
<td><p>CFTMN</p></td>
<td><p>This is the procedure to manage Transfer CFT and to configure multi-node. Add
the following action(s) to manage your product:</p>
<ul>
<li>START</li>
<li>STOP</li>
<li>RESTART</li>
<li>ADD_NODE</li>
<li>REMOVE_NODE</li>
<li>ADD_HOST</li>
<li>REMOVE_HOST</li>
<li>REMOVE_NODE</li>
<li>ENABLE_NODE</li>
<li>DISABLE_NODE</li>
</ul>
<table data-cellpadding="0" data-cellspacing="0" data-xmlns="">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">CFTMN is the equivalent of <span>cft script</span> for UNIX or
Windows.</td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>

## Deprecated commands

<table data-border="1" data-cellpadding="0" data-cellspacing="0" data-xmlns="http://www.w3.org/TR/REC-html40">
<thead data-xmlns="">
<tr class="header">
<th>Replace this command...</th>
<th>With the new command...</th>
</tr>
</thead>
<tbody data-xmlns="">
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>SHUT</p></td>
<td data-valign="top" width="337"><p>CFTSTOP + COPSTOP</p></td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>CFTMGSBM</p></td>
<td data-valign="top" width="337"><p>CFTSTART</p></td>
</tr>
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>STARTCOPB</p></td>
<td data-valign="top" width="337"><p>COPSTART</p></td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>COPSMNG</p></td>
<td data-valign="top" width="337"><p>COPSTART</p></td>
</tr>
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>COPSTOPM</p></td>
<td data-valign="top" width="337"><p>COPSTOP</p></td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>STOPCOPL</p></td>
<td data-valign="top" width="337"><p>COPSTOP</p></td>
</tr>
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255"><p>BACKGROUND_C</p></td>
<td data-valign="top" width="337"><p>BACKGROUND</p></td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255">SNDCFTF</td>
<td data-valign="top" width="337" data-xmlns="">CFTUTIL (See <strong>Example 1</strong>)</td>
</tr>
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255">SNDCFTSPLF</td>
<td data-valign="top" width="337" data-xmlns="">CFTUTIL (See <strong>Example 2</strong>)</td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255">MAJSECINI</td>
<td data-valign="top" width="337" data-xmlns="">No replacement</td>
</tr>
<tr class="odd" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255">MAJSECENVG</td>
<td data-valign="top" width="337" data-xmlns="">No replacement</td>
</tr>
<tr class="even" data-xmlns="http://www.w3.org/TR/REC-html40">
<td data-valign="top" width="255">GENEDICT</td>
<td data-valign="top" width="337" data-xmlns="">No replacement</td>
</tr>
</tbody>
</table>

**Example 1**

Send a member:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL send PART=&lt;PART&gt;, IDF=&lt;IDF&gt;, FNAME=&amp;LIB/&amp;FILE(&amp;MBR)</td>
</tr>
</tbody>
</table>

**Example 2**

Send a spool file:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTUTIL send PART=&lt;PART&gt;, IDF=&lt;IDF&gt;, FNAME=&amp;FILE/&amp;SPLNBR/&amp;WORK/&amp;JOBNBR</td>
</tr>
</tbody>
</table>

 
