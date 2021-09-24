{
    "title": "Stage Before repositioning",
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

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Field</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ret1</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Return code:</p>
            <ul>
               <li>0: processing 
 ok               </li>
               <li>1: restart 
 at the beginning of the file               </li>
               <li>9: refusal 
 and end of transfer               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ret2</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Error message </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>msg</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Message sent to the standard output </p>
         </td>
      </tr>
</table>

### Field values

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th> </th>
<th colspan="2">Sender mode</th>
<th colspan="2">Receiver mode</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p> </p>
         </td>
         <td colspan="2" rowspan="1">
            <p> </p>
         </td>
         <td colspan="2" rowspan="1">
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>Field</p>
         </td>
         <td>
            <p>Before</p>
         </td>
         <td>
            <p>After</p>
         </td>
         <td>
            <p>Before</p>
         </td>
         <td>
            <p>After</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>mtype</p>
         </td>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>5</p>
         </td>
         <td>
            <p>5</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>masc</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>*</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>*</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>access</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>retsync</p>
         </td>
         <td>
            <p>0</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p>0</p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ret1</p>
         </td>
         <td>
            <p>0</p>
         </td>
         <td>
            <p>*</p>
         </td>
         <td>
            <p>0</p>
         </td>
         <td>
            <p>*</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ret2</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>blank</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>*</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>blank</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>*</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>us-sem</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>us-ctx</p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
         <td>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idexit</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>exname</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>parmexit</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>version</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>language</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>reserv</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>waittask</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>part</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idf</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nidf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idt</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>direct</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>mode</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>relance</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>prot</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>prof</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>spart</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rpart</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>suser</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ruser</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fpassw</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sappl</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rappl</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>userid</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>groupid</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>exec</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fdate</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ftime</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fdisp</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>faction</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>state</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>parm</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>comment</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fname</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fdb</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fksize</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fkloc</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>flrecl</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fblksize</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>frecfm</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>frecfmx</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fspace</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ftype</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fcode</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>forg</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>facc</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fsyst</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nfname</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nfver</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nlrecl</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nblksize</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nrecfm</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nrecfmx</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nspace</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ntype</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ncode</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>norg</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nsyst</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ncomp</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>fcars</p>
         </td>
         <td>
            <p>fcars</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>fcars</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>frecs</p>
         </td>
         <td>
            <p>frecs</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>frecs</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ecars</p>
         </td>
         <td>
            <p>ecars</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>ecars</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nrecs</p>
         </td>
         <td>
            <p>nrecs</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>nrecs</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>rpos</p>
         </td>
         <td>
            <p>rpos</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>rpos</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>notify</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>msg</p>
         </td>
         <td>
            <p>blank</p>
         </td>
         <td>
            <p>*</p>
         </td>
         <td>
            <p>blank</p>
         </td>
         <td>
            <p>*</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ldata</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>/</p>
         </td>
         <td>
            <p>/</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>idtu</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
         <td>
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cMode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>cAuthPolicy</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>bCipher</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sParm</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteUserDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteIssuerDn</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteCaId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sUserCId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sCertFname</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sProf</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>sRemoteSerial</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>ExitFree</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>X</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>X</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nspart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>nrpart</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferCycleId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>XferObjectId</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
      </tr>
   </tbody>
</table>
