{
    "title": "Managing transfers and partners",
    "linkTitle": "Managing transfers and partners",
    "weight": "110"
}## Transfer concepts

This section describes transfers, and how to create and
manage your transfer operations using <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> can execute both file and message transfers. A transfer
consists of a set of processes that result in the exchange of files between
computers. In a transfer, one computer is the sender, the other is the
receiver. The sender and receiver are linked together by a network. A
file transfer may consist of sending a file, group of files, or a message.

## Transfer objects

Transfer CFT requires a certain number parameters, such as the protocol, to successfully perform transfers with partners.

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> provides
a set of *objects* that allow you to define these transfer related parameters. Prerequisites to make file transfers between two Transfer CFTs include:

-   A common network, such as TCP
-   A common protocol, such as PeSIT ANY
-   A basic partner object on each Transfer CFT (declare each partner)

However, your out-of-the-box Transfer CFT can perform a basic loop transfer without any additional configuration. Additionally, the Transfer CFT installation provides samples that you can use as a templates to get started. For more information on samples and performing a verification transfer, refer to the Post installation section in your OS specific *Transfer CFT Installation Guide*.

## Transfer types

In Transfer
CFT there are 3 types of transfers:

-   Files
-   Replies (acknowledgments)
-   Messages

See also, [Transfer command basics.](transfer_command_overview)

## Transfer commands

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses two commands for transfer requests:

-   SEND: sends a file or message to a partner
-   RECV: requests the reception of files from a partner

Additionally, there are basic [transfer control commands](../c_intro_userinterfaces/web_copilot_ui/operations/managing_transfer_states) that you can use to manage a transfer.

<table>
   <th>
      <tr>
<th>Command         </th>
<th>Action         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../admin_intro/admin_commands_intro/delete_command">DELETE</a></p>         </td>
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

<span id="Transfer_owners"></span>

## Identifiers

### Model files: IDF

Depending on the type of data to be sent, a model file identifier is assigned to each transfer, for example
IDF = INVOICES. Processing operations and default values for transfer
parameters and data file description parameters can be associated with
a model file identifier.

These processing operations and default values are indicated in the flow definition
(CFTSEND and CFTRECV parameter setting commands), for sending and receiving
files respectively.

A CFTSEND or CFTRECV command corresponds to a model
file. In the absence of these commands for a given transfer, <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses the default CFTSEND and CFTRECV command parameters, which are
valid regardless of the IDF.

When using <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> with <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>, an identifier corresponds to each flow definition. In the absence of this flow identifier, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> uses the flow default value.

The default command is the command whose file identifier corresponds either to the:

-   CFTPART
    IDF = parameter
-   Or, if the above
    parameter is not included, to the CFTPARM DEFAULT
    = parameter

<span id="Messages__IDM"></span>

### Messages: IDM

A message is a character string specified by a SEND command and sent
by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> as a specific transfer. A message transfer does not make reference to a flow definition (a CFTSEND or CFTRECV command).

 

![](/Images/TransferCFT/temp_type_data.png)

## Transfer records

All transfer requests, either SEND or RECV, are recorded and saved in
the Transfer CFT catalog file.

A catalog record, known as a catalog
entry, includes information such as the:

-   Transfer direction:
    Send or Receive
-   Type of object
    transferred: File, Message, or Reply
-   Partner name
-   Transfer identifier
-   Transfer status
-   Troubleshooting diagnostics

For more information, see the [list catalog contents](../c_intro_userinterfaces/about_cftutil/monitoring_cftutil_intro/listcat_command) topic.

### Example command to send a file

In this example the partner is PARIS, and the file to send is called REPORT1.

![](/Images/TransferCFT/temp_request.png)

### Transfer identifiers

<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> enables the transferring sequential files, or files seen
as such. These files can be accessed through one of the operating system
access methods . See [File locations: Model and physical files](creating_transfers_start_here/model_and_physical_file_concepts).

When a transfer occurs, it is labeled with an identifier. There are
two additional types of identifiers, besides the IDM and IDF, that can correspond with a transfer:

-   Transfer
    identifier
-   Catalog
    identifier

<span id="Transfer_identifier__IDT"></span>

#### Transfer identifier: IDT

The transfer identifier is a label associated with each transfer, that is, time stamping. However, the IDT synchronization with the current date and time is lost as soon as Transfer CFT manages more than 6 transfers per minute. This means that Transfer CFTs can have IDTs that differ by up to several months as compared with the current date.

<span id="Catalog_identifier__IDTU"></span>

#### Catalog identifier: IDTU

The catalog identifier, IDTU
is a transfer unique local representation. It corresponds to a transfer
counter systematically implemented by Transfer CFT.

A transfer can always be uniquely identified locally, regardless of
the situation - simultaneous transfers, resumption after incidents, and
so on. When there are several <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s on the same computer, uniqueness
is guaranteed between two <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s sharing the same catalog.