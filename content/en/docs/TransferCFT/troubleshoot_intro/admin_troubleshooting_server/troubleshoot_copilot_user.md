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

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>/home/cft/company/Transfer_CFT/home/bin/<b>cftsu must be launch as setuid root!</b>         </td>
      </tr>
   </tbody>
</table>

1.  The owner is not root. Check:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>ls -l cftsu-rwsrwxrwx 1 cft cft  cftsu          </td>
      </tr>
   </tbody>
</table>

    Fix: Set the root using the chown root:root &lt;file> command.

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>ls -l cftsu-rwsrwxrwx 1 <span>root root</span> cftsu         </td>
      </tr>
   </tbody>
</table>

2.  The setuid option (s) is not set for the cftsu file. Check:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>ls -l cftsu-rwxrwxrwx 1 root root  cftsu</p>
         </td>
      </tr>
   </tbody>
</table>

    Fix: Set using the chmod u+s &lt;file> command.

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>ls -l cftsu</p>
            <p>-rw<u>s</u>rwxrwx 1 root root cftsu</p>
         </td>
      </tr>
   </tbody>
</table>

3.  The nosuid option is set for the disk. Check by executing the mount command:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>&gt; mount </p>
            <p>devpts on /dev/pts type devpts (rw,<b>nosuid</b>,gid=5,mode=620) </p>
         </td>
      </tr>
   </tbody>
</table>

    1.  If the nosuid flag displays, you cannot set the SetUID (set group id) bit on this disk. You can, though, copy the file to another disk and use the UCONF copilot.unix.cftsu.fname parameter to set the path to the new file (see the *Transfer CFT Installation Guide - Unix* for more information).
