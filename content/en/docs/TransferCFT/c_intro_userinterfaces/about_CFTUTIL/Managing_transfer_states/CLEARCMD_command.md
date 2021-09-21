{
    "title": "CLEARCMD - Deleting a transfer request",
    "linkTitle": "CLEARCMD - Deleting a transfer request",
    "weight": "310"
}# <span id="kanchor78"></span><span id="Deleting_a_transfer_request"></span> CLEARCMD - Delete a command in the COM file

This page describes the <span id="CLEARCMD_command"></span>CLEARCMD. Use this
command to delete a transfer request from the communication file. A log message is generated to trace who has cleared which command.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You must include either the COMMAND or JOBNAME parameter when using this command.         </td>
      </tr>
</table>

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameters</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
            <p>COMMAND </p>
         </td>
         <td>
            <p>Request keyword.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>INDEX </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Request number as displayed by the LISTCOM command. </p>
            <p>For example:</p>
            <ul>
               <li><span>INDEX=*</span> Selects all record numbers.               </li>
               <li><span>INDEX=12345</span> Selects the record number 12345 in the COM file.               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td>JOBNAME         </td>
         <td>
            <p>Jobname   (string 15), which you can combine with wildcard characters.</p>
            <p>For example:</p>
            <ul>
               <li>JOBNAME=12345               </li>
               <li>JOBNAME=123*               </li>
               <li>JOBNAME=12?45               </li>
            </ul>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>USERID</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier of the request owner.</p>
         </td>
      </tr>
   </tbody>
</table>

### Delete a single command

To use CLEARCMD to delete a single command, the USERID, INDEX, and COMMAND parameters are mandatory.

**Example**

Begin by running the LISTCOM command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><b>cftutil listcom</b>
</p>
            <p>RECORDS</p>
            <p>RECORD N      1            ACTIVE  : YES</p>
            <p>COMMAND-TYPE : SEND        USERID  : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 17944</p>
            <p>COMMAND :</p>
            <p>part=bclpm,idf=un,fname=cc,mintime=+1</p>
         </td>
      </tr>
   </tbody>
</table>

Enter the CLEARCMD command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><strong>cftutil clearcmd userid=AXWAY\Manager,command=send,index=1</strong>
</p>
         </td>
      </tr>
   </tbody>
</table>

Repeat the LISTCOM command, and the example below displays  the results (note the record is now set to CLEARED).

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p><b>cftutil listcom</b>
</p>
            <p>RECORD N 1 ACTIVE : CLEARED</p>
            <p>COMMAND-TYPE : SEND USERID : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 17944</p>
            <p>COMMAND :</p>
            <p>On 20200203 at 161221 UserId=AXWAY\Administrator, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=1, Command=SEND'. This clears the command: UserId=AXWAY\Manager, JobName=17944, Command=SEND PART='NEWYORK'</p>
         </td>
      </tr>
</table>

### Delete a group of commands

To delete a group of commands use the following syntax.

To delete all commands=cmd for this userid:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INDEX=*,COMMAND= cmd,USERID=userid </p>
         </td>
      </tr>
   </tbody>
</table>

To delete all commands for this jobname and this userid:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INDEX=*,JOBNAME= job,USERID=userid </p>
         </td>
      </tr>
   </tbody>
</table>

To delete all commands=cmd for this jobname and this userid:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>INDEX=*,JOBNAME= job,COMMAND=cmd ,USERID=userid</p>
         </td>
      </tr>
   </tbody>
</table>

**Example**

To delete all RECV commands that have the JOBNAME 9168 for the Axway/Manager account user begin by executing the LISTCOM command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><b>cftutil listcom</b>
</p>
            <p>RECORD N      3            ACTIVE  : YES</p>
            <p>COMMAND-TYPE : RECV        USERID  : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 9168</p>
            <p>COMMAND :</p>
            <p>part=loop,idf=*</p>
            <p>RECORD N      4            ACTIVE  : YES</p>
            <p>COMMAND-TYPE : RECV        USERID  : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 9168</p>
            <p>COMMAND :</p>
            <p>part=pesit1,idf=*</p>
         </td>
      </tr>
   </tbody>
</table>

Enter the CLEARCMD command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><strong>cftutil clearcmd userid=AXWAY\Manager,command=recv,index=*,jobname=9168</strong>
</p>
         </td>
      </tr>
   </tbody>
</table>

Run LISTCOM; the selected records now display as CLEARED.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><b>cftutil listcom</b>
</p>
            <p>RECORD N      3            ACTIVE  : CLEARED</p>
            <p>COMMAND-TYPE : RECV        USERID  : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 9168</p>
            <p>COMMAND :</p>
            <p>On 20200203 at 161221 UserId=AXWAY\Manager, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=*, JobName=9168, Command=RECV'. This clears the command: UserId=AXWAY\Manager, JobName=9168, Command=RECV part=loop,idf=*</p>
            <p>RECORD N 4 ACTIVE : CLEARED</p>
            <p>COMMAND-TYPE : RECV USERID : AXWAY\Manager</p>
            <p>GROUPID :</p>
            <p>JOBNAME : 9168</p>
            <p>COMMAND :</p>
            <p>On 20200203 at 161221 UserId=AXWAY\Manager, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=*, JobName=9168, Command=RECV'. This clears the command: UserId=AXWAY\Manager, JobName=9168, Command=RECV part=pesit1,idf=*</p>
         </td>
      </tr>
   </tbody>
</table>

### Syntax error

The following is a list of error and information messages that display.

**Error 1**

CFTU26E CLEARCMD \_ Error (Index value not authorized\_ Bad command)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=4\*,command=recv)

 

**Error 2**

CFTU26E CLEARCMD \_ Error (COMMAND Keyword missing)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=4,jobname=1234)

 

**Error 3**

CFTU26E CLEARCMD \_ Error (COMMAND or JOBNAME Keyword missing)

CFTU00I CLEARCMD \_ Failed (userid=AXWAY\\Manager,index=\*)
