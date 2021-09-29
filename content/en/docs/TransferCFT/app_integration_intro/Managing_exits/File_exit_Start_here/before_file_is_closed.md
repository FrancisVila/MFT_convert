{
    "title": "Stage Before the file is closed",
    "linkTitle": "Stage Before the file is closed",
    "weight": "420"
}If the user function manages file accessing, it must close the file.

### Fields to define

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ret1</p></td>
<td><p>Return code:</p>
<ul>
<li>0: processing
ok</li>
<li>9: refusal
and end of transfer </li>
</ul></td>
</tr>
<tr class="even">
<td><p>ret2</p></td>
<td><p>Error message </p></td>
</tr>
<tr class="odd">
<td><p>msg</p></td>
<td><p>Message sent to the standard output </p></td>
</tr>
</tbody>
</table>

### Field values

<table data-cellspacing="0">
<thead>
<tr class="header">
<th> </th>
<th colspan="2">Sender mode</th>
<th colspan="2">Receiver mode</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Field</p></td>
<td><p>Before</p></td>
<td><p>After</p></td>
<td><p>Before</p></td>
<td><p>After</p></td>
</tr>
<tr class="even">
<td><p>mtype</p></td>
<td><p>7</p></td>
<td><p>7</p></td>
<td><p>7</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>masc</p></td>
<td><p>=</p></td>
<td><p>*</p></td>
<td><p>=</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>access</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>retsync</p></td>
<td><p>0</p></td>
<td><p> </p></td>
<td><p>0</p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>ret1</p></td>
<td><p>0</p></td>
<td><p>*</p></td>
<td><p>0</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>ret2</p></td>
<td><p>blank</p></td>
<td><p>*</p></td>
<td><p>blank</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>us-sem</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>us-ctx</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>idexit</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>exname</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>parmexit</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>version</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>language</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>reserv</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>waittask</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>part</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>idf</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nidf</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>idt</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>direct</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>mode</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>relance</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>prot</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>prof</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>spart</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>rpart</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>suser</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>ruser</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fpassw</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>sappl</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>rappl</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>userid</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>groupid</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>exec</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fdate</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>ftime</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fdisp</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>faction</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>state</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>parm</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>comment</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>fname</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fdb</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>fksize</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fkloc</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>flrecl</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fblksize</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>frecfm</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>frecfmx</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>fspace</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>ftype</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>fcode</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>forg</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>facc</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>fsyst</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nfname</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>nfver</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nlrecl</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>nblksize</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nrecfm</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>nrecfmx</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nspace</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>ntype</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>ncode</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>norg</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nsyst</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>ncomp</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>fcars</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="even">
<td><p>frecs</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="odd">
<td><p>ecars</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="even">
<td><p>nrecs</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="odd">
<td><p>rpos</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="even">
<td><p>notify</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>msg</p></td>
<td><p>blank</p></td>
<td><p>*</p></td>
<td><p>blank</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>ldata</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
<td><p>/</p></td>
</tr>
<tr class="odd">
<td><p>idtu</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>cMode</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>cAuthPolicy</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>bCipher</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>sParm</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>sRemoteUserDn</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>sRemoteIssuerDn</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>sRemoteCaId</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>sUserCId</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>sCertFname</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>sProf</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>sRemoteSerial</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>ExitFree</p></td>
<td><p>=</p></td>
<td><p>x</p></td>
<td><p>=</p></td>
<td><p>x</p></td>
</tr>
<tr class="even">
<td><p>nspart</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>nrpart</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="even">
<td><p>XferCycleId</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
<tr class="odd">
<td><p>XferObjectId</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
<td><p>=</p></td>
</tr>
</tbody>
</table>
