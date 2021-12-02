{
    "title": "Use case: replace variable and zip file",
    "linkTitle": "Usage: zip a file before sending",
    "weight": "210"
}**Example in UNIX**

This use case demonstrates how to replace a variable in a file, and then zip the file prior to processing the transfer.

1.  In a command line window, enter: `cd $CFTDIRRUNTIME`

2.  Create your sample file: `echo “Hello _user_” > Hello`

    In this example the **Hello** file is in $CFTDIRRUNTIME.  

3.  Create and display your sample script `cat myexec.sh:`

4.  Execute the following command, where `preexec `points to your script:

    CFTUTIL send part=paris,idf=test,fname=$CFTDIRRUNTIME/Hello,preexec=$CFTDIRRUNTIME/myexec.sh

Results

The script replaces ` _user_` in the **Hello** file with the PARTNER name, and then compress this modified file. At the end of the preprocessing , the tar file is sent to the partner. The partner can set an exec for this idf, `test `in our example, that will untar the received file.

> **Note:**
>
> Notification is done by the CFTUTIL end istate=no, where no is the default istate value.
