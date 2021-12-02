{
    "title": "Access management  reference information ",
    "linkTitle": "Reference: access management mapping",
    "weight": "220"
}This section describes how to configure access management when not using .

## Access management mapping in earlier versions

Prior to the PassPort AM implementation and interoperability, Transfer
CFT used the following Access Management setup. This information is provided as a reference.

### Access Management without PassPort AM

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
