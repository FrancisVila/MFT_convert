{
    "title": "Transfer concepts",
    "linkTitle": "Transfer concepts",
    "weight": "170"
}The transfer concept topics introduce the various Transfer CFT transfer
processes. For general transfer principles, refer to the introductory
overview section.

The transfer commands are
divided in categories depending on their function.

## Entering a command

There are multiple interfaces that you can use to enter Transfer CFT commands, such as the Transfer CFT command utility CFTUTIL or client user interface.

You can enter a command using CFTUTIL in a command window from the Transfer CFT runtime directory. For example in a Windows environment:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>C:\Axwaycft313sp1\Transfer_CFT\runtime&gt; profile</p>
            <p>C:\Axwaycft313sp1\Transfer_CFT\runtime&gt; CFTUTIL  </p>
            <p>1:[CFU] </p>
         </td>
      </tr>
   </tbody>
</table>

## Entering parameters

There are two ways to supply parameters for a command:

-   You can define all information for a command, both mandatory and optional parameters

<!-- -->

-   You can rely on default values or template values that are common for a given command

## <span id="Transfer_associated_commands"></span>Using basic transfer associated commands

The commands associated with the transfers are listed in the table below.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Type</p>
</th>
         <th>
            <p>Command</p>
</th>
         <th>
            <p>Description </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="2" valign="top" width="25%">
            <p>Transfers </p>
         </td>
         <td valign="top" width="19%">
            <p><a href="submitting_transfers_start_here.htm">SEND</a> </p>
         </td>
         <td valign="top" width="56%">Send files, messages, or replies (acknowledgments)         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="submitting_transfers_start_here.htm">RECV</a> </p>
         </td>
         <td valign="top" width="56%">
            <p>Receive files </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="6" valign="top" width="25%">
            <p>Actions on transfers </p>
         </td>
         <td valign="top" width="19%">
            <p><a href="../../../admin_intro/admin_commands_intro/delete_command">DELETE</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Delete catalog entries </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/halt_command">HALT</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Stop transfers </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/keep_command">KEEP</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Suspend transfers </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/start_command">START</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Restart transfers </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/submit_command">SUBMIT</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Submit an end-of-transfer procedure </p>
         </td>
      </tr>
      <tr>
         <td valign="top" width="19%">
            <p><a href="../../../c_intro_userinterfaces/about_cftutil/managing_transfer_states/end_command">END</a>
</p>
         </td>
         <td valign="top" width="56%">
            <p>Declare that flow is finished</p>
         </td>
      </tr>
   </tbody>
</table>

For each command, the Transfer CFT command interface performs the following
actions:

-   Checks the syntax
    of the command
-   Puts the command
    in the Transfer CFT communication medium
