{
    "title": "CLEARCMD - Delete a command in the COM file",
    "linkTitle": "Delete a command in the COM file",
    "weight": "310"
}This page describes the <span id="CLEARCMD_command"></span>CLEARCMD. Use this
command to delete a transfer request from the communication file. A log message is generated to trace who has cleared which command.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>You must include either the COMMAND or JOBNAME parameter when using this command.         </td>
      </tr>
   </tbody>
</table>

<table>
         
         
         
   
   <th>
      <tr>
<th>Parameters         </th>
<th>Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>COMMAND</p>         </td>
         <td><p>Request keyword.</p>         </td>
      </tr>
      <tr>
         <td><p>INDEX</p>         </td>
         <td><p>Request number as displayed by the LISTCOM command.</p>
<p>For example:</p>
<ul>
<li><span class="code">INDEX=*</span> Selects all record numbers.</li>
<li><span class="code">INDEX=12345</span> Selects the record number 12345 in the COM file.</li>
</ul>         </td>
      </tr>
      <tr>
         <td>JOBNAME         </td>
         <td><p>Jobname (string 15), which you can combine with wildcard characters.</p>
<p>For example:</p>
<ul>
<li>JOBNAME=12345</li>
<li>JOBNAME=123*</li>
<li>JOBNAME=12?45</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>USERID</p>         </td>
         <td><p>Identifier of the request owner.</p>         </td>
      </tr>
   </tbody>
</table>

### Delete a single command

To use CLEARCMD to delete a single command, the USERID, INDEX, and COMMAND parameters are mandatory.

**Example**

Begin by running the LISTCOM command.



    cftutil listcom

    RECORDS
    RECORD N      1            ACTIVE  : YES
    COMMAND-TYPE : SEND        USERID  : AXWAY\Manager
    GROUPID :
    JOBNAME : 17944
    COMMAND :
    part=bclpm,idf=un,fname=cc,mintime=+1

Enter the CLEARCMD command.



    cftutil clearcmd userid=AXWAY\Manager,command=send,index=1

Repeat the LISTCOM command, and the example below displays  the results (note the record is now set to CLEARED).


    cftutil listcom

    RECORD N 1 ACTIVE : CLEARED
    COMMAND-TYPE : SEND USERID : AXWAY\Manager
    GROUPID :
    JOBNAME : 17944
    COMMAND :
    On 20200203 at 161221 UserId=AXWAY\Administrator, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=1, Command=SEND'. This clears the command: UserId=AXWAY\Manager, JobName=17944, Command=SEND PART='NEWYORK'

### Delete a group of commands

To delete a group of commands use the following syntax.

To delete all commands=cmd for this userid:



    INDEX=*,COMMAND= cmd,USERID=userid 

To delete all commands for this jobname and this userid:



    INDEX=*,JOBNAME= job,USERID=userid 

To delete all commands=cmd for this jobname and this userid:



    INDEX=*,JOBNAME= job,COMMAND=cmd ,USERID=userid

**Example**

To delete all RECV commands that have the JOBNAME 9168 for the Axway/Manager account user begin by executing the LISTCOM command.



    cftutil listcom

    RECORD N      3            ACTIVE  : YES
    COMMAND-TYPE : RECV        USERID  : AXWAY\Manager
    GROUPID :
    JOBNAME : 9168
    COMMAND :
    part=loop,idf=*
    RECORD N      4            ACTIVE  : YES
    COMMAND-TYPE : RECV        USERID  : AXWAY\Manager
    GROUPID :
    JOBNAME : 9168
    COMMAND :
    part=pesit1,idf=*

Enter the CLEARCMD command.



    cftutil clearcmd userid=AXWAY\Manager,command=recv,index=*,jobname=9168

Run LISTCOM; the selected records now display as CLEARED.



    cftutil listcom

    RECORD N      3            ACTIVE  : CLEARED
    COMMAND-TYPE : RECV        USERID  : AXWAY\Manager
    GROUPID :
    JOBNAME : 9168
    COMMAND :
    On 20200203 at 161221 UserId=AXWAY\Manager, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=*, JobName=9168, Command=RECV'. This clears the command: UserId=AXWAY\Manager, JobName=9168, Command=RECV part=loop,idf=*
    RECORD N 4 ACTIVE : CLEARED
    COMMAND-TYPE : RECV USERID : AXWAY\Manager
    GROUPID :
    JOBNAME : 9168
    COMMAND :
    On 20200203 at 161221 UserId=AXWAY\Manager, JobName=20144 ran the command 'CLEARCMD UserId=AXWAY\Manager, Index=*, JobName=9168, Command=RECV'. This clears the command: UserId=AXWAY\Manager, JobName=9168, Command=RECV part=pesit1,idf=*

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
