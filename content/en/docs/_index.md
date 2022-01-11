{
    "title": "Manage  transfers",
    "linkTitle": "Managing Transfer states",
    "weight": "20"
}This section describes transfers, and how to create and
manage your transfer operations using {{< TransferCFTtest/componentshortname  >}}.  

'\[ PHASE = string \]

\[ PHASESTEP = string \]

WWWWWWWWWw[Restart transfers]()WWWWWWWWWWWWWWW
            &lt;/p>

\[ [SCOPE]() = string \]

<span id="SUBMIT"></span>

#### SUBMIT: Submit end-of-transfer procedure

Syntax
'


{{< TransferCFTtest/componentshortname  >}} can execute both file and message transfers. A transfer
consists of a set of processes that result in the exchange of files between
computers. In a transfer, one computer is the sender, the other is the
receiver. The sender and receiver are linked together by a network. A
file transfer may consist of sending a file, group of files, or a message.

## Managing transfers in the user interface

To view the transfers log:

1.  In the left pane, click **Transfer**.
2.  In the main pane, select a transfer.
3.  Click the transfer action.  
    <img src="/Images/TransferCFTtest/ui_transfers.png" class="maxWidth" />

Available actions to include in the Transfers page include:

```

UI

Parameter details

Description

New
<a href="concepts" class="MCXref xref">Managing transfers and partners</a>
Create a new transfer request
Clone
No equivalent parameter
Copy an existing transfer request
Restart
Restarting
transfers
Restart transfers in the H or K state in the catalog
Delete
Deleting
catalog entries
Delete one or more catalog entries
 
Suspending
transfers
Suspend one or all of the send and/or receive transfers
with selected partners
 
Submitting
an end-of-tranfser
Submit an end-of-transfer procedure for each selected
transfer
Halt
Halting
a transfer
Suspend one or all the send and/or receive transfers,
with the partners selected
End
Declaring
executed transfers
Declare that all the operations related to the end-of-transfer,
send and receive, have been executed correctly
 
Retrieving
a blocked request
Retrieves, in server mode, a blocked send request that
has the *hold* status, if the diagnostic codes are not null
 
Suspending
a catalog request
Suspend a transfer in the catalog
 
Deleting
a transfer request
Delete a transfer request from the communication file
Ack
Use the SEND acknowledgement commands  
Send a transfer acknowledgement
Nack
Sending a negative acknowledgement
Send a notification indicating an error occurred
```

## Create  transfer requests filters

To create a new transfer request filter or modify an existing filter:

1.  Click an exiting filter to use as the basis for the filter or click the filter icon ![](/Images/TransferCFTtest/filter_create.png) .
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

-   Click the settings icon ![](/Images/TransferCFTtest/settings_icon.png)to open the column options. You can use the filter field to help you find fields more quickly.
-   Add or remove the filters you want to display in your page layout.
-   Click **Save as** and name the layout.

> **Note**
>
> These page customizations are defined in the CFTUIPREF object.  

## Troubleshooting transfer filters

**Issue**: I cannot create filters

**Solution**: Check that you have the MANAGE CFTUIPREF or VIEW CFTUIPREF privilege. This issue may have occurred due to an upgrade.
