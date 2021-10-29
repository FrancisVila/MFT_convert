{
    "title": "Before repositioning",
    "linkTitle": "Stage Before repositioning",
    "weight": "430"
}At the receiver end (DIRECT = R)
with file accessing managed by the user, the user function has to reposition
using the information (rpos, frecs and fcars) the Transfer CFT provides.

At the sender end (DIRECT = S) or
if file accessing is managed by Transfer CFT, the Transfer CFT
has all the information it requires for repositioning.

In both cases, you can request the restart of the transfer  from
the beginning of the file by setting the ret1 field to 1.

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
         <td>            <p>ret1</p>         </td>
         <td>            <p>Return code:</p>
            <ul>
               <li>0: processing
ok               </li>
               <li>1: restart
at the beginning of the file               </li>
               <li>9: refusal
and end of transfer               </li>
            </ul>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ret2</p>         </td>
         <td>            <p>Error message </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>msg</p>         </td>
         <td>            <p>Message sent to the standard output </p>         </td>
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
         <td>            <p> </p>         </td>
         <td colspan="2">            <p> </p>         </td>
         <td colspan="2">            <p> </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>Field</p>         </td>
         <td>            <p>Before</p>         </td>
         <td>            <p>After</p>         </td>
         <td>            <p>Before</p>         </td>
         <td>            <p>After</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>mtype</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>5</p>         </td>
         <td>            <p>5</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>masc</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>*</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>access</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>retsync</p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p> </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>ret1</p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>0</p>         </td>
         <td>            <p>*</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ret2</p>         </td>
         <td>            <p>blank</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>blank</p>         </td>
         <td>            <p>*</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>us-sem</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>us-ctx</p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
         <td>            <p> </p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>idexit</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>exname</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>parmexit</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>version</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>language</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>reserv</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>waittask</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>part</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>idf</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nidf</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>idt</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>direct</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>mode</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>relance</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>prot</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>prof</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>spart</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>rpart</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>suser</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ruser</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fpassw</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>sappl</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>rappl</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>userid</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>groupid</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>exec</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fdate</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ftime</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fdisp</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>faction</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>state</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>parm</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>comment</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>fname</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fdb</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>fksize</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fkloc</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>flrecl</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fblksize</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>frecfm</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>frecfmx</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>fspace</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>ftype</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>fcode</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>forg</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>facc</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>fsyst</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nfname</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>nfver</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nlrecl</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>nblksize</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nrecfm</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>nrecfmx</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nspace</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>ntype</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ncode</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>norg</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nsyst</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>ncomp</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>fcars</p>         </td>
         <td>            <p>fcars</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>fcars</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>frecs</p>         </td>
         <td>            <p>frecs</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>frecs</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ecars</p>         </td>
         <td>            <p>ecars</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>ecars</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>nrecs</p>         </td>
         <td>            <p>nrecs</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>nrecs</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>rpos</p>         </td>
         <td>            <p>rpos</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>rpos</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>notify</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>msg</p>         </td>
         <td>            <p>blank</p>         </td>
         <td>            <p>*</p>         </td>
         <td>            <p>blank</p>         </td>
         <td>            <p>*</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>ldata</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>/</p>         </td>
         <td>            <p>/</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>idtu</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>cMode</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>cAuthPolicy</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>bCipher</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>sParm</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>sRemoteUserDn</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>sRemoteIssuerDn</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>sRemoteCaId</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>sUserCId</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>sCertFname</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>sProf</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>sRemoteSerial</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>ExitFree</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>X</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>X</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>nspart</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>nrpart</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="odd">
         <td>            <p>XferCycleId</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
      <tr class="even">
         <td>            <p>XferObjectId</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
         <td>            <p>=</p>         </td>
      </tr>
   </tbody>
</table>
