{
    "title": "spasswd",
    "linkTitle": "spasswd",
    "weight": "3280"
}### spasswd

#### CFTSEND/CFTRECV

\[ SPASSWD = *string* , \_AUTH\_\]

Password for the user who is sending the file. You can provide the SPASSWD directly or through an external file, and uses the following format:

part1 user1 passwd1

part2 user2 passwd2

\* user1 passwd3

\* \* passwd4

Or you can use \_AUTH\_ to indicate authentication method as defined in the uconf cft.server.authentication\_method parameter.

Example

/home/&USERID/cft\_passw

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If you begin a password with an indirection character (Unix @, Windows #), it is  considered a reference to a file and not part of the password.         </td>
      </tr>
</table>

[Return to Command index](../../)

 
