{
    "title": "Troubleshoot the Copilot server",
    "linkTitle": "Troubleshoot the Copilot server",
    "weight": "270"
}## Failed cftsu

### UNIX

Create process as user is not set correctly

If the UCONF parameter copilot.misc.createprocessasuser=NO, the cftsu process cannot start. Check and set to YES.

There is an incorrect setting in cftsu

The following message may be due to one of the causes listed below.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>/home/cft/company/Transfer_CFT/home/bin/<strong>cftsu must be launch as setuid root!</strong>         </td>
      </tr>
   </tbody>
</table>

1.  The owner is not root. Check:  

    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>ls -l cftsu-rwsrwxrwx 1 cft cft cftsu         </td>
          </tr>
       </tbody>
    </table>

    Fix: Set the root using the chown root:root &lt;file> command.

    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>ls -l cftsu-rwsrwxrwx 1 <span>root root</span> cftsu         </td>
          </tr>
       </tbody>
    </table>

2.  The setuid option (s) is not set for the cftsu file. Check:  

    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>ls -l cftsu-rwxrwxrwx 1 root root cftsu</p>         </td>
          </tr>
       </tbody>
    </table>

    Fix: Set using the chmod u+s &lt;file> command.

    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>ls -l cftsu</p>
                <p>-rw<u>s</u>rwxrwx 1 root root cftsu</p>         </td>
          </tr>
       </tbody>
    </table>

3.  The nosuid option is set for the disk. Check by executing the mount command:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>&gt; mount</p>
                <p>devpts on /dev/pts type devpts (rw,<strong>nosuid</strong>,gid=5,mode=620)</p>         </td>
          </tr>
       </tbody>
    </table>

    1.  If the nosuid flag displays, you cannot set the SetUID (set group id) bit on this disk. You can, though, copy the file to another disk and use the UCONF copilot.unix.cftsu.fname parameter to set the path to the new file (see the *Transfer CFT Installation Guide - Unix* for more information).
