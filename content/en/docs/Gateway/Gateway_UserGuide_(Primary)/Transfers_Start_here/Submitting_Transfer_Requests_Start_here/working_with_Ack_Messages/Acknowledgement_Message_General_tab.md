{
    "title": "New Acknowledgment Message: General tab",
    "linkTitle": "General tab",
    "weight": "160"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer ID to ack</p>         </td>
         <td><p>Enter the identifier of the Transfer that is being acknowledged.</p>         </td>
      </tr>
      <tr>
         <td><p>Ack type</p>         </td>
         <td><p>Select one of the following acknowledgement options:</p>
<ul>
<li><span style="font-weight: bold;">EERP</span></li>
<li><span style="font-weight: bold;">RECEIPT</span> for EDIINT Trading Partner and SWIFTNet exchanges</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Negative acknowledgement</p>         </td>
         <td><p>Select this option if you want to receive a negative acknowledgement from the Remote Site in the event of transfer failure.</p>
<p>This option is valid only if the Remote Site negative acknowledgement is activated for the Remote Site.</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message in file</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message in file</p>         </td>
         <td><p>If the message to send is stored in an external file, select this option. Then complete the following fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Message file path</p>         </td>
         <td><p>Enter the complete file and path of the external file that contains the message to send.</p>         </td>
      </tr>
      <tr>
         <td><p>Application</p>         </td>
         <td><p>Select an Application from the drop-down list.</p>
<p>Alternatively, enter the Application name manually.<br />
Maximum: 25 alphanumeric characters.</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message</p>         </td>
      </tr>
      <tr>
         <td><p>Send text message</p>         </td>
         <td><p>If the message to send is not contained in an external file, select this option. Then complete the following fields.</p>         </td>
      </tr>
      <tr>
         <td><p>Message text</p>         </td>
         <td><p>Enter the text of the message to send directly in the text field.</p>         </td>
      </tr>
      <tr>
         <td><p>Message data code</p>         </td>
         <td><p>Select the data code for the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Transfer data code</p>         </td>
         <td><p>Select the data code for the transferred message.</p>         </td>
      </tr>
      <tr>
         <td><p>SMTP/POP3 only</p>         </td>
      </tr>
      <tr>
         <td><p>SMTP Site</p>         </td>
         <td><p>Select an SMTP Site.</p>         </td>
      </tr>
      <tr>
         <td><p>From</p>         </td>
         <td><p>Enter the SMTP <span style="font-weight: bold;">From</span> address.<br />
Maximum: 128 alphanumeric characters.</p>
<p>If you do not specify an originating address in this field, Gateway uses the default email address that you specify in the Local Site associated with the Remote Site.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with Acknowledgement Messages](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
