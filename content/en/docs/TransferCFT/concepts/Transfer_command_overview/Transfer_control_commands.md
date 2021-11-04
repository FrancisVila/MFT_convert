{
    "title": "Transfer control commands",
    "linkTitle": "Transfer control commands",
    "weight": "170"
}This topic describes the transfer control commands and provides a link
to more information on these commands. The transfer control commands can
be used to:

-   Interrupt a transfer
    in process
-   Activate or reactivate
    a suspended or held transfer
-   Delete a transfer
    request
-   Submit, or resubmit,
    an end-of-transfer procedure where the transfer in the T state
-   Declare that the
    processing following a transfer is completed

The following table describes the commands associated with these actions.

<table>
   <th>
      <tr>
<th>Command         </th>
<th>Action         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../admin_intro/admin_commands_intro/delete_command">DELETE</a></p>         </td>
         <td><p>Deletes a catalog entry </p>         </td>
      </tr>
      <tr>
         <td><p><a href="#">HALT</a></p>         </td>
         <td><p>Stops a transfer and sets it to the HOLD state </p>         </td>
      </tr>
      <tr>
         <td><p><a href="#">KEEP</a></p>         </td>
         <td><p>Stops a transfer and sets it to the KEEP state </p>         </td>
      </tr>
      <tr>
         <td><p><a href="#">START</a></p>         </td>
         <td><p>Reactivates a transfer </p>         </td>
      </tr>
      <tr>
         <td><p><a href="#">SUBMIT</a></p>         </td>
         <td>Runs a preprocessing, a post-processing or an acknowledgment processing procedure according to the current phase of the transfer request.         </td>
      </tr>
      <tr>
         <td><p><a href="#">END</a></p>         </td>
         <td><p>Declares the processing subsequent to the transfer terminated </p>         </td>
      </tr>
      <tr>
         <td><p><a href="#">RESUME</a></p>         </td>
         <td><p>Retrieves, in the server mode, a blocked send request having
the hold status</p>         </td>
      </tr>
   </tbody>
</table>

The parameters relative to these commands determine the transfer selection
criteria, catalog entries, these commands relate to.

The transfer control commands modify the state of the transfers in the
Transfer CFT catalog. This state can be queried by the [LISTCAT](../../../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command) command,
both before and after the control command is executed. The meaning of
these states is indicated in the next topic, Transfer
states.
