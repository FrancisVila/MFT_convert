{
    "title": "Use the communication structure",
    "linkTitle": "Using the communication structure",
    "weight": "360"
}The following topics describe the stages in a file transfer. These are:

-   [Before
    the file is allocated](#Before_the_File_is_Allocated)
-   [Before
    the file is opened](#Before_the_File_is_Opened)
-   [Before
    the start of the transfer](#Before_the_Start_of_the_Transfer)
-   [Before
    a record is sent or after it is received](#Before_a_Record_is_Sent_or_After_it_is_Received)
-   Before
    repositioning
-   After
    a synchronization point
-   Before
    the end of the file
-   Before
    the file is closed
-   Before
    the end of the transfer
-   After
    a transfer interruption

Each stage is explained in a table as follows:

-   Fields to define - the first table indicates the fields that you must update
-   Field values - the second table indicates the
    values for each field of the communication area as seen from the sender
    or the receiver side before and after the call.  

The symbols used are indicated in the following table.

<table>
   <th>
      <tr>
<th>Symbol         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>/</p>         </td>
         <td><p>This field does not apply to  the
current field </p>         </td>
      </tr>
      <tr>
         <td><p>=</p>         </td>
         <td><p>This field keeps the value taken in the previous stage </p>         </td>
      </tr>
      <tr>
         <td><p>x</p>         </td>
         <td><p>This field can be modified by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
(before the call) or by the user function (after the call) </p>         </td>
      </tr>
      <tr>
         <td><p>*</p>         </td>
         <td><p>This field can be defined by the user function </p>         </td>
      </tr>
   </tbody>
</table>

The return code (ret1) must always be defined.

<span id="Before_the_File_is_Allocated"></span>

## Before the file is allocated

This is the first stage in a file transfer. During this stage, you indicate
the stages at which you want to take control by defining the masc parameter.

<span id="Fields_to_define"></span>

### Fields to define

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>masc</p>         </td>
         <td><p>Mask used to select stages </p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>File access:</p>
<ul>
<li>0: controlled
by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span></li>
<li>1: controlled
by the user</li>
</ul>         </td>
      </tr>
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
   </tbody>
</table>

<span id="Field_values"></span>

### Field values

<table>
   <th>
      <tr>
<th>          </th>
<th>Sender mode         </th>
<th>Receiver mode         </th>
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
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
      </tr>
      <tr>
         <td><p>masc</p>         </td>
         <td><p>10000000...000</p>         </td>
         <td><p>*</p>         </td>
         <td><p>10000000...000</p>         </td>
         <td><p>*</p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>0</p>         </td>
         <td><p>*</p>         </td>
         <td><p>0</p>         </td>
         <td><p>*</p>         </td>
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
         <td><p>IDEXIT</p>         </td>
         <td><p>=</p>         </td>
         <td><p>IDEXIT</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>exname</p>         </td>
         <td><p> </p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>parmexit</p>         </td>
         <td><p>PARM</p>         </td>
         <td><p>=</p>         </td>
         <td><p>PARM</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>version</p>         </td>
         <td><p>FORMAT</p>         </td>
         <td><p>=</p>         </td>
         <td><p>FORMAT</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>LANGUAGE</p>         </td>
         <td><p>=</p>         </td>
         <td><p>LANGUAGE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>reserv</p>         </td>
         <td><p>RESERV</p>         </td>
         <td><p>=</p>         </td>
         <td><p>RESERV</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>waittask</p>         </td>
         <td><p>WAITTASK</p>         </td>
         <td><p>=</p>         </td>
         <td><p>WAITTASK</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>PART</p>         </td>
         <td><p>=</p>         </td>
         <td><p>PART</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>idf</p>         </td>
         <td><p>IDF</p>         </td>
         <td><p>=</p>         </td>
         <td><p>IDF</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nidf</p>         </td>
         <td><p>NIDF</p>         </td>
         <td><p>=</p>         </td>
         <td><p>NIDF</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>idt</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>=</p>         </td>
         <td><p>IDT</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>direct</p>         </td>
         <td><p>DIRECT</p>         </td>
         <td><p>=</p>         </td>
         <td><p>DIRECT</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>MODE</p>         </td>
         <td><p>=</p>         </td>
         <td><p>MODE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>relance</p>         </td>
         <td><p>RELANCE</p>         </td>
         <td><p>=</p>         </td>
         <td><p>RELANCE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>prot</p>         </td>
         <td><p>PROT</p>         </td>
         <td><p>=</p>         </td>
         <td><p>PROT</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>prof</p>         </td>
         <td><p>PROF</p>         </td>
         <td><p>=</p>         </td>
         <td><p>PROF</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>spart</p>         </td>
         <td><p>SPART</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SPART</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>rpart</p>         </td>
         <td><p>RPART</p>         </td>
         <td><p>=</p>         </td>
         <td><p>RPART</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>suser</p>         </td>
         <td><p>SUSER</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SUSER</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ruser</p>         </td>
         <td><p>RUSER</p>         </td>
         <td><p>=</p>         </td>
         <td><p>RUSER</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fpassw</p>         </td>
         <td><p>FPASSW</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FPASSW</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sappl</p>         </td>
         <td><p>SAPPL</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SAPPL</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>rappl</p>         </td>
         <td><p>RAPPL</p>         </td>
         <td><p>=</p>         </td>
         <td><p>RAPPL</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td><p>USERID</p>         </td>
         <td><p>x</p>         </td>
         <td><p>USERID</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>groupid</p>         </td>
         <td><p>GROUPID</p>         </td>
         <td><p>x</p>         </td>
         <td><p>GROUPID</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>exec</p>         </td>
         <td><p>EXEC</p>         </td>
         <td><p>=</p>         </td>
         <td><p>EXEC</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fdate</p>         </td>
         <td><p>FDATE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FDATE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>ftime</p>         </td>
         <td><p>FTIME</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FTIME</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fdisp</p>         </td>
         <td><p>FDISP</p>         </td>
         <td><p>=</p>         </td>
         <td><p>FDISP</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>faction</p>         </td>
         <td><p>FACTION</p>         </td>
         <td><p>=</p>         </td>
         <td><p>FACTION</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>STATE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>STATE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>PARM</p>         </td>
         <td><p>x</p>         </td>
         <td><p>PARM</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>COMMENT</p>         </td>
         <td><p>x</p>         </td>
         <td><p>COMMENT</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fname</p>         </td>
         <td><p>FNAME</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FNAME</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fksize</p>         </td>
         <td><p>FKEYSIZE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FKEYSIZE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fkloc</p>         </td>
         <td><p>FKEYPOS</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FKEYPOS</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>FLRECL</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FLRECL</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>FBLKSIZE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FBLKSIZE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>FRECFM</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FRECFM</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>frecfmx</p>         </td>
         <td><p>FRECFMX</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FRECFMX</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>FSPACE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FSPACE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>FTYPE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FTYPE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>FCODE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FCODE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>FORG</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FORG</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>facc</p>         </td>
         <td><p>FACC</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FACC</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>fsyst</p>         </td>
         <td><p>FSYST</p>         </td>
         <td><p>x</p>         </td>
         <td><p>FSYST</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>nfname</p>         </td>
         <td><p>NFNAME</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NFNAME</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nfver</p>         </td>
         <td><p>NFVER</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NFVER</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nlrecl</p>         </td>
         <td><p>NLRECL</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NLRECL</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nblksize</p>         </td>
         <td><p>NBLKSIZE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NBLKSIZE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfm</p>         </td>
         <td><p>NRECFM</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NRECFM</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfmx</p>         </td>
         <td><p>NRECFMX</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NRECFMX</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nspace</p>         </td>
         <td><p>NSPACE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NSPACE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>NTYPE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NTYPE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ncode</p>         </td>
         <td><p>NCODE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NCODE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>norg</p>         </td>
         <td><p>NORG</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NORG</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nsyst</p>         </td>
         <td><p>NSYST</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NSYST</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ncomp</p>         </td>
         <td><p>NCOMP</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NCOMP</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>NOTIFY</p>         </td>
         <td><p>x</p>         </td>
         <td><p>NOTIFY</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>IDTU</p>         </td>
         <td><p>=</p>         </td>
         <td><p>IDTU</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>cMode</p>         </td>
         <td><p>CMODE</p>         </td>
         <td><p>=</p>         </td>
         <td><p>CMODE</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>cAuthPolicy</p>         </td>
         <td><p>CAUTHPOLICY</p>         </td>
         <td><p>=</p>         </td>
         <td><p>CAUTHPOLICY</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>bCipher</p>         </td>
         <td><p>BCIPHER</p>         </td>
         <td><p>=</p>         </td>
         <td><p>BCIPHER</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sParm</p>         </td>
         <td><p>SPARM</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SPARM</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteUserDn</p>         </td>
         <td><p>SREMOTEUSERDN</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SREMOTEUSERDN</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteIssuerDn</p>         </td>
         <td><p>SREMOTEISSUERDN</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SREMOTEISSUERDN</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteCaId</p>         </td>
         <td><p>SREMOTECAID</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SREMOTECAID</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sUserCId</p>         </td>
         <td><p>SUSERCID</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SUSERCID</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sCertFname</p>         </td>
         <td><p>SCERTFNAME</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SCERTFNAME</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sProf</p>         </td>
         <td><p>SPROF</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SPROF</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteSerial</p>         </td>
         <td><p>SREMOTESERIAL</p>         </td>
         <td><p>=</p>         </td>
         <td><p>SREMOTESERIAL</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>EXITFREE</p>         </td>
         <td><p>x</p>         </td>
         <td><p>EXITFREE</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>NSPART</p>         </td>
         <td><p>=</p>         </td>
         <td><p>NSPART</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>NRPART</p>         </td>
         <td><p>=</p>         </td>
         <td><p>NRPART</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>XferCycleId</p>         </td>
         <td><p>TRKR</p>         </td>
         <td><p>=</p>         </td>
         <td><p>TRKR</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>XferObjectcId</p>         </td>
         <td><p>"XFBTransfer"</p>         </td>
         <td><p>=</p>         </td>
         <td><p>"XFBTransfer"</p>         </td>
         <td><p>=</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Before_the_File_is_Opened"></span>

## Before the file is opened

If the user function manages file accessing, it must open the file at
this stage.

### Fields to define

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Meaning         </th>
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
   </tbody>
</table>

### Field values

<table>
   <th>
      <tr>
<th>          </th>
<th>Sender mode         </th>
<th>Receiver mode         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>Field</p>         </td>
         <td><p>Before</p>         </td>
         <td><p>After</p>         </td>
         <td><p>Before</p>         </td>
         <td><p>After</p>         </td>
      </tr>
      <tr>
         <td><p>mtype</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
         <td><p>1</p>         </td>
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
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fkloc</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>frecfmx</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>facc</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nblksize</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nrecfmx</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>nspace</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>ncode</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>norg</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>XferObjectId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Before_the_Start_of_the_Transfer"></span>

## Before the start of the transfer

Only a File type EXIT at the sender end, DIRECT = S’ can process this
stage.

### Fields to define

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Description         </th>
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
   </tbody>
</table>

### Field values

<table>
   <th>
      <tr>
<th>          </th>
<th>Sender mode         </th>
<th>Receiver mode         </th>
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
         <td><p>2</p>         </td>
         <td><p>2</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>masc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>*</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>access</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>retsync</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>*</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ret2</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
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
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>exname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>parmexit</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>version</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>language</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>reserv</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>waittask</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>part</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>idf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nidf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>idt</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>direct</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>mode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>relance</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>prot</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>prof</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>spart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>rpart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>suser</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ruser</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fpassw</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sappl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>rappl</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>userid</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>groupid</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>exec</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fdate</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ftime</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fdisp</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>faction</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>state</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>parm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>comment</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fdb</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fksize</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fkloc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>flrecl</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fblksize</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>frecfm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>frecfmx</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fspace</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ftype</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fcode</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>forg</p>         </td>
         <td><p>x</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>facc</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fsyst</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nfname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nfver</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nlrecl</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nblksize</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nrecfm</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nrecfmx</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nspace</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ntype</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ncode</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>norg</p>         </td>
         <td><p>x</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nsyst</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ncomp</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>fcars</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>frecs</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ecars</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nrecs</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>rpos</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>notify</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>msg</p>         </td>
         <td><p>blank</p>         </td>
         <td><p>*</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ldata</p>         </td>
         <td><p>/</p>         </td>
         <td><p>/</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>idtu</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cMode</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>cAuthPolicy</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>bCipher</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sParm</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteUserDn</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteIssuerDn</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sRemoteCaId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sUserCId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sCertFname</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>sProf</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ExitFree</p>         </td>
         <td><p>=</p>         </td>
         <td><p>x</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nspart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>nrpart</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>XferCycleId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>XferObjectId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
      </tr>
   </tbody>
</table>

<span id="Before_a_Record_is_Sent_or_After_it_is_Received"></span>

## Before a record is sent or after it is received

At the sender end, DIRECT =
S, the user function is called before the record is sent to the
remote site, and after the record is read if <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> manages file
accessing. If file accessing is managed by the user function, the latter
has to read the record and define the ldata field as well as the zdata
parameter before handing back control to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

At the receiver end, DIRECT = R,
the user function is called after the record is received, and before the
record is written if <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> manages file accessing. If file accessing
is managed by the user function, the latter has to write the record before
handing back control to <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

At this stage (DATA\_TYP) and before the record is sent or after it is
received, the user function can perform the following operations:

-   Modify the record
    sent or to be sent
-   Insert one or more
    records
-   Delete the record
-   Set the "END
    of FILE" event

### Fields to define

<table>
   <th>
      <tr>
<th>Field         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ret1</p>         </td>
         <td><p>Return code:</p>
<ul>
<li>0 = processing
ok.<br />
Record not modified</li>
<li>4 = end
of file<br />
The previous record becomes the last one</li>
<li>9 = refusal
and end of transfer</li>
</ul>
<p>If file accessing is managed by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>:</p>
<ul>
<li>1 = record
modified<br />
The user function must modify the ldata field and the zdata parameter.
The record length must be consistent with the value of the flrecl field
in order not to cause a read or write error.</li>
<li>2 = one
or more records inserted<br />
At the time the first record is inserted, you can save the current
record in the zwork working area before handing back control to Transfer
CFT. In the insertion mode (as long as ret1 = 2), the zdata is not defined
by <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> in the following DATA_TYP stages and the user can continue
to insert as many records as required.</li>
<li>3 = record
deleted <br />
On returning from the user function, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> ignores the current
record. The record is not sent when in send mode, and not written into
the file when in receive mode.</li>
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
         <td><p>ldata</p>         </td>
         <td><p>Record length (in bytes) </p>         </td>
      </tr>
   </tbody>
</table>

#### Compression

Records are compressed as a result of a negotiation between the sender
partner and the receiver partner. At the
sender end, records are compressed before being sent by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. At the receiver end, the
records are decompressed by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> immediately after
they are received. The records <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> supplies to the user function
are never in compressed form.

The ncomp field designates the compression algorithm used. The default
value of this field is the value specified in the NCOMP parameter of the
CFTSEND or CFTRECV command associated with the File type EXIT.

The user function can modify the ncomp field at the first stage in the
transfer (ALLOC\_TYP). A zero value inhibits compression.

### Field values

<table>
   <th>
      <tr>
<th>          </th>
<th>Sender mode         </th>
<th>Receiver mode         </th>
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
         <td><p>3</p>         </td>
         <td><p>3</p>         </td>
         <td><p>3</p>         </td>
         <td><p>3</p>         </td>
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
         <td><p>=</p>         </td>
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
         <td><p>x</p>         </td>
         <td><p>/</p>         </td>
         <td><p>x</p>         </td>
      </tr>
      <tr>
         <td><p>frecs</p>         </td>
         <td><p>/</p>         </td>
         <td><p>x</p>         </td>
         <td><p>/</p>         </td>
         <td><p>x</p>         </td>
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
         <td><p>*</p>         </td>
         <td><p>ldata</p>         </td>
         <td><p>*</p>         </td>
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
         <td><p>XferObjectId</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
         <td><p>=</p>         </td>
      </tr>
   </tbody>
</table>
