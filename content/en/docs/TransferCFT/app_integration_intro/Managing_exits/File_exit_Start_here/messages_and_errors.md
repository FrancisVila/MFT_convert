{
    "title": "Messages  and errors",
    "linkTitle": "Messages and errors",
    "weight": "350"
}When serious faults arise, such as parameter setting errors, overwriting
data, time-outs, and so on, {{< TransferCFT/componentshortname  >}} and the communication
interface generate messages, which are sent to the standard output for your use. For a list of the possible
errors that may occur with a File exit, see [Messages
and error codes](../../../../troubleshoot_intro/messages_and_error_codes_start_here).

You can also generate your own messages and error messages via the fields
indicated in the table below.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>ret2</p>         </td>
         <td><p>Error message (up to eight characters)<br />
To be defined in case of transfer refusal (ret1 = 9)<br />
This message appears in the {{< TransferCFT/componentshortname  >}} catalog in the DIAGP (protocol
diagnosis) field </p>         </td>
      </tr>
      <tr>
         <td><p>msg </p>         </td>
         <td><p>Error message (up to 512 characters)<br />
The user function can define this field at each stage<br />
This message is redirected to the standard output </p>         </td>
      </tr>
   </tbody>
</table>
