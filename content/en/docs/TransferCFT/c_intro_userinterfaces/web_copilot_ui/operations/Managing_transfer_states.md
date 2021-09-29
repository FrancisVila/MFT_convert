{
    "title": "Transfers",
    "linkTitle": "Transfers",
    "weight": "170"
}# <span id="kanchor55"></span><span id="Managing_transfer_states__Start_here"></span>Manage transfers

This section describes transfers, and how to create and
manage your transfer operations using Transfer CFT.

Transfer CFT can execute both file and message transfers. A transfer
consists of a set of processes that result in the exchange of files between
computers. In a transfer, one computer is the sender, the other is the
receiver. The sender and receiver are linked together by a network. A
file transfer may consist of sending a file, group of files, or a message.

## Managing transfers in the user interface

To view the transfers log:

1.  In the left pane, click **Transfer**.
2.  In the main pane, select a transfer.
3.  Click the transfer action.  
    ![](settings_icon.png)

Available actions to include in the Transfers page include:

<table data-border="1" data-cellspacing="0" width="90%" data-wrapperparagraphselector="P">
<thead>
<tr class="header">
<th>UI</th>
<th>Parameter details</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>New</td>
<td><a href="../../../../concepts">Managing transfers and partners</a></td>
<td>Create a new transfer request</td>
</tr>
<tr class="even">
<td>Clone</td>
<td>No equivalent parameter</td>
<td>Copy an existing transfer request</td>
</tr>
<tr class="odd">
<td>Restart</td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/start_command">Restarting
transfers</a></p></td>
<td data-valign="top" width="75%"><p>Restart transfers in the H or K state in the catalog</p></td>
</tr>
<tr class="even">
<td>Delete</td>
<td data-valign="top" width="25%"><p><a href="../../../../admin_intro/admin_commands_intro/delete_command">Deleting
catalog entries</a></p></td>
<td data-valign="top" width="75%"><p>Delete one or more catalog entries</p></td>
</tr>
<tr class="odd">
<td> </td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/keep_command">Suspending
transfers</a></p></td>
<td data-valign="top" width="75%"><p>Suspend one or all of the send and/or receive transfers
with selected partners</p></td>
</tr>
<tr class="even">
<td> </td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/submit_command">Submitting
an end-of-tranfser</a></p></td>
<td data-valign="top" width="75%"><p>Submit an end-of-transfer procedure for each selected
transfer</p></td>
</tr>
<tr class="odd">
<td>Halt</td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/halt_command">Halting
a transfer</a></p></td>
<td data-valign="top" width="75%"><p>Suspend one or all the send and/or receive transfers,
with the partners selected</p></td>
</tr>
<tr class="even">
<td>End</td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/end_command">Declaring
executed transfers</a></p></td>
<td data-valign="top" width="75%"><p>Declare that all the operations related to the end-of-transfer,
send and receive, have been executed correctly</p></td>
</tr>
<tr class="odd">
<td> </td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/resume_command">Retrieving
a blocked request</a></p></td>
<td data-valign="top" width="75%"><p>Retrieves, in server mode, a blocked send request that
has the <em>hold</em> status, if the diagnostic codes are not null</p></td>
</tr>
<tr class="even">
<td> </td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/kstate_command">Suspending
a catalog request</a></p></td>
<td data-valign="top" width="75%"><p>Suspend a transfer in the catalog</p></td>
</tr>
<tr class="odd">
<td> </td>
<td data-valign="top" width="25%"><p><a href="../../../about_cftutil/managing_transfer_states/clearcmd_command">Deleting
a transfer request</a></p></td>
<td data-valign="top" width="75%"><p>Delete a transfer request from the communication file</p></td>
</tr>
<tr class="even">
<td>Ack</td>
<td data-valign="top" width="25%"><a href="../../../../concepts/using_the_send_command/sending_replies">Use the SEND acknowledgement commands</a></td>
<td data-valign="top" width="75%">Send a transfer acknowledgement</td>
</tr>
<tr class="odd">
<td>Nack</td>
<td data-valign="top" width="25%"><a href="../../../../concepts/using_the_send_command/transfers_neg_ack_pesit">Sending a negative acknowledgement</a></td>
<td data-valign="top" width="75%">Send a notification indicating an error occurred</td>
</tr>
</tbody>
</table>

## Create transfer requests filters

To create a new transfer request filter or modify an existing filter:

1.  Click an exiting filter to use as the basis for the filter or click the filter icon ![](settings_icon.png) .
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

-   Click the settings icon ![](settings_icon.png)to open the column options. You can use the filter field to help you find fields more quickly.
-   Add or remove the filters you want to display in your page layout.
-   Click **Save as** and name the layout.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">These page customizations are defined in the CFTUIPREF object.</td>
</tr>
</tbody>
</table>

## Troubleshooting transfer filters

Issue: I cannot create filters

Solution: Check that you have the MANAGE CFTUIPREF or VIEW CFTUIPREF privilege. This issue may have occurred due to an upgrade.
