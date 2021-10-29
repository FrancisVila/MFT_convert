{
    "title": "Use case: replace variable and zip file",
    "linkTitle": "Usage: zip a file before sending",
    "weight": "220"
}**Example in UNIX**

This use case demonstrates how to replace a variable in a file, and then zip the file prior to processing the transfer.

1.  In a command line window, enter: cd $CFTDIRRUNTIME

2.  Create your sample file: echo “Hello \_user\_” > Hello

    In this example the Hello file is in $CFTDIRRUNTIME.  

3.  Create and display your sample script cat myexec.sh:
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>! /bin/sh</p>
                <p>if [ "&amp;APPSTATE" = "" ]; then</p>
                <p>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=yes,appstate="0%"</p>
                <p>fi</p>
                <p>if [ "&amp;APPSTATE" = "0%" -o "&amp;APPSTATE" = "" ]; then</p>
                <p>tmpfile=&amp;FNAME_&amp;PART</p>
                <p>sed s/_user_/&amp;PART/g &lt;&amp;FNAME &gt;$tmpfile</p>
                <p>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=yes,appstate="50%",fname=$tmpfile</p>
                <p>else</p>
                <p>tmpfile=&amp;FNAME</p>
                <p>fi</p>
                <p>if [ "&amp;APPSTATE" = "50%" -o "&amp;APPSTATE" = "0%" -o "&amp;APPSTATE" = "" ]; then</p>
                <p>outputfile=$tmpfile.tgz</p>
                <p>tar zcvf $outputfile $tmpfile</p>
                <p>CFTUTIL end part=&amp;PART,idtu=&amp;IDTU,istate=no,appstate="100%",fname=$outputfile</p>
                <p>rm $tmpfile</p>
                <p>fi</p>         </td>
          </tr>
       </tbody>
    </table>

4.  Execute the following command, where preexec points to your script:

    CFTUTIL send part=paris,idf=test,fname=$CFTDIRRUNTIME/Hello,preexec=$CFTDIRRUNTIME/myexec.sh

Results

The script replaces \_user\_ in the Hello file with the PARTNER name, and then compress this modified file. At the end of the preprocessing , the tar file is sent to the partner. The partner can set an exec for this idf, test in our example, that will untar the received file.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Notification is done by the <span>CFTUTIL end istate=no</span>, where no is the default istate value.         </td>
      </tr>
   </tbody>
</table>
