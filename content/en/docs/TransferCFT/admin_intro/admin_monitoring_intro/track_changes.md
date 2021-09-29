{
    "title": "Tracking Transfer CFT configuration changes",
    "linkTitle": "Tracking Transfer CFT configuration changes",
    "weight": "300"
}# Track configuration changes



The configuration auditing feature enables Transfer CFT to track configuration changes and send this information to the Sentinel

server. The configuration change can be:



-   Deleting, modifying, or creating a CFTxxx object (PART, or PART database)

-   Creating or deleting

    a CFTFILE object (PARM, PART, CAT, LOG…)



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">The configuration change tracking feature described in this section is not available when using Central Governance or Flow Manager as Transfer CFT configuration changes are tracked by those products. Consequently, you cannot set the parameters described in this section using either of these products.</td>
</tr>
</tbody>
</table>



## Procedure



<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr>
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note  &lt;/b&gt;" data-valign="top">To enable the configuration change audit, set the Sentinel parameter value to <span>uconf:sentinel.xfb.audit=yes</span> in the <a href="../../uconf">unified configuration</a> (UCONF).</td>
</tr>
</tbody>
</table>



**Example**



Using CFTUTIL, for example, define the parameter in UCONFSET as follows:



<table data-cellspacing="0" data-summary="Reference: code example of text">
<tbody>
<tr>
<td>CFTUTIL UCONFSET ID=sentinel.xfb.audit,

value=yes<br/>
</td>
</tr>
</tbody>
</table>



### Message Track



Message Track is an XML XFBLog message

containing:



-   Ident attribute

-   Return message attribute

-   Sentinel.xfb.audit



<span>Example </span>



/Action=CREATE /Object=CFTSEND /id=ZZ /user=My\_Company\\giovanip /groupid= /owner= /CrDate=20191204 /CrTime=17471640 /UpdDate=20191204 /UpdTime=17471640



#### <span id="Ident attribute"></span>Ident attribute details



<table data-cellspacing="0">
<thead>
<tr>
<th>CFTA0nX</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr>
<td><p>n=1</p></td>
<td>CFTPARM

file</td>
</tr>
<tr>
<td><p>n=2</p></td>
<td>CFTPART

file</td>
</tr>
<tr>
<td><p>n=3</p></td>
<td>CFTCAT

file</td>
</tr>
<tr>
<td><p>n=4</p></td>
<td>CFTCOM

file</td>
</tr>
<tr>
<td><p>n=5</p></td>
<td>CFTLOG

file</td>
</tr>
<tr>
<td><p>n=6</p></td>
<td>CFTACCNT

file</td>
</tr>
<tr>
<td><p>X=I </p></td>
<td>Information</td>
</tr>
<tr>
<td>X=E</td>
<td>Error </td>
</tr>
</tbody>
</table>



#### <span id="Return message attribute"></span>Return message attribute details



<table data-cellspacing="0">
<thead>
<tr>
<th>Attribute</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr>
<td>Action=&amp;act</td>
<td> &amp;act

is the action on an object (“CREATE” , “MODIFY” , “DELETE”)</td>
</tr>
<tr>
<td>Object=&amp;obj</td>
<td>&amp;obj is the

object identifier (type of object for the CFTFILE command)</td>
</tr>
<tr>
<td>id=&amp;id</td>
<td> </td>
</tr>
<tr>
<td>user=&amp;user</td>
<td> &amp;user

is the user that modified the object</td>
</tr>
<tr>
<td>groupid=&amp;group</td>
<td>&amp;group

is the user group that modified the object</td>
</tr>
<tr>
<td>owner=&amp;owner</td>
<td>&amp;owner

is the object owner</td>
</tr>
<tr>
<td>CrDate=&amp;cdate</td>
<td>&amp;cdate

is the Creation Date for the object</td>
</tr>
<tr>
<td>CrTime=&amp;ctime</td>
<td>&amp;ctime

is the Creation Time for the object</td>
</tr>
<tr>
<td>UpdDate=&amp;upddate</td>
<td>&amp;upddate

is the Update Date for the object</td>
</tr>
<tr>
<td>UpdTime=&amp;updtime</td>
<td>&amp;updtime

is the Update Time for the object</td>
</tr>
</tbody>
</table>
