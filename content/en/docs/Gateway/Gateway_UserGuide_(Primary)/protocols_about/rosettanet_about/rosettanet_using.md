{
    "title": "Using RosettaNet",
    "linkTitle": "Using RosettaNet",
    "weight": "260"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Protocols

[Overview](#intro)

[Defining a RosettaNet outgoing request](#Defining_a_RosettaNet_Outgoing_Request)

[Defining a RosettaNet Response, Exception Signal or acknowledgment](#Defining_a_RosettaNet_Response_or_Exception_Signal)

<span id="intro"></span>

## Overview

This topic describes the Gateway parameters required for transfers using the RosettaNet protocol.

### Prerequisites

Before you can use RosettaNet on Gateway, you must first:

-   Configure Gateway for use with RosettaNet
-   Confirm your network connection
-   Create the necessary objects

For more information, refer to [Configuring the RosettaNet environment](../rosettanet_config).

After completing these preliminary steps, you are ready to:

-   Submit a Transfer Request to send a file to a business partner via RosettaNet
-   Receive RosettaNet messages from remote business partners

### RosettaNet monitoring

Each RosettaNet message (request, receipt acknowledgment, signal, and response) has a transfer record in Gateway. These messages are displayed in the Gateway log.

<span id="Defining_a_RosettaNet_Outgoing_Request"></span>

## Defining a RosettaNet outgoing request

To submit an outgoing RosettaNet request, define the parameters listed in the table below. Parameters that have no value and description listed, have the same values and definitions as in other Gateway parameter lists.

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Parameter</p>         </th>
<th class="HeadD-Column1-Header1"><p>Value and definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><strong>Trading Partner Info:</strong></p>         </td>
      </tr>
      <tr>
         <td><p>TYPE</p>
<p>(<span style="font-style: italic;">Mandatory</span>)</p>         </td>
         <td><p>TYPE_TRANS</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_FORMAT</p>         </td>
         <td><p>TRADE_FORMAT_RN</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_ORG</p>         </td>
         <td><p>TRADE_ORG and TRADE_ORG_ALIAS are mutually exclusive.</p>
<p>If TRADE_ORG is specified, TRADE_FORMAT must also be defined.</p>
<p>Only one of these can be specified. If both are specified, they are taken into account in the listed order.</p>
<p>If none of these is defined, the default associated local partner defined in the destination partner is used.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_ORG_ALIAS</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_DEST</p>
<p>(<span style="font-style: italic;">Mandatory</span>)</p>         </td>
         <td><p>TRADE_DEST, TRADE_DEST_ALIAS and EXT_DEA_ID are mutually exclusive.</p>
<p>If TRADE_DEST is specified, TRADE_FORMAT must also be present. Only one of these can be specified. If more than one is specified, they are taken into account in the listed order.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_DEST_ALIAS</p>
<p>(<span style="font-style: italic;">Mandatory</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>EXT_DEA_ID</p>
<p>(<span style="font-style: italic;">Mandatory</span>)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>RosettaNet Message Info:</strong></p>         </td>
      </tr>
      <tr>
         <td><p>FILE_COMPONENT</p>
<p>(<span style="font-style: italic;">Mandatory</span>)</p>         </td>
         <td><p>FILE_COMPONENT is a MIME file containing the complete RosettaNet message.</p>
<p>It contains up to five top level elements corresponding to the RosettaNet:</p>
<ul>
<li>preamble header</li>
<li>delivery header (if RNIF V2.0)</li>
<li>service header</li>
<li>service content</li>
<li>attachments (if any)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>TRADE_SIGN</p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>YES</strong></li>
<li><strong>NO</strong></li>
</ul>
<p>If TRADE_SIGN is required and TRADE_SIGN_ALGO is not specified, the default value defined in destination trading partner is used.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_SIGN_ALGO</p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>MD5_RSA</strong></li>
<li><strong>SHA1_RSA</strong></li>
</ul>
<p>If TRADE_SIGN is required and TRADE_SIGN_ALGO is not specified, the default value defined in destination trading partner is used.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_ENCRYPT</p>
<p><em>(Applicable only for RN V2.0)</em></p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>YES</strong></li>
<li><strong>NO</strong></li>
</ul>
<p>If TRADE_ENCRYPT is required and TRADE_ENCRYPT_ALGO is not specified, the default value defined in destination trading partner is used.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_ENCRYPT_ALGO</p>
<p><em>(Applicable only for RN V2.0)</em></p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>AES128</strong></li>
<li><strong>AES256</strong></li>
<li><strong>DES</strong></li>
<li><strong>3DES</strong></li>
<li><strong>RC2_40</strong></li>
<li><strong>RC4</strong></li>
</ul>
<p>If TRADE_ENCRYPT is required and TRADE_ENCRYPT_ALGO is not specified, the default value defined in destination trading partner is used.</p>
<p><strong>Note:</strong> Gateway supports RC4 with 128-bit key size. Gateway does not support RC4 with 40-bit or 64-bit key sizes.</p>         </td>
      </tr>
      <tr>
         <td><p>TRADE_ENCRYPT_PARTS</p>
<p><em>(Applicable only for RN V2.0)</em></p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>RN_PAYLOAD</strong></li>
<li><strong>RN_PAYLOAD_CONTAINER</strong></li>
</ul>
<p>TRADE_ENCRYPT_PART indicates whether the whole payload container (service header plus service content) or only payload (service content) is to be encrypted.</p>         </td>
      </tr>
      <tr>
         <td><p>RECEIPT_REQUEST_SYNC</p>         </td>
         <td><p>Select from:</p>
<ul>
<li><strong>YES</strong></li>
<li><strong>NO</strong></li>
</ul>
<p>RECEIPT_REQUEST_SYNC indicates whether it is a synchronous request.</p>         </td>
      </tr>
      <tr>
         <td><p>RSEND_COUNT_MAX</p>         </td>
         <td><p>10 retry attempts</p>         </td>
      </tr>
      <tr>
         <td><p>RESEND_DELAY</p>         </td>
         <td><p>300 (seconds)</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Transport Info:</strong></p>         </td>
      </tr>
      <tr>
         <td><p>REMOTE_AGENT</p>         </td>
         <td><p>If REMOTE_AGENT is not specified, the one specified in the destination trading partner is used.</p>         </td>
      </tr>
      <tr>
         <td><p>MAIL_SUBJECT</p>
<p>(if transport is SMTP)</p>         </td>
         <td><p>Select from:</p>
<ul>
<li><span style="font-weight: bold;">FROM</span>: if transport is SMTP</li>
<li><span style="font-weight: bold;">TO</span>: if transport is SMTP</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><strong>Schedule Info:</strong></p>         </td>
      </tr>
      <tr>
         <td><p>DATE_TO_BEGIN</p>         </td>
         <td><p>The Schedule Information fields use the same values as for typical transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>DATE_TO_END</p>         </td>
      </tr>
      <tr>
         <td><p>PRIORITY</p>         </td>
      </tr>
      <tr>
         <td><p>RETRY_COUNT_MAX</p>         </td>
      </tr>
      <tr>
         <td><p>FROZEN_STATE</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Application Info:</strong></p>         </td>
      </tr>
      <tr>
         <td><p>MODEL</p>         </td>
         <td><p>The Application Information fields use the same values as for typical transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>PURGE_OPTION</p>         </td>
      </tr>
      <tr>
         <td><p>PARAM1</p>         </td>
      </tr>
      <tr>
         <td><p>PARAM2</p>         </td>
      </tr>
      <tr>
         <td><p>SENTINEL_TRANSFER_FILTER</p>         </td>
      </tr>
      <tr>
         <td><p>EX_SENTINEL_IDENT</p>         </td>
      </tr>
      <tr>
         <td><p>EX_SENTINEL_OBJECTNAME</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_a_RosettaNet_Response_or_Exception_Signal"></span>

## Defining a RosettaNet Response, Exception Signal or acknowledgment

To submit an outgoing RosettaNet response, exception signal, or acknowledgment, use the same values as for Defining a RosettaNet outgoing request.

------------------------------------------------------------------------

Related topics

[About RosettaNet](../)

[Configuring the RosettaNet environment](../rosettanet_config)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
