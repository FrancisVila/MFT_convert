{
    "title": "Submitting a PEL Transfer Request",
    "linkTitle": "Submitting a PEL transfer request",
    "weight": "230"
}{{< Gateway/componentlongname  >}}: Protocols

[About PEL Transfer Requests](#About_PEL_Transfer_Requests)

[File submission process](#File_submission_process)

[Submitting a Transfer Request without an Application](#Submitting_a_Transfer_Request_without_an_Application)

[Submitting a Transfer Request with an Application](#Submitting_a_Transfer_Request_with_an_Application)

[Reply Codes](#reply_codes)

[Protocol trace messages](#Protocol_trace_messages)

<span id="About_PEL_Transfer_Requests"></span>

## About PEL Transfer Requests

Submit Transfer Requests using the GUI, the` peltrans` online command, or user programs linked with APIs. Each of these interfaces transmits transfer parameters to Gateway.

The examples provided in this section use the `peltrans` online command, which has the following syntax:

**peltrans** &lt;argument> value &lt;argument> value &lt;argument> value

 

<table>
         
         
         
         
         
   
   <thead>
      <tr>
<th colspan="4" class="HeadD-Column1-Header1"><p>Transfer Request parameters</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Keyword names (*)</p>         </td>
         <td><p>Appli default</p>         </td>
         <td><p>Internal default</p>         </td>
         <td><p>Comments</p>         </td>
      </tr>
      <tr>
         <td><p>-originator</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Responder Site name (used for type = LOTS transfers only)</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>         </td>
         <td><p>I</p>         </td>
         <td><p>I</p>         </td>
         <td><p>Transfer mode: Initiator or Responder</p>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>         </td>
         <td><p>O</p>         </td>
         <td><p>O</p>         </td>
         <td><p>Transfer direction: O = out (Sender), I = in (Receiver)</p>
<p>Sending or receiving a file</p>         </td>
      </tr>
      <tr>
         <td><p>-compress (-comp)</p>         </td>
         <td><p>U</p>         </td>
         <td><p>U</p>         </td>
         <td><p>U = no compression</p>         </td>
      </tr>
      <tr>
         <td><p>-prio</p>         </td>
         <td><p>1</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer priority</p>         </td>
      </tr>
      <tr>
         <td><p>-f_org</p>         </td>
         <td><p>S</p>         </td>
         <td><p> </p>         </td>
         <td><p>File organization</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_fmt (-rf)</p>         </td>
         <td><p>F</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Record format</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_len (-rl)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>512</p>         </td>
         <td><p>Record length</p>         </td>
      </tr>
      <tr>
         <td><p>-data_code (-dc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>B</p>         </td>
         <td><p>B = binary</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_fmt (-xrf)</p>         </td>
         <td><p> </p>         </td>
         <td><p>S</p>         </td>
         <td><p>Transfer record format</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_len (-xrl)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>512</p>         </td>
         <td><p>Transfer record length</p>         </td>
      </tr>
      <tr>
         <td><p>-x_data_code (-xdc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>B</p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>-padding</p>         </td>
         <td><p> </p>         </td>
         <td><p>0</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-type</p>         </td>
         <td><p>TRANS</p>         </td>
         <td><p>TRANS</p>         </td>
         <td><p>Type of processing</p>         </td>
      </tr>
      <tr>
         <td><p>-interval</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Interval between Remote Site polling (LOTS and POLL request types)</p>         </td>
      </tr>
      <tr>
         <td><p>-text_file</p>         </td>
         <td><p>N</p>         </td>
         <td><p>N</p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>-snd_msg (-sm)</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>Transmitted unchanged: can be a Gateway Application</p>         </td>
      </tr>
      <tr>
         <td><p>-sd</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td><p>System-dependent parameter</p>         </td>
      </tr>
      <tr>
         <td><p>-retry_count_max (-rc_max)</p>         </td>
         <td><p>10</p>         </td>
         <td><p>5</p>         </td>
         <td><p>Max retries before canceling transfer</p>         </td>
      </tr>
      <tr>
         <td><p>-purge_option (-po)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Purge file option for purge during transfer deletion</p>         </td>
      </tr>
      <tr>
         <td><p>-user_processed (-usr_proc)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>N</p>         </td>
         <td><p>User processed flag</p>         </td>
      </tr>
   </tbody>
</table>

(\*) Abbreviated keyword names in parentheses.

<span id="File_submission_process"></span>

## File submission process

### Description

Gateway records Transfer Requests in the Mailbox, provided that they contain the minimum set of consistent parameters required for Gateway processing (including transfer monitoring, scheduling parameters, and file system attributes).

Typically, the Transfer Request contains only a subset of parameters. To record Transfer Requests in the Mailbox, Gateway completes the remaining transfer parameters from:

-   User interface default values
-   Corresponding values in the Application object and/or Site objects, if supplied
-   Internal default values, if some parameters are still missing or are unresolved (such as transfer direction, which is set to *Both* in the default Application)

Gateway always verifies the consistency of Transfer Requests before it records them in the Mailbox. If Gateway cannot find a mandatory transfer parameter in the Transfer Request, the Application, or in the internal default values (such as the file receiver Site), it rejects the Transfer Request and does not add the record to the Mailbox.

### Error reporting

When Gateway encounters a problem during the Transfer Request processing, it returns an error. The error format depends on the user interface used:

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Interface</p>         </th>
<th class="HeadD-Column1-Header1"><p>Error Format</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Online commands</p>         </td>
         <td><p>Error message is displayed directly on output</p>         </td>
      </tr>
      <tr>
         <td><p>GUI</p>         </td>
      </tr>
      <tr>
         <td><p>API calls</p>         </td>
         <td><p>Return value is 1</p>
<p>An error code is automatically loaded into the global variable <strong>ErrCod</strong>. This code can be used to retrieve the error message using a special API function: <span style="font-weight: bold;"><a href="../../../customizing_gw_about/c_api_about/c_api_primitives#GikErrMsg">GikErrMsg</a></span>.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Submitting_a_Transfer_Request_without_an_Application"></span>

## Submitting a Transfer Request without an Application

For Gateway to process a Transfer Request submitted without using an Application, you must supply all the file system attributes that Gateway normally retrieves from the Application, in the Transfer Request itself.

<span style="font-weight: bold;">Note:</span> You can also supply file system attributes for Transfer Requests that you submit <span style="font-style: italic;">with</span> an Application. In this case, Transfer Request parameters override the corresponding Application attributes.

#### Example

The following command creates a Transfer Request to send a file containing 80-byte fixed-length records. Platform-dependent parameters (such as<span class="code"> sd</span> in this example) must be supplied if requested for a given platform.

peltrans  -org\_alias locpel  -dest\_alias xpel

   -appli PEL1

   -file\_component &lt;name\_of\_file\_to\_send>

   -f\_org S

   -rec\_fmt F  -rec\_len 80

   -x\_rec\_fmt F  -x\_rec\_len 80

   \[-sd &lt;system\_dependent\_param>\]

<span id="Submitting_a_Transfer_Request_with_an_Application"></span>

## Submitting a Transfer Request with an Application

In all modes, the Site and Application objects must belong to the same group. Refer to the table in [About PEL Transfer Requests](#About_PEL_Transfer_Requests) for parameter information.

### Sending a file in Initiator mode

In Initiator mode, one Site represents the Initiator/Sender, while the partner Site is the Responder/Receiver.

The partner automatically receives the file, without submitting any further request.

#### Example: Sending a file using a TCP/IP network

The following command sends a file with variable-length records (maximum length: 255) and requests ASCII to EBCDIC code conversion.

The Transfer Request uses:

-   Application: <span style="font-weight: bold;">var255</span>
-   Remote Site: <span style="font-weight: bold;">tpelpc</span>

peltrans  \[-org\_alias  locpel\]   -dest\_alias  tpelpc

   -appli  var255

   -file\_component  &lt;name\_of\_file\_to\_send>

   -snd\_msg  tutu

### Sending a File in Responder mode

The server partner can submit a Transfer Request in Responder/Sender mode. This operation simply registers the Request in the Gateway Mailbox.

The Remote Site initiates the actual file transmission by submitting a Transfer Request in Initiator/Receiver mode.

#### Example

In the following example, the Local Site <span style="font-weight: bold;">locpel</span> submits a Transfer Request in Responder/Sender mode, using an Application named <span style="font-weight: bold;">fb80</span>.

peltrans  \[-org\_alias locpel\]

   -dest\_alias xpelpc

   -appli fb80

   -direction O  -mode R

   -file\_component &lt;name\_of\_the\_file\_to\_send>

### Receiving a file in Initiator mode (PEL LOTS request)

An Initiator Site can submit a Transfer Request to receive a file from the partner Site.

The Site receiving the file is Initiator/Receiver, while the partner Site is Responder/Sender.

A Transfer Request in Initiator/Receiver mode is called a LOTS request in PEL terminology. Such a Request is created with its own local identifier, which is just a registration number, and does not correspond to any file data transmission.

However, end-of-transfer exits are scheduled for this type of Transfer Request, just as for Requests associated with actual file transfers.

You can receive up to ten files with the same LOTS Request, depending on the number of Transfer Requests in the Remote Site that meet the LOTS criteria. The Remote Site reply contains the list of Requests selected according to LOTS command criteria. Gateway automatically creates as many file Transfer Requests as the number received in the response to the LOTS command.

The Initiator Site receives the file if the Remote Site previously submitted a Transfer Request in Responder/Sender mode, on condition that:

-   Both Transfer Requests use the same Application
-   The Remote Site and the Application belong to the same group

#### Example

In the following example, the Remote Site <span style="font-weight: bold;">xpelpc</span> is the Initiator/Receiver. This Site submits a Transfer Request to receive files from the Local Site <span style="font-weight: bold;">locpel</span>.

peltrans  -org\_alias locpel  -dest\_alias xpelpc

   -originator locpel

   -appli fb80

   -type LOTS

   -direction I  -mode I

The Responder (<span style="font-weight: bold;">locpel</span>) selects the files to transmit based on the transfer attributes supplied in this LOTS Transfer Request.

Gateway returns a Transfer Request identifier for the received Request (LOTS command), and creates a separate Transfer Request for each file transfer that the LOTS command generates.

<span id="reply_codes"></span>

## Reply Codes

#### Errors associated with \*NON response message

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>*NON Error number</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>001</p>         </td>
         <td><p>Responder out of sync</p>         </td>
      </tr>
      <tr>
         <td><p>002</p>         </td>
         <td><p>Command does not begin with the character ?</p>         </td>
      </tr>
      <tr>
         <td><p>003</p>         </td>
         <td><p>Incorrect syntax</p>         </td>
      </tr>
      <tr>
         <td><p>004</p>         </td>
         <td><p>Confidentiality breached in transmission</p>         </td>
      </tr>
      <tr>
         <td><p>005</p>         </td>
         <td><p>Confidentiality breached in reception</p>         </td>
      </tr>
      <tr>
         <td><p>006</p>         </td>
         <td><p>File not found on disk</p>         </td>
      </tr>
      <tr>
         <td><p>007</p>         </td>
         <td><p>Responder error</p>         </td>
      </tr>
      <tr>
         <td><p>008</p>         </td>
         <td><p>Responder name error name invalid</p>         </td>
      </tr>
      <tr>
         <td><p>009</p>         </td>
         <td><p>Application name invalid</p>         </td>
      </tr>
      <tr>
         <td><p>00A</p>         </td>
         <td><p>File reference error</p>         </td>
      </tr>
      <tr>
         <td><p>00B</p>         </td>
         <td><p>File not allocated</p>         </td>
      </tr>
      <tr>
         <td><p>00C</p>         </td>
         <td><p>No entry in the MAILBOX</p>         </td>
      </tr>
      <tr>
         <td><p>00D</p>         </td>
         <td><p>Incorrect file state</p>         </td>
      </tr>
      <tr>
         <td><p>00E</p>         </td>
         <td><p>The transfer cannot be restarted</p>         </td>
      </tr>
      <tr>
         <td><p>00F</p>         </td>
         <td><p>Number of records at zero in TRANS commands</p>         </td>
      </tr>
      <tr>
         <td><p>00G</p>         </td>
         <td><p>Compression not supported</p>         </td>
      </tr>
   </tbody>
</table>

#### Errors associated with \*NDL response message

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>*NDL Message number</p>         </th>
<th class="HeadD-Column1-Header1"><p>Meaning</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>001</p>         </td>
         <td><p>*DDL not valid</p>         </td>
      </tr>
      <tr>
         <td><p>002</p>         </td>
         <td><p>Invalid number of blocks for acknowledgment</p>         </td>
      </tr>
      <tr>
         <td><p>003</p>         </td>
         <td><p>Invalid result</p>         </td>
      </tr>
      <tr>
         <td><p>004</p>         </td>
         <td><p>The transfer can not be restarted</p>         </td>
      </tr>
      <tr>
         <td><p>999</p>         </td>
         <td><p>ABORT</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Protocol_trace_messages"></span>

## Protocol trace messages

Each protocol command or response corresponds to a protocol trace message that you can record in the log file. The protocol trace is an optional feature that you define for transfer activity for a given Site.

You can enable or disable trace printing for a Site object at either of the following stages by setting the Remote Site parameter<span class="code"> -trace\_mode (-tm)</span> to <span style="font-style: italic;">Y</span> (yes) or <span style="font-style: italic;">N</span> (no):

-   During Site creation
-   On modifying attributes of an existing Site
-   During Gateway processing (dynamically)

Enabling or disabling protocol tracing using this method is only valid for the current session. The update is lost when you stop Gateway.

 

Related topics

[About PEL](../)

[Configuring Gateway for PEL](../pel_config)

[Working with File Transfer Requests](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
