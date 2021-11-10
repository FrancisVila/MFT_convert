{
    "title": "Submitting a PeSIT Hors SIT Transfer Request",
    "linkTitle": "Submitting a PeSIT Transfer Request",
    "weight": "230"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[About the PeSIT Hors SIT Transfer Request](#About_the_PeSIT_hors_SIT_Transfer_Request)

[Submitting a Transfer Request without an Application](#Submitting_a_Transfer_Request_without_an_Application)

[Submitting a Transfer Request with an Application](#Submitting_a_Transfer_Request_with_an_Application)

[Sending a message](#Sending_a_message)

[Sending an EERP acknowledgment](#Sending_an_EERP_acknowledgement)

[PeSIT HS E file reception requests](#PeSIT_HS_E_file_reception_requests)

<span id="About_the_PeSIT_hors_SIT_Transfer_Request"></span>

## About the PeSIT Hors SIT Transfer Request

Submit Transfer Requests using the<span class="code" style="font-weight: bold;"> peltrans</span> online command, the GUI, or user programs linked with APIs. Each of these interfaces transmits transfer parameters to Gateway.

The examples provided in this section were created with the<span class="code" style="font-weight: bold;"> peltrans</span> online command, which has the following syntax:

peltrans &lt;argument> value &lt;argument> value&lt;argument> value

Command arguments are keywords, each followed by the corresponding value. Keywords are prefixed by a "-" character, and most of them have abbreviated names (as shown in parentheses in the table below).

The following table lists Transfer Request parameters relevant to the PeSIT protocol. For details of all available parameters, refer to [Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli).

<span style="font-weight: bold;">Note:</span> Set the size of data buffers transmitted on the network (defined by the <span class="code" style="font-weight: bold;">data\_size\_max</span> parameter in the Remote Site) greater than the maximum record size (defined by the <span class="code" style="font-weight: bold;">rec\_len</span> and <span class="code" style="font-weight: bold;">x\_rec\_len</span> parameters in the Application).

<table>
         
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Transfer Request parameters Sending and Receiving files</p>         </td>
      </tr>
      <tr>
         <td><p>Keyword name(*)</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>Sending</p>
<p>Internal default</p>         </td>
         <td><p>Receiving</p>
<p>Application default</p>         </td>
         <td><p>Comments</p>         </td>
      </tr>
      <tr>
         <td><p>-org_alias (-oa)</p>         </td>
         <td><p>3<br />
(61) <sup>(1)</sup></p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Originator Site alias name, which must be a Remote Site defined with PeSIT protocol and the appropriate version</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>         </td>
         <td><p>4<br />
(62) <sup>(1)</sup></p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Destination Site alias name, which must be a Local Site name</p>         </td>
      </tr>
      <tr>
         <td><p>-file_type (-ft)</p>         </td>
         <td><p>11</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Mandatory</p>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>         </td>
         <td><p>12</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Mandatory</p>         </td>
      </tr>
      <tr>
         <td><p>-compress (-comp)</p>         </td>
         <td><p>21</p>         </td>
         <td><p>U</p>         </td>
         <td><p>U</p>         </td>
         <td><p>U = no compression</p>         </td>
      </tr>
      <tr>
         <td><p>-hist_create_date (-hd)</p>         </td>
         <td><p>51</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>PeSIT transfer creation date</p>         </td>
      </tr>
      <tr>
         <td><p>-prio</p>         </td>
         <td><p>17</p>         </td>
         <td><p>0</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer priority</p>         </td>
      </tr>
      <tr>
         <td><p>-f_org</p>         </td>
         <td><p>33</p>         </td>
         <td><p> </p>         </td>
         <td><p>S</p>         </td>
         <td><p>File organization</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_fmt (-rf)</p>         </td>
         <td><p>31</p>         </td>
         <td><p>S</p>         </td>
         <td><p>F</p>         </td>
         <td><p>Record format</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_len (-rl)</p>         </td>
         <td><p>32</p>         </td>
         <td><p>512</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Record length</p>         </td>
      </tr>
      <tr>
         <td><p>-key_offset</p>         </td>
         <td><p>39</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-key_len (-kl)</p>         </td>
         <td><p>38</p>         </td>
         <td><p>0</p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-data_code (-dc)</p>         </td>
         <td><p>16</p>         </td>
         <td><p>B</p>         </td>
         <td><p> </p>         </td>
         <td><p>B = binary</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_fmt (-xrf)</p>         </td>
         <td><p>31</p>         </td>
         <td><p>S</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer record format</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_len (-xrl)</p>         </td>
         <td><p>32</p>         </td>
         <td><p>512</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer record length</p>         </td>
      </tr>
      <tr>
         <td><p>-x_data_code (-xdc)</p>         </td>
         <td><p>16</p>         </td>
         <td><p>B</p>         </td>
         <td><p> </p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>-interval</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Interval between Remote Site polling (LOTS and POLL request types)</p>         </td>
      </tr>
      <tr>
         <td><p>-text_file</p>         </td>
         <td><p> </p>         </td>
         <td><p>N</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Y/N</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_user</p>         </td>
         <td><p>3</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: sender Id</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_appli</p>         </td>
         <td><p>3</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: sender application Id</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_text</p>         </td>
         <td><p>3</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: sender free text</p>         </td>
      </tr>
      <tr>
         <td><p>-rcv_user</p>         </td>
         <td><p>4</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: receiver Id</p>         </td>
      </tr>
      <tr>
         <td><p>-rcv_appli</p>         </td>
         <td><p>4</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: receiver application Id</p>         </td>
      </tr>
      <tr>
         <td><p>-rcv_text</p>         </td>
         <td><p>4</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Store-and-Forward only: receiver free text</p>         </td>
      </tr>
      <tr>
         <td><p>-maxi-files</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of files allowed</p>         </td>
      </tr>
      <tr>
         <td><p>-maxi-reqs</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>1</p>         </td>
         <td><p>Maximum number of requests allowed</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviations in parentheses

\(1\) PI value for Store-and-Forward mode

<span id="Submitting_a_Transfer_Request_without_an_Application"></span>

## Submitting a Transfer Request without an Application

For Gateway to process a Transfer Request submitted without using an Application, you must supply all the file system attributes that Gateway normally retrieves from the Application, in the Transfer Request itself.

For this type of transfer, Gateway uses a default Application named *DEFAULT*. An Application with this name must exist in both Sites.

<span style="font-weight: bold;">Note:</span> You can also supply file system attributes for Transfer Requests submitted *with* an Application. In this case, Transfer Request parameters override the corresponding Application attributes.

#### Example

The following command creates a Transfer Request to send a file containing 80-byte fixed-length records. Platform-dependent parameters (such as *sd* in this example) must be supplied if requested for a given platform.

**peltrans**  -org\_alias locpsit  -dest\_alias x25phsd

          -appli DEFAULT

          -file\_name DEFAULT  -file\_type 0

          -file\_component &lt;name\_of\_file\_to\_send>

          -f\_org S

          -rec\_fmt F  -rec\_len 80

          -x\_rec\_fmt F  -x\_rec\_len 80

          \[-sd &lt;system\_dependent\_param>\]

<span id="Submitting_a_Transfer_Request_with_an_Application"></span>

## Submitting a Transfer Request with an Application

In all modes, the Site and Application objects must belong to the same group. Refer to the table in the Overview section for parameter information.

### Sending a file: Initiator mode

In Initiator mode, one Site represents the Initiator/Sender, while the partner Site is Responder/Receiver.

The partner automatically receives the file, without submitting any further request.

#### Example: Sending a file using TCP/IP and PeSIT HS E

The following command sends a file with variable-length records. The maximum value length is 255.

The Transfer Request uses:

-   Application **var255**
-   Remote Site **tpelpc**

**peltrans**  -org\_alias localpsit

          -dest\_alias tcpphse

          -appli var255

          -file\_name var255

          -file\_component &lt;name\_of\_file\_to\_send>

          -snd\_msg send\_message\_text\_sample

### Sending a file: Responder mode

The Responder partner can submit a Transfer Request to send a file. Such requests are registered in the Mailbox and the Remote Site representing the partner initiates the actual file transmission, by submitting a Transfer Request in Initiator/Receiver mode.

#### Example

In the following example, the Local Site **locpsit** submits a Transfer Request in Responder/Sender mode, using the Application **fix255**.

**peltrans**  -org\_alias locpsit

          -dest\_alias x25phsd

          -appli fix255

          -file\_name fix255

          -direction O

          -mode R

          -file\_component &lt;name\_of\_file\_to\_send>\\

### Receiving a file: Responder mode

The Responder Site is the file receiver. This mode is used when the Remote Site submits a Transfer Request to send a file. The receiver side automatically receives the file, without submitting any further request.

### Receiving a file: Initiator mode

A file-reading feature allows a Site to submit a Transfer Request to receive a file made available by the partner Site. The Site receiving the file is Initiator/Receiver, while the partner Site is Responder/Sender.

The Initiator Site actually receives the file if the Remote Site has previously submitted a Transfer Request in Responder/Sender mode.

Both requests must use the same Application, the same file type and file name protocol parameters.

#### Example

In the following example, the Remote Site **x25phsd** submits a Transfer Request to receive the file made available by the Local Site **locpsit**.

**peltrans**  -org\_alias locpsit

          -dest\_alias x25phsd

          -direction I

          -mode I

          -appli fix255

          -file\_name fix255

<span style="font-weight: bold;">Note:</span> This type of Transfer Request can only transmit one file.

<span id="Sending_a_message"></span>

## Sending a message

PeSIT Hors SIT message transmission is only available in PeSIT Hors SIT E.

To send a PeSIT HORS SIT message, you must specify at least the following parameters:

-   Request type (must be MSG)
-   Initial message originator (origin alias)
-   Final message destination (destination alias)
-   Protocol file name
-   Message to send

You can supply the message content either in a message file or as an in-line message. If both are specified, the in-line message is used.

### Message Request parameters

The following table lists PeSIT HS relevant parameters for sending a message request using the <span class="code" style="font-weight: bold;">peltrans</span> command. Refer to [Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli) for information on all available parameters.

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Sending a message: Transfer Request parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Keyword names (*)</p>         </td>
         <td><p>Default</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>Comments</p>         </td>
      </tr>
      <tr>
         <td><p>-type</p>         </td>
         <td><p>MSG</p>         </td>
         <td><p> </p>         </td>
         <td><p>Identifies transfer as a message request</p>         </td>
      </tr>
      <tr>
         <td><p>-org_alias (-oa)</p>         </td>
         <td><p> </p>         </td>
         <td><p>3<br />
(61) <sup>(1)</sup></p>         </td>
         <td><p>Origin alias name</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>         </td>
         <td><p> </p>         </td>
         <td><p>4<br />
(62) <sup>(1)</sup></p>         </td>
         <td><p>Destination alias name</p>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>         </td>
         <td><p> </p>         </td>
         <td><p>12</p>         </td>
         <td><p>Protocol file name</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>         </td>
         <td><p> </p>         </td>
         <td><p>91</p>         </td>
         <td><p>User message</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_count_max (-rc_max)</p>         </td>
         <td><p>5</p>         </td>
         <td><p> </p>         </td>
         <td><p>Maximum number of retries allowed</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviations in parentheses

\(1\) PI value for Store-and-Forward mode

<span id="Sending_an_EERP_acknowledgement"></span>

## Sending an EERP acknowledgment

The EERP acknowledgment feature is only available in PeSIT Hors SIT E.

To send a PeSIT HORS SIT end-to-end-response (EERP) acknowledgment, you must specify at least the following parameters:

-   Request type (must be EERP)
-   Transfer ID to reply to
-   Message to send

You can supply the message content either in a message file or as an in-line message. If both are specified, the in-line message is used.

### acknowledgment Request parameters

The following table lists PeSIT HS relevant **<span class="code">peltrans</span>**parameters for an end-to-end-response acknowledgment message request.

For more information on the **<span class="code">peltrans</span>**command, refer to [Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli).

<table>
         
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>EERP acknowledgment message request parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Keyword names (*)</p>         </td>
         <td><p>Internal Default</p>         </td>
         <td><p>PI</p>         </td>
         <td><p>Comments</p>         </td>
      </tr>
      <tr>
         <td><p>-type</p>         </td>
         <td><p>EERP</p>         </td>
         <td><p> </p>         </td>
         <td><p>Identifies an acknowledgment request</p>         </td>
      </tr>
      <tr>
         <td><p>-reply_to_xfer</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>ID of the transfer to reply to</p>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>         </td>
         <td><p> </p>         </td>
         <td><p>91</p>         </td>
         <td><p>User message</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviations in parentheses

<span id="PeSIT_HS_E_file_reception_requests"></span>

## PeSIT HS E file reception requests

With PeSIT HS E, you can specify a SELECT request to receive a variable number of files made available on the server.

Apart from the parameters required for a normal PeSIT HS transfer, three parameters govern the selection request behavior:

-   Max\_file: the maximum number of files to receive. Accepted values are from 0 to 32000.
-   Max\_request: the maximum number of attempts that can be made. Accepted values are from 0 to 32000
-   Interval: the interval (in seconds) between two attempts

#### Use notes

-   To receive a variable (indeterminate) number of files, specify: <span class="code">  
    max\_file = 0, max\_request = n (with n > 0)</span>  
    to set an upper limit for the number of files to receive.
-   The selection request ends when no more files are available or when the maximum number (n) is reached.
-   To receive a fixed number of files, specify: <span class="code">  
    max\_file = m (with m > 0), max\_request=0, interval = s</span>
-   The selection request ends when <span style="font-style: italic;">m</span> files have been received. If less than <span style="font-style: italic;">m</span> files are made available at the moment of the request, successive attempts are made every <span style="font-style: italic;">s</span> seconds, as specified by the interval parameter.
-   If you specify <span class="code">max\_request = n</span> (with n > m), the selection request ends when all m files have been received or n attempts have been made.
-   For purposes of backward compatibility, if neither <span class="code">max\_file</span> nor <span class="code">max\_request</span> are specified, an attempt is issued to receive a single file.

## Case of a transfer to an existing file name

To view in detail the actions Gateway performs on a pre-existing file before receiving the transfer via PeSIT or OFTP of a file with the same name, read: <a href="../../oftp_about/transfer_to_existing_file_name" class="MCXref xref">Transfer to an existing file name</a>

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
