{
    "title": "Stage After a transfer interruption",
    "linkTitle": "Stage After a transfer interruption",
    "weight": "400"
}This event occurs if there is a:

-   Mains supply cut
    or protocol fault
-   Request by one
    of the partners (HALT or KEEP command)
-   Request by the
    user function during one of the previous stages (ret1 = 9)

If the user function manages file accessing, it must de-allocate the
file and save the zwork working area for subsequent restarting purposes,
before handing back control to Transfer CFT.

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
               <li>9: refusal 
 and end of transfer                </li>
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
      <tr>
         <td colspan="1" rowspan="1">
            <p>exec</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the end of transfer procedure </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>state</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Transfer state ('H' or 'K')</p>
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
            <p>9</p>
         </td>
         <td>
            <p>9</p>
         </td>
         <td>
            <p>9</p>
         </td>
         <td>
            <p>9</p>
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
            <p>x</p>
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
            <p>frecs</p>
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
            <p>ecars</p>
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
            <p>nrecs</p>
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
            <p>rpos</p>
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
            <p>x</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>=</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>x</p>
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
            <p>XferObjectcId</p>
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
