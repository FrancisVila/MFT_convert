{
    "title": "After a transfer interruption",
    "linkTitle": "Stage After a transfer interruption",
    "weight": "370"
}This event occurs if there is a:

-   Mains supply cut
    or protocol fault
-   Request by one
    of the partners (HALT or KEEP command)
-   Request by the
    user function during one of the previous stages (ret1 = 9)

If the user function manages file accessing, it must de-allocate the
file and save the zwork working area for subsequent restarting purposes,
before handing back control to {{< TransferCFT/componentshortname  >}}.

### Fields to define

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>Return code:</p>
<ul>
<li>0: processing
ok</li>
<li>9: refusal
and end of transfer </li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ret2</p>         </td>
         <td><p>Error message </p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>Message sent to the standard output </p>         </td>
      </tr>
      <tr>
         <td><p>exec</p>         </td>
         <td><p>Name of the end of transfer procedure </p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>Transfer state ('H' or 'K')</p>         </td>
      </tr>
   </tbody>
</table>

### Field values

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">          </th>
<th colspan="2" class="HeadE-Column1-Header1">Sender mode         </th>
<th colspan="2" class="HeadD-Column1-Header1">Receiver mode         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Before</p>         </td>
         <td><p>After</p>         </td>
         <td><p>Before</p>         </td>
         <td><p>After</p>         </td>
      </tr>
      <tr>
         <td><p>mtype</p>         </td>
         <td><p>9</p>         </td>
         <td><p>9</p>         </td>
         <td><p>9</p>         </td>
         <td><p>9</p>         </td>
      </tr>
      <tr>
         <td><p>masc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>*</p>         </td>
         <td><p>=</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>retsync</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>*</p>         </td>
         <td><p>0</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>ret2</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>us-sem</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>us-ctx</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>idexit</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>exname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>parmexit</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>version</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>reserv</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>waittask</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>idf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nidf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>idt</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>direct</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>relance</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>prot</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>prof</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>spart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>rpart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>suser</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ruser</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fpassw</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sappl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>rappl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>groupid</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>exec</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fdate</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ftime</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fdisp</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>faction</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fdb</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fksize</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fkloc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>frecfmx</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>facc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fsyst</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nfname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nfver</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nlrecl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nblksize</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfm</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfmx</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nspace</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ncode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>norg</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nsyst</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ncomp</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fcars</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>frecs</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>ecars</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>nrecs</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>rpos</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>notify</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>ldata</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>idtu</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>cMode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>cAuthPolicy</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>bCipher</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sParm</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteUserDn</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteIssuerDn</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteCaId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sUserCId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sCertFname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sProf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteSerial</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>=</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>XferCycleId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>XferObjectcId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
   </tbody>
</table>
