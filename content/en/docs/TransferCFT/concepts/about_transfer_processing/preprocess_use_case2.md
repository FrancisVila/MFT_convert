{
    "title": "Use case: replace variable and zip file",
    "linkTitle": "Usage: zip a file before sending",
    "weight": "210"
}**Example in UNIX**

This use case demonstrates how to replace a variable in a file, and then zip the file prior to processing the transfer.

1.  In a command line window, enter: <span class="code">cd $CFTDIRRUNTIME</span>

2.  Create your sample file: <span class="code">echo “Hello \_user\_” > Hello</span>

    In this example the <span class="bold_in_para">Hello </span>file is in $CFTDIRRUNTIME.  

3.  Create and display your sample script <span class="code">cat myexec.sh:</span>

        ! /bin/sh
        if [ "&APPSTATE" = "" ]; then
        CFTUTIL end part=&PART,idtu=&IDTU,istate=yes,appstate="0%"
        fi
        if [ "&APPSTATE" = "0%" -o "&APPSTATE" = "" ]; then
        tmpfile=&FNAME_&PART
        sed s/_user_/&PART/g <&FNAME >$tmpfile
        CFTUTIL end part=&PART,idtu=&IDTU,istate=yes,appstate="50%",fname=$tmpfile
        else
        tmpfile=&FNAME
        fi
        if [ "&APPSTATE" = "50%" -o "&APPSTATE" = "0%" -o "&APPSTATE" = "" ]; then
        outputfile=$tmpfile.tgz
        tar zcvf $outputfile $tmpfile
        CFTUTIL end part=&PART,idtu=&IDTU,istate=no,appstate="100%",fname=$outputfile
        rm $tmpfile
        fi

4.  Execute the following command, where <span class="code">preexec </span>points to your script:

    CFTUTIL send part=paris,idf=test,fname=$CFTDIRRUNTIME/Hello,preexec=$CFTDIRRUNTIME/myexec.sh

Results

The script replaces <span class="code"> \_user\_</span> in the <span class="bold_in_para">Hello </span>file with the PARTNER name, and then compress this modified file. At the end of the preprocessing , the tar file is sent to the partner. The partner can set an exec for this idf, <span class="code">test </span>in our example, that will untar the received file.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>Notification is done by the <span class="code">CFTUTIL end istate=no</span>, where no is the default istate value.         </td>
      </tr>
   </tbody>
</table>