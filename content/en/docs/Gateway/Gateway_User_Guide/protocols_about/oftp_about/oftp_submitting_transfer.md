{
    "title": "Submitting an OFTP Transfer Request",
    "linkTitle": "Submitting a Transfer Request",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[Overview](#overview)

[Transfer Request parameters for OFTP](#tr_paras)

[Submitting a Transfer Request without an Application](#submitting_tr_without_appli)

[Submitting a Transfer Request with an Application](#submitting_tr_with_appli)

<span id="overview"></span>

## Overview

You can submit Transfer Requests using:

-   The GUI
-   The <span class="code" style="font-weight: bold;">peltrans</span> online command
-   User programs using APIs

The examples provided in this topic use the <span class="code">[peltrans](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli#peltrans)</span> command.

<span id="tr_paras"></span>

## Transfer Request parameters for OFTP

### List of Transfer Request parameters

The following table describes parameters relevant to OFTP. For full details of Transfer Request parameters and their default values, refer to [Transfers: Parameters List](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list).

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter name (and abbreviation)</p>         </th>
<th class="HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comments</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span class="code">-org_alias (-oa)</span></p>         </td>
         <td><p> </p>         </td>
         <td><p>Initiator site ID (a Local Site)</p>         </td>
      </tr>
      <tr>
         <td><p>-dest_alias (-da)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Responder site ID (a Remote Site)</p>         </td>
      </tr>
      <tr>
         <td><p>-file_component (-fc)</p>         </td>
         <td><p> </p>         </td>
         <td><p>File to send</p>         </td>
      </tr>
      <tr>
         <td><p>-file_name (-fn)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Symbolic name for the sent file</p>         </td>
      </tr>
      <tr>
         <td><p>-appli (-ap)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Defines the file attributes for the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>-originator (-org)</p>         </td>
         <td><p> </p>         </td>
         <td><p>File originator OFTP ID</p>         </td>
      </tr>
      <tr>
         <td><p>-destination (-dest)</p>         </td>
         <td><p> </p>         </td>
         <td><p>File destination OFTP ID</p>         </td>
      </tr>
      <tr>
         <td><p>-mode (-m)</p>         </td>
         <td><p>I</p>         </td>
         <td><p>Transfer mode: <span style="font-weight: bold;">I</span>nitiator or <span style="font-weight: bold;">R</span>esponder</p>         </td>
      </tr>
      <tr>
         <td><p>-direction (-dir)</p>         </td>
         <td><p>O</p>         </td>
         <td><p>Transfer direction: O = out (Sender), I = in (Receiver)</p>         </td>
      </tr>
      <tr>
         <td><p>-compress (-comp)</p>         </td>
         <td><p>U</p>         </td>
         <td><p>Horizontal compression: values H, V and B have the same action</p>         </td>
      </tr>
      <tr>
         <td><p>-priority (-prio)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Transfer priority</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_fmt (-rf)</p>         </td>
         <td><p>F</p>         </td>
         <td><p>Record format: <span style="font-weight: bold;">F</span>ixed, <span style="font-weight: bold;">V</span>ariable or <span style="font-weight: bold;">S</span>tream</p>         </td>
      </tr>
      <tr>
         <td><p>-rec_len (-rl)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Record length: 0 – 32767</p>         </td>
      </tr>
      <tr>
         <td><p>-block_size (-bs)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>File block size (used by some operating systems)</p>         </td>
      </tr>
      <tr>
         <td><p>-data_code (-dc)</p>         </td>
         <td><p>U</p>         </td>
         <td><p>Data code of local file</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_fmt (-xrf)</p>         </td>
         <td><p>S</p>         </td>
         <td><p>Transfer record format</p>         </td>
      </tr>
      <tr>
         <td><p>-x_rec_len (-xrl)</p>         </td>
         <td><p>512</p>         </td>
         <td><p>Transfer record length</p>         </td>
      </tr>
      <tr>
         <td><p>-x_data_code (-xdc)</p>         </td>
         <td><p>B</p>         </td>
         <td><p>Transfer data code</p>         </td>
      </tr>
      <tr>
         <td><p>-padding (-pad)</p>         </td>
         <td><p>0</p>         </td>
         <td><p>Used for padding transfer records</p>         </td>
      </tr>
      <tr>
         <td><p>-type</p>         </td>
         <td><p>TRANS</p>         </td>
         <td><p>If specified: TRANS or EERP</p>         </td>
      </tr>
      <tr>
         <td><p>-purge_option (-po)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Purge file option for purge during transfer deletion</p>         </td>
      </tr>
      <tr>
         <td><p>-user_processed (-usr_proc)</p>         </td>
         <td><p>N</p>         </td>
         <td><p>User processed flag</p>         </td>
      </tr>
   </tbody>
</table>

 

The following parameters concern file security (OFTP R2.0 only):

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter names (and abbreviation)</p>         </th>
<th class="HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="HeadD-Column1-Header1"><p>Comments</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-sfidsign</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Is signed EERP required? { Y | N }</p>         </td>
      </tr>
      <tr>
         <td><p>-sfiddesc</p>         </td>
         <td><p> </p>         </td>
         <td><p>Virtual file description (free text)</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_format (-tradef)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Must be <span style="font-style: italic;">CMS</span> (Cryptographic Message Syntax)</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_org (-tradeo)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Original Trading Partner (sender)</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_dest (-traded)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Destination Trading Partner (receiver)</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign (-trades)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Is file signature required? { Y | N }</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_sign_algo (-tradesa)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Signing algorithm: SHA1withRSA</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_encrypt (-tradee)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Is file encryption required? { Y | N }</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_encryption_algo (-tradeea)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Encryption algorithm: { AES256 | 3DES }</p>         </td>
      </tr>
      <tr>
         <td><p>-trade_compress (-tradecomp)</p>         </td>
         <td><p> </p>         </td>
         <td><p>Is file compression required? { Y | N }</p>         </td>
      </tr>
   </tbody>
</table>

 

### Minimal set of Transfer Request parameters

The minimal set of parameters required for an OFTP Transfer Request is:

peltrans

           -org\_alias       &lt;request originator (sender)>

           -dest\_alias      &lt;request destination (receiver)>

           -file\_component  &lt;file to be sent>

           -appli           &lt;application name>

In this case, the file originator and destination coincide with the Site in communication.

 

If the file originator or final destination is different from the Site in communication, then you must specify them in the <span class="code">originator</span> and<span class="code"> destination</span> parameters.

peltrans

           -org\_alias       &lt;request originator>

           -dest\_alias      &lt;request destination>

           -file\_component  &lt;file to be sent>

           -appli           &lt;application name>

           -originator      &lt;file originator (sender)>

           -destination     &lt;file destination (receiver)>

### Transfer Request parameters when using file security services

If you use any of the file security services, the originator and destination must be predefined Trading Partners, with the appropriate security parameters.

peltrans

           -org\_alias       &lt;request originator (sender)>

           -dest\_alias      &lt;request destination (receiver)>

           -file\_component  &lt;file to be sent>

           -appli           &lt;application name>

           -trade\_org       &lt;file originator>

           -trade\_dest      &lt;file destination>

           -trade\_format    &lt;CMS>

           -trade\_sign      &lt; Y | N &gt;

           -trade\_encrypt   &lt; Y | N &gt;

           -trade\_compression &lt; Y | N &gt;

           -trade\_encryption\_algo &lt; AES256 | 3DES &gt;

           -signed\_eerp     &lt; Y | N &gt;

           -vfile\_desc      &lt;optional virtual file description>

Notes:

<span class="code">trade\_org</span>, <span class="code">trade\_dest</span> and <span class="code">trade\_format</span> are mandatory.

Cryptographic parameters (signature, encryption, compression) are optional. If not specified, their values are those defined in the corresponding Trading Partner.

<span id="submitting_tr_without_appli"></span>

## Submitting a Transfer Request without an Application

Gateway can process Transfer Requests submitted <span style="font-weight: bold;font-style: italic;">without</span> an Application. All file system attributes that are normally retrieved from Application objects must be supplied in the Transfer Request.

For this type of transfer, Gateway uses a default Application named PEL1.

<span style="font-weight: bold;">Note:</span> You can also supply file system attributes for Transfer Requests submitted <span style="font-style: italic;">with</span> an Application. In this case, Transfer Request parameters override the corresponding Application attributes.

#### Example

The following command submits a Transfer Request to send a file that contains 80-byte fixed-length records:

peltrans  \[-org\_alias  loc\_odette\]

           -dest\_alias  X25\_odette

           -file\_component  &lt;name of file to send>

           -f\_org  S

           -rec\_fmt  F

           -rec\_len  80

<span id="submitting_tr_with_appli"></span>

## Submitting a Transfer Request with an Application

Sites and Applications always belong to a group. For a Transfer to be valid, the Remote Site and Application must belong to the same group.

### Sending a file: Initiator mode

A Site represents the Initiator/Sender, while the partner is the Responder/Receiver. In Initiator mode, the partner automatically receives the file, without submitting any other request.

#### Example 1: Sending a file on a TCP/IP network

The following <span class="code" style="font-weight: bold;">peltrans</span> command transmits a file with variable-length records (maximum length: <span style="font-weight: bold;">255</span>).

The command requests ASCII to EBCDIC character set conversion.

In this example, the Application used is var255, and the Remote Site is TCP\_odette (as defined in [Configuring Gateway for OFTP](../oftp_config)). The Application var255 is specified in the <span class="code">file\_name</span> attribute.

peltrans  \[-org\_alias  loc\_odette\]

           -dest\_alias  TCP\_odette

           -appli  var255

           -file\_name  var255

           -file\_component  &lt;name of file to send>

### Sending a file : Responder mode

The Responder can submit a transfer in Responder/Sender mode. This operation registers the request in the Gateway Mailbox.

The Remote Site partner initiates the file transmission by submitting a Transfer Request in Initiator/Receiver mode.

#### Example

In the following example, the Site loc\_odette submits a Transfer Request in Responder/Sender mode, using an Application named fix255.

peltrans  \[-org\_alias  loc\_odette\]

           -dest\_alias  X25\_odette

           -appli  fix255

           -mode  R

          \[-direction  O\]

           -file\_component  &lt;name of file to send>

### Receiving a file: Initiator mode

A Site can submit a Transfer Request to receive a file from the partner Site. The Site receiving the file is the Initiator/Receiver, while the partner Site is the Responder.

As described in the <span style="font-style: italic;">Responder mode</span> section below, the Initiator receives the file if the Remote Site previously submitted a Transfer Request in Responder/Sender mode.

OFTP cannot select which file to receive. Therefore, you must connect to the server so that the protocol can process corresponding existing transfers as illustrated in the following example:

#### Example

peltrans  \[-org\_alias  loc\_odette\]

           -dest\_alias  X25\_odette

          \[-mode  I\]

           -dir  I

          \[-rc\_max  2\]

### Receiving a file: Responder mode

The Responder (Server) Site is the file receiver. This mode is used when the remote Initiator Site submits a Transfer Request to send a file. The Receiver automatically receives the file, without submitting any further request.

### Sending an end-to-end response (EERP/NERP)

To send an OFTP end-to-end-response (EERP/NERP) acknowledgment, you must specify the following parameters:

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p>Sending an EERP: Transfer Request parameters</p>         </td>
      </tr>
      <tr>
         <td><p>Parameter names</p>         </td>
         <td><p>Default</p>         </td>
         <td><p>Comments</p>         </td>
      </tr>
      <tr>
         <td><p>-type</p>         </td>
         <td><p>EERP</p>         </td>
         <td><p>Identify this as an acknowledgment request</p>         </td>
      </tr>
      <tr>
         <td><p>-reply_to_xfer</p>         </td>
         <td><p> </p>         </td>
         <td><p>ID of the transfer to acknowledge</p>         </td>
      </tr>
      <tr>
         <td><p>-nack</p>         </td>
         <td><p>N</p>         </td>
         <td><p>Is it a negative ACK? { Y | N }</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About OFTP](../)

[Configuring Gateway for OFTP](../oftp_config)

[Monitoring an OFTP transfer](../oftp_monitoring_transfer)

[OFTP trace example](../oftp_trace_example)

[Working with File Transfer Requests](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui))

[Working with Transfers (command line)](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli)

[Internal user exits](../../../customizing_gw_about/user_exits_about/user_exits_internal)

[Using PassPort PM with OFTP](../oftp_and_passport_pm)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
