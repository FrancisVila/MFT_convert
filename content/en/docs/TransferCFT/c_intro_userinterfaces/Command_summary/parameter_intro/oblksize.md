{
    "title": "oblksize",
    "linkTitle": "oblksize",
    "weight": "2400"
}### <span id="oblksize"></span>oblksize

#### COPYFILE

\[OBLKSIZE = {IBLKSIZE value | n }\]

Output file block size, in bytes. The value indicated must be greater
than the value of the OLRECL parameter.  
The following table indicates for each system if the parameter
must be defined.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
      <tr>
         <td bgcolor="#C0C0C0" valign="top" width="19%">
            <p><b>OS</b>
</p>
         </td>
         <td bgcolor="#C0C0C0" valign="top" width="81%">
            <p><b>OBLKSIZE</b> </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>z/OS (MVS)</p>
         </td>
         <td valign="top" width="81%">
<p align="center">YES </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>OS400 </p>
         </td>
         <td valign="top" width="81%">
<p align="center">NO </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>UNIX </p>
         </td>
         <td valign="top" width="81%">
<p align="center">NO </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>VMS </p>
         </td>
         <td valign="top" width="81%">
<p align="center">NO </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p>Windows </p>
         </td>
         <td valign="top" width="81%">
<p align="center">NO</p>
         </td>
      </tr>
</table>

[Return to Command index](../../)
