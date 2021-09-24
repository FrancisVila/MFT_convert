{
    "title": "PKI and PassPort PS",
    "linkTitle": "PKI and PassPort PS",
    "weight": "320"
}# UCONF: PKI and PassPort PS options

This topic presents the parameters to set to define Transfer CFT to PassPort PS server connectivity.  You can define this connectivity in Transfer CFT using
a command line window.

PassPort PS parameters

To enable Transfer CFT to PassPort PS server connectivity, use the UCONFSET
command to set the following parameters:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTUTIL 
 UCONFSET ID= pki.type, value=”passport”</p>
            <p>CFTUTIL 
 UCONFSET ID= pki.passport.hostname, value=”xxxx”</p>
            <p>CFTUTL 
 UCONFSET ID= pki.passport.port, value=”xxxx”</p>
         </td>
      </tr>
   </tbody>
</table>

Refer to the [UCONF parameters](../uconf_directory) table for information on the pki.passport type parameters.
