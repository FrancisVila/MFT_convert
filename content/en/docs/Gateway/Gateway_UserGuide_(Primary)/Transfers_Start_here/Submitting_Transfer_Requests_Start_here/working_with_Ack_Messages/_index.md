{
    "title": "Acknowledgment messages",
    "linkTitle": "Acknowledgement Messages",
    "weight": "140"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

## Working with acknowledgment Messages

### Submitting acknowledgment Message Requests

To create and transfer an acknowledgment Message:

1.  In the left pane of the GUI main window, click <img src="/Images/Gateway/expand_marker.gif" width="16" height="16" /> to expand the <span style="font-weight: bold;">Transfer Management</span> node.
2.  Right-click <span style="font-weight: bold;">Transfers</span>, and then select <span style="font-weight: bold;">New > acknowledgment Message</span> from the context menu.  
    Gateway opens the <span style="font-style: italic;">New acknowledgment message</span> window.
3.  Complete the tabs of this window:
    -   <span style="font-weight: bold;">[General](acknowledgement_message_general_tab)</span> tab
    -   <span style="font-weight: bold;">[Options](../working_with_appli_messages/application_message_options_tab)</span> tab  
        Use this tab to specify a date and time, or a range of dates and times, when the message can be sent. If you leave all of these fields empty, Gateway sends the message immediately.
4.  After completing the tabs, click <span style="font-weight: bold;">OK</span> to validate and initiate the transfer.  
    If the parameters are correct, Gateway processes the transfer and deposits a transfer record to the Mailbox.

Related topics

[Working with Transfers (command line)](../working_with_transfers_cli)

[Transfers: Parameters List](../working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)