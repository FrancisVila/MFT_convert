{
    "title": "SWIFTNet OverdueTime",
    "linkTitle": "SWIFTNet OverdueTime",
    "weight": "310"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

[Overview](#overview)

[Sending OverdueTime](#sending)

[Receiving an Overdue file or message](#receiving)

[Verifying the OverdueTime in the transfer properties](#verifying)

<span id="overview"></span>

## Overview

SWIFTNet OverdueTime allows the sender of a SWIFT transfer to specify the latest date/time when the receiver should receive the file or message. After this time, a message or file is considered as being overdue.

The receiver will receive the file or message even after the overdue time. The receiver will be warned about this, but no further action is performed. The sender will also receive a message saying that the transfer is overdue.

### Time zone

The overdue time must be entered as local time (the seconds are truncated to '00') and will appear as such in Gateway's interface. However, it is converted to UTC when sending to SWIFT.

<span id="sending"></span>

## Sending OverdueTime

When you send a file or message you can specify the OverdueTime in the Transfer Request or in the Transfer Model.

### Specifying OverdueTime in the Transfer Request

#### Using the peltrans command

peltrans \[-sw\_overdue\_time (-swot)\]

Specify the overdue time using the <span class="code">-sw\_overdue\_time (-swot)</span> parameter.

Enter the date and time in the format <span style="font-style: italic;">YYYYMMDD HHMMSS</span>. Note however that the seconds are truncated to '00' when sending.

#### Using the Gateway GUI

On the Transfer Request **SWIFTNet** tab, **SnF** sub-tab, check and complete the **Date** and **Time** fields as follows:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SnF sub-tab <span style="font-weight: normal;">[for Store and forward Delivery mode]</span></p>         </td>
      </tr>
      <tr>
         <td><p><span style="font-weight: bold;">Overdue time</span></p>         </td>
      </tr>
      <tr>
         <td><p>Date</p>         </td>
         <td><p>To set a date value for the OverdueTime, check this option and select the required date using the drop-down calendar.</p>
<p>When the option is unchecked, no OverdueTime will be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Time</p>         </td>
         <td><p>To set a time value for the OverdueTime, check this option and set the required hours and minutes (the seconds are truncated to '00' when sending).</p>
<p>When the option is unchecked, but <strong>Date</strong> is checked, the OverdueTime sent is the date with time '00:00:00'.</p>
<p>When both <strong>Time</strong> and <strong>Date</strong> are unchecked, no OverdueTime will be sent.</p>
<p><strong>Note:</strong> If you use the <strong>Time</strong> option, you must also set the <strong>Date</strong> option.</p>         </td>
      </tr>
   </tbody>
</table>

### Specifying OverdueTime in the Transfer Model

You can also specify the SWIFTNet overdue time in the Transfer Model.

<span id="receiving"></span>

## Receiving an Overdue file or message

Even if the overdue date has passed, the transfer is accepted. A log entry will appear, indicating the transfer was overdue.

### Example:

SNET080W 10.05.2011 15:43:31 SAGLIVEGTW(rnd9\_mp) \[93\] Transfer is overdue; due date: 2011-05-10 15:40:00.

<span id="verifying"></span>

## Verifying the OverdueTime in the transfer properties

### Sender

For the sender, the presence of an OverdueTime means the transfer should be received before the indicated date. The overdue time is set by the sender himself.

When the due time arrives, SWIFT automatically creates a system message for the sender and stores it in the notification queue to inform him about the partner not receiving the file before the specified time. The system message is present in the Mailbox and linked to the original transfer by the <span class="code">receipt\_reply\_to</span> field (in the system message).

To receive overdue warning system messages, you need a Trading Partner that allows the reception of these system message types. For information about the default Trading Partner used to receive system messages, refer to [SYSTEM\_MESSAGES remote Trading Partner](../../swiftnet_connector/swiftnet_configuring#sys_messages_tp). For information about request type values associated with different system message types, refer to the SWIFTNet documentation.

### Receiver

For the receiver, the presence of an OverdueTime means the transfer was overdue when receiving.

### Displaying transfer details

Use the <span class="codeBold_in_para">peldsp display\_trans</span> command to display the details of a transfer.

In the details, Gateway displays the OverdueTime (if present).

Alternatively you can view the transfer details, including the OverdueTime (if present), in the **SWIFTNet** / **SnF** tab of the View transfer dialog.

Related topics

[Working with <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet](../../swiftnet_connector/swiftnet_working_with)

[Model objects: Parameters List](../../../../transfers_start_here/parameters_start_here/models_start_here/model_object_parameter_list)

[SWIFTNet (SNET) log messages](../../../../log_messages_about/swiftnet_messages_(snet))

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
