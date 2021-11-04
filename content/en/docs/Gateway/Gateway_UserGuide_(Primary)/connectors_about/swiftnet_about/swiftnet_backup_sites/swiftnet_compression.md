{
    "title": "Using pre/post transfer compression for SWIFTNet",
    "linkTitle": "Using pre/post transfer compression",
    "weight": "270"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

The Gateway SWIFTNet connector supports compression for outgoing transfers and decompression for incoming transfers.

You can compress files or messages before sending them for reasons of efficiency, or compatibility with your SWIFTNet partner. The files or messages then need to be decompressed using the same algorithm at the receiving end.

## Compression

By default, Gateway uses ZIP compression when sending a file or message. Alternatively, you can choose to compress with GZIP or ZLIB. [Manual compression](#manual_compression) (using algorithms other than ZIP, GZIP or ZLIB) is also possible.

## Decompression

When receiving a file, Gateway supports ZIP, ZLIB and GZIP. If a received file is compressed using one of these compression algorithms, the received information can be decompressed. For other algorithms, [manual decompression](#manual_compression) is possible.

## Requesting compression

You can request compression for a transfer in two different ways:

-   In the <span style="font-weight: bold;">Trading Partner</span> object, using the <span style="font-weight: bold;">[Compress](../../swiftnet_connector/swiftnet_configuring#Compress)</span> parameter  
    (or <span class="code">[compress](../../swiftnet_connector/swiftnet_configuring#_compress)</span> if you use online commands)
-   In the <span style="font-weight: bold;">Transfer Request</span> object, when submitting the transfer, using the <span style="font-weight: bold;">[Compress](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_swiftnet_tab#compress)</span> parameter  
    (or <span class="code">[trade\_compress](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list#_trade_compress)</span> if you use online commands)

## File naming on Gateway

After compression or decompression, Gateway creates a new file in the directory where the files are stored. The new file has the following format:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>After...</p>         </th>
<th class="HeadD-Column1-Header1"><p>New file name</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Compression</p>         </td>
         <td><p><span class="code">transfer_id.cmp</span><br />
(for example, <span class="code">F0000006.cmp</span>)</p>         </td>
      </tr>
      <tr>
         <td><p>Decompression</p>         </td>
         <td><p><span class="code">transfer_id.dcm</span><br />
(for example, <span class="code">F0000006.dcm</span>)</p>         </td>
      </tr>
   </tbody>
</table>

By default, the files are stored in the directory<span class="code"> &lt;Gateway installation directory>/run\_time/tmp</span>. You can change the default directory for incoming files in the Remote Site.

<span id="compress_FileAct"></span>

## FileAct transfers

If a transfer is made <span style="font-style: italic;">without</span> compression, the <span style="font-weight: bold;">Sw:FileInfo</span> field in the request contains <span style="font-weight: bold;">SwCompression=None</span>.

If a transfer is made <span style="font-style: italic;">with</span> compression, the file is compressed using ZIP (by default) and the <span style="font-weight: bold;">Sw:FileInfo</span> field in the request contains <span style="font-weight: bold;">SwCompression=Zip</span>.

To compress with GZIP or ZLIB, set <span style="font-weight: bold;">SwCompression=GZIP</span> or <span style="font-weight: bold;">SwCompression=ZLIB</span> in the <span style="font-weight: bold;">[File information](../../swiftnet_connector/swiftnet_configuring#File_information)</span> (<span class="code">[file\_info](../../swiftnet_connector/swiftnet_configuring#_file_info)</span>) parameter of the Trading Partner or in the <span class="code">[rcv\_msg](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list#_rcv_msg)</span> parameter when submitting a transfer.

<span id="compress_InterAct"></span>

## InterAct transfers

If a transfer is made <span style="font-style: italic;">without</span> compression, there are no changes to the request that is sent.

If a transfer is made <span style="font-style: italic;">with</span> compression, Gateway sets compression attributes in the <span style="font-weight: bold;">RequestPayload/ ResponsePayload</span> tag. The compression attributes have the form: dt="Zip-Base64". For example, &lt;RequestPayload dt="Zip-Base64">.

Gateway encodes the compressed message in base 64 and carries out the following operations:

-   When sending a message: compression with ZIP (by default) and conversion to base 64
-   When receiving a message: conversion from base 64 and decompression (if the compression algorithm is known - ZIP, ZLIB or GZIP)

To compress using GZIP or ZLIB, you must specify it in the Transfer Request when starting a transfer. In the <span style="font-weight: bold;">[HTTP/FTP](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_http_ftp_tab)</span> tab,<span style="font-weight: bold;"> HTTP CGI parameters/ FTP user command</span> field, enter dt=\\"GZIP-Base64\\" or dt=\\"ZLIB-Base64\\".

Alternatively, if you are using online commands, set the <span class="code">[ftp\_command](../../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_cli/transfer_req_parameter_list#_ftp_command)</span> parameter to dt=\\"GZIP-Base64\\" or dt=\\"ZLIB-Base64\\".

<span style="font-weight: bold;">Note:</span> Gateway supports compression/decompression for embedded payload.

<span id="manual_compression"></span>

## Manual compression and decompression

Gateway supports manual compression and decompression for algorithms other than ZIP, GZIP or ZLIB. You have to compress the file/message before it is sent and decompress the file/message after it is received.

### Sending a message or a file using an algorithm other than ZIP, GZIP or ZLIB

<span style="font-weight: bold;">FileAct:</span> Before sending the file, compress it using your specific compression algorithm. Specify the algorithm in the Trading Partner object or Transfer Request object as described in [FileAct transfers](#compress_FileAct).

<span style="font-weight: bold;">InterAct:</span> Before sending the message, compress it using your specific compression algorithm. Carry out a normal message transfer as you would for a message that is not compressed.

### Receiving a message or a file that it compressed using an unknown compression algorithm

For both FileAct and InterAct, after a file/message is received with an unknown compression algorithm, an information message stating that the compression type is not supported is written to the log and the transfer ends normally. You then need to decompress the file/message.

Related topics

[Configuring the <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>/SWIFTNet environment](../../swiftnet_connector/swiftnet_configuring)

[Trading Partner objects](../../../../managing_partners_start_here/trading_partners_start_here)

[Working with Trading Partner objects](../../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_(gui))

[Working with Trading Partners (command line)](../../../../managing_partners_start_here/trading_partners_start_here/working_with_trading_partners_cli)

[SWIFTNet Proof keeping](../swiftnet_proof_keeping)

[Modifying conffile parameters](../../../../configuration_start_here/t_gw_config_conffile_paras_modify)

[SWIFTNet-specific user exits](../../swiftnet_connector/swiftnet_configuring)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
