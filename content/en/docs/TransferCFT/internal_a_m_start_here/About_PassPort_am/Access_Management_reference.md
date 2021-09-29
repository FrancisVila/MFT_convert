{
    "title": "Reference: access management mapping",
    "linkTitle": "Reference: access management mapping",
    "weight": "220"
}This section describes how to configure access management when not using Central Governance.

## Access management mapping in earlier versions

Prior to the PassPort AM implementation and interoperability, Transfer
CFT used the following Access Management setup. This information is provided as a reference.

### Access Management without PassPort AM

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>        Appl
(ID)</p>
<p>            (control:
end,halt,keep,start,submit)</p>
<p>            (create:
send,recv)</p>
<p>            (delete:
delete_catalog)</p>
<p>            (read:
view_catalog)</p>
<p>            (modify:
resume)</p>
<p>    Command:</p>
<p>          Shut</p>
<p>             create</p>
<p>          Switch_log,</p>
<p>             create</p>
<p>          Switch_accnt,</p>
<p>             create</p>
<p>          Act,</p>
<p>             create</p>
<p>          Inact,</p>
<p>              create</p>
<p>          Mquery,</p>
<p>              create</p>
<p>          Turn,</p>
<p>              create</p>
<p>    File</p>
<p>          File
(FNAME)</p>
<p>               (read)</p>
<p>               (delete)</p>
<p>    Message:</p>
<p>           Message
(IDM,PART,SPART,RPART,MODE)</p>
<p>                create</p>
<p>    Operator:</p>
<p>            ALL_PART
(fname)</p>
<p>                    create,delete,read,modify</p>
<p>            ALL_CAT
(fname)</p>
<p>                    control(see
appl), delete, read, modify (resume)</p>
<p>            ALL_COM
(fname)</p>
<p>                    create,
read, delete</p>
<p>    Parameter:</p>
<p>             CFT
obj (ID)</p>
<p>                    create,delete,read,modify</p>
<p>    Partner:</p>
<p>             CFT
obj (ID)</p>
<p>                    create,delete,read,modify
     </p>
<p>    Transfer:</p>
<p>             Transfer
(IDF,PART,SPART,RPART,IPART,MODE,FNAME)</p>
<p>                    create</p>
<p>             Commut
(PART,IPART)</p>
<p>                    create</p></td>
</tr>
</tbody>
</table>

## About resources and actions

You can map the environment variables as displayed
in the following examples.

### Configuration

    PKI....
  (ID)
Create/Delete/View/Edit (New)

    CFT....
  (ID)
Create/Delete/View/Edit

    CFTPART
  (ID)
Create/Delete/View/Edit/Turn/Activate/Deactivate

    CFTCRON
  (ID)
Create/Delete/View/Edit/Activate/Deactivate/Reload

    CFTUCONF
 (ID) Create/Delete/View/Edit
(New)

###  Service

        CATALOG
       Purge
   

        LOG
                Switch

        ACCOUNT
      Switch

        SENTINEL
     Activate/Inactivate

        BATCH(ID,FNAME)
Execute/View/Edit

        CFTNAV
         Startup/Shutdown/Restart/Trace

        CFTSRV
          Startup/Shutdown/Restart/Trace

        UI(TYPE=CFTUTIL/CFTNAVIGATOR/IUI/WEBSERVICE)
Connect                             

        PROBE(ID)
     View

        CACHE

             CATALOG
    View

             CRON
          View

             COMMAND
 View

             DMZ
            View

         COM
               Delete/View
   

### Transfer

(IDAPPL, ID, PART, SPART , RPART, IPART, TYPE, DIRECT, MODE, FNAME, MESSAGE, USERID)

          Create
  SEND/RECV

          Delete
  DELETE

          View
     LISTCAT

          Edit
      KSTATE

          Cancel
  KEEP

          Resume
 RESUME/START

          Pause
    HALT

          Execute
   

          Submit

          "End"

          ViewFile

          EditFile

          DeleteFile

###    Filter

  CATALOG(ID)
Create/Edit/View/Delete

  LOG(ID)
         Create/Edit/View/Delete

   FILE(FNAME)
       Create/Edit/View/Delete

   URL(URL)
              View
       

   \[
FILE                (FNAME)
 Create\*/View/Delete
\]

   \[
VFMFILE         (FDB,
FNAME) Create/Delete/View/Edit \]
