{
    "title": "Use the SEND acknowledgement commands  ",
    "linkTitle": "Sending a REPLY",
    "weight": "230"
}## <span id="About_the_SEND_REPLY_Command"></span>

## Sending an acknowledgement

This topic describes the SEND REPLY command, which sends a positive acknowledgement.

The SEND TYPE = REPLY command
initiates the sending of a reply type message
to a previous transfer from the partner that the message was
intended for. The partner monitor interprets this message as a transfer
acknowledgement.

The REPLY sender must define the IDT parameter corresponding
to the identifier of the transfer to be acknowledged. This facility may
be used, for example, after processing a file received, or a message, in order to inform the sender that
all the operations related to this receive transfer have been correctly
accomplished.

The protocol used to acknowledge a transfer must be the same as the
one used for the transfer. A transfer acknowledgement is a protocol concept.

## Sending a negative acknowledgement

This topic describes the SEND NACK command, which sends a negative acknowledgement.

Via negative acknowledgments, the
final partner signals to the initial sender of the file that application
errors were detected.

If the initial sender does not support this function, as for example in earlier versions of Transfer CFT, the final partner does not transmit the
negative acknowledgement and the Transfer CFT log file displays:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>CFTT93W PART=XFB1 IDS=00008 Negative ack not supported by server         </td>
      </tr>
   </tbody>
</table>

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>cftutil send<br />
type=nack,<br />
part=&amp;part,<br />
idm=nack,<br />
msg=recu,<br />
idt=&amp;idt</p>         </td>
      </tr>
   </tbody>
</table>

<table data-cellspacing="0" width="90%">
   <thead>
      <tr class="header">
         <th>Description</th>
<th colspan="2">Use this command to initiates the sending of a message
of a particular type. This message is a reply to a previous transfer from
the partner.</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="top">
         <td rowspan="8" width="19.982%">            <p>Parameters</p>         </td>
         <td colspan="2">            <p>FOR OPTIONAL
PARAMETERS COMMON TO SEND: see the <a href="../../c_intro_userinterfaces/command_summary">SEND</a>
command.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/exec.htm">EXEC</a></p>         </td>
         <td width="59.777%">            <p>Filename.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/ida.htm">IDA</a> </p>         </td>
         <td width="59.777%">            <p>Local transfer identifier assigned by the user or user
application. The maximum length is 64 characters.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/idm.htm">IDM</a> </p>         </td>
         <td width="59.777%">            <p>Message identifier. The value of this identifier is unrestricted.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/idu.htm">IDT</a> </p>         </td>
         <td width="59.777%">            <p>Identifier of the original transfer acknowledged by this
message.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/msg.htm">MSG</a></p>         </td>
         <td width="59.777%">            <p>Message</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td>            <p><strong><a href="../../CFTUTIL/Parameter_index/part.htm">PART</a> </strong></p>         </td>
         <td width="59.777%">            <p>Transfer partner identifier.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td>            <p><a href="../../CFTUTIL/Parameter_index/pri.htm">PRI</a></p>         </td>
         <td width="59.777%">            <p>Request selection priority.</p>         </td>
      </tr>
      <tr class="odd" data-valign="top">
         <td width="19.982%">            <p> </p>         </td>
         <td>            <p><strong><a href="../../CFTUTIL/Parameter_index/type.htm">TYPE</a> =
REPLY</strong></p>         </td>
         <td width="59.777%">            <p>Characterizes a reply send transfer.</p>         </td>
      </tr>
      <tr class="even" data-valign="top">
         <td colspan="3" width="100%">         </td>
      </tr>
   </tbody>
</table>
