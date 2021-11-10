{
    "title": "Transfer command basics",
    "linkTitle": "Transfer concepts",
    "weight": "140"
}The transfer concept topics introduce the various <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> transfer
processes. For general transfer principles, refer to the introductory
overview section.

The transfer commands are
divided in categories depending on their function.

## Entering a command

There are multiple interfaces that you can use to enter Transfer CFT commands, such as the Transfer CFT command utility CFTUTIL or client user interface.

You can enter a command using CFTUTIL in a command window from the Transfer CFT runtime directory. For example in a Windows environment:



    C:\Axwaycft313sp1\Transfer_CFT\runtime> profile
    C:\Axwaycft313sp1\Transfer_CFT\runtime> CFTUTIL  
    1:[CFU] 

## Entering parameters

There are two ways to supply parameters for a command:

-   You can define all information for a command, both mandatory and optional parameters

<!-- -->

-   You can rely on default values or template values that are common for a given command

<span id="Transfer_associated_commands"></span>

## Using basic transfer associated commands

The commands associated with the transfers are listed in the table below.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Type</p>         </th>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfers </p>         </td>
         <td><p>SEND </p>         </td>
         <td>Send files, messages, or replies (acknowledgments)         </td>
      </tr>
      <tr>
         <td><p>RECV </p>         </td>
         <td><p>Receive files </p>         </td>
      </tr>
      <tr>
         <td><p>Actions on transfers </p>         </td>
         <td><p><a href="../../admin_intro/admin_commands_intro/delete_command">DELETE</a></p>         </td>
         <td><p>Delete catalog entries </p>         </td>
      </tr>
      <tr>
         <td><p><a href="">HALT</a></p>         </td>
         <td><p>Stop transfers </p>         </td>
      </tr>
      <tr>
         <td><p><a href="">KEEP</a></p>         </td>
         <td><p>Suspend transfers </p>         </td>
      </tr>
      <tr>
         <td><p><a href="">START</a></p>         </td>
         <td><p>Restart transfers </p>         </td>
      </tr>
      <tr>
         <td><p><a href="">SUBMIT</a></p>         </td>
         <td><p>Submit an end-of-transfer procedure</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">END</a></p>         </td>
         <td><p>Declare that flow is finished</p>         </td>
      </tr>
   </tbody>
</table>

For each command, the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> command interface performs the following
actions:

-   Checks the syntax
    of the command
-   Puts the command
    in the Transfer CFT communication medium
