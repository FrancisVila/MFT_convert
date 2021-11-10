{
    "title": "Manage  transfers",
    "linkTitle": "Transfers",
    "weight": "170"
}This section describes transfers, and how to create and
manage your transfer operations using <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can execute both file and message transfers. A transfer
consists of a set of processes that result in the exchange of files between
computers. In a transfer, one computer is the sender, the other is the
receiver. The sender and receiver are linked together by a network. A
file transfer may consist of sending a file, group of files, or a message.

## Managing transfers in the user interface

To view the transfers log:

1.  In the left pane, click **Transfer**.
2.  In the main pane, select a transfer.
3.  Click the transfer action.  
    <img src="/Images/TransferCFT/ui_transfers.png" class="maxWidth" />

Available actions to include in the Transfers page include:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">UI         </th>
<th class="HeadE-Column1-Header1">Parameter details         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>New         </td>
         <td><a href="../../../../concepts" class="MCXref xref">Managing transfers and partners</a>         </td>
         <td>Create a new transfer request         </td>
      </tr>
      <tr>
         <td>Clone         </td>
         <td>No equivalent parameter         </td>
         <td>Copy an existing transfer request         </td>
      </tr>
      <tr>
         <td>Restart         </td>
         <td><p><a href="">Restarting
transfers</a></p>         </td>
         <td><p>Restart transfers in the H or K state in the catalog</p>         </td>
      </tr>
      <tr>
         <td>Delete         </td>
         <td><p><a href="../../../../admin_intro/admin_commands_intro/delete_command">Deleting
catalog entries</a></p>         </td>
         <td><p>Delete one or more catalog entries</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><a href="">Suspending
transfers</a></p>         </td>
         <td><p>Suspend one or all of the send and/or receive transfers
with selected partners</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><a href="">Submitting
an end-of-tranfser</a></p>         </td>
         <td><p>Submit an end-of-transfer procedure for each selected
transfer</p>         </td>
      </tr>
      <tr>
         <td>Halt         </td>
         <td><p><a href="">Halting
a transfer</a></p>         </td>
         <td><p>Suspend one or all the send and/or receive transfers,
with the partners selected</p>         </td>
      </tr>
      <tr>
         <td>End         </td>
         <td><p><a href="">Declaring
executed transfers</a></p>         </td>
         <td><p>Declare that all the operations related to the end-of-transfer,
send and receive, have been executed correctly</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><a href="">Retrieving
a blocked request</a></p>         </td>
         <td><p>Retrieves, in server mode, a blocked send request that
has the <em>hold</em> status, if the diagnostic codes are not null</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><a href="../../../../troubleshoot_intro/admin_troubleshooting_server/admin_troubleshooting_runtime/kstate_command">Suspending
a catalog request</a></p>         </td>
         <td><p>Suspend a transfer in the catalog</p>         </td>
      </tr>
      <tr>
         <td>          </td>
         <td><p><a href="../../../../troubleshoot_intro/admin_troubleshooting_server/admin_troubleshooting_runtime/clearcmd_command">Deleting
a transfer request</a></p>         </td>
         <td><p>Delete a transfer request from the communication file</p>         </td>
      </tr>
      <tr>
         <td>Ack         </td>
         <td><a href="../../../../concepts/using_the_send_command/sending_replies" class="MCXref xref">Use the SEND acknowledgement commands</a>         </td>
         <td>Send a transfer acknowledgement         </td>
      </tr>
      <tr>
         <td>Nack         </td>
         <td><a href="../../../../concepts/using_the_send_command/transfers_neg_ack_pesit" class="MCXref xref">Sending a negative acknowledgement</a>         </td>
         <td>Send a notification indicating an error occurred         </td>
      </tr>
   </tbody>
</table>

## Create transfer requests filters

To create a new transfer request filter or modify an existing filter:

1.  Click an exiting filter to use as the basis for the filter or click the filter icon ![](/Images/TransferCFT/filter_create.png) .
2.  Customize the filter.
3.  Click **Save** if you are modifying and existing filter or **Save as...** if this is a new filter.

## Display transfer request details

To display transfer request details:

-   Click any line to expand details that include the severity, timing, code, and message.
-   Click the IDTU to display the request details.

For details on the transfer states in Transfer CFT,
refer to Transfer states
topic.

## Create or modify the page layout

Optionally you can select a **Layout** in the drop-down menu to use a customized column or filter display. To create a new layout:

-   Click the settings icon ![](/Images/TransferCFT/settings_icon.png)to open the column options. You can use the filter field to help you find fields more quickly.
-   Add or remove the filters you want to display in your page layout.
-   Click **Save as** and name the layout.

> **Note:**
>
> These page customizations are defined in the CFTUIPREF object.

## Troubleshooting transfer filters

<span class="bold_in_para">Issue</span>: I cannot create filters

<span class="bold_in_para">Solution</span>: Check that you have the MANAGE CFTUIPREF or VIEW CFTUIPREF privilege. This issue may have occurred due to an upgrade.
