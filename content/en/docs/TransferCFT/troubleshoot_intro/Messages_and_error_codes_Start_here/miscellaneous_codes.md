{
    "title": "Miscellaneous codes",
    "linkTitle": "Miscellaneous codes",
    "weight": "480"
}# <span id="title"></span>Miscellaneous codes

The codes in this topic are listed by protocol.

### <span id="FPDU_Build_Error_Codes__PeSIT_"></span>FPDU Build error codes (PeSIT)

This code specifies a build error in the received PeSIT FPDU. It forms the "PDU iNN"-type protocol diagnostic code.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Error code</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td width="19.396%">
            <p>1</p>
         </td>
         <td width="80.604%">
            <p>Received AckCONNECT FPDU header does not conform: an error 
 was detected in the source or target identifier content. The source 
 identifier must be null. The target identifier must be the same as the 
 source identifier sent in the CONNECT FPDU</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="19.396%">
            <p>2</p>
         </td>
         <td width="80.604%">
            <p>Reception of two or more FPDUs concatenated in one NSDU. 
 According to protocol specifications, an FPDU cannot be followed or preceded 
 by another FPDU</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>3</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of a CONNECT FPDU followed by two bytes that 
 do not belong to it, but the CRC option has not been implemented</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>4</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of a CONNECT FPDU with an incorrect CRC</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>5</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Received CONNECT FPDU header does not conform: an error 
 has been detected in the source or target identifier content. The source 
 identifier must not be null. The target identifier must be null</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>6</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of an FPDU other than CONNECT with an incorrect 
 CRC</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>7</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of two or more FPDUs concatenated in one NSDU, 
 while the CRC option is active. According to the protocol specifications, 
 FPDU concatenation is inhibited with the CRC option enabled</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>8</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received FPDU does not conform: the size indicated 
 is smaller than the minimum size of an FPDU. The minimum size of an FPDU 
 in the PeSIT protocol is six bytes (length of the header). If a CRC is 
 applied, the minimum size of an FPDU becomes eight bytes (length of a 
 header with its CRC)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>9</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received CONNECT-phase FPDU does not conform: 
 an error has been detected in the target identifier in the header</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>10</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received CONNECT-phase FPDU does not conform: 
 an error has been detected in the source identifier in the header</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>11</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of a network message that is smaller than the 
 minimum size of an FPDU. The minimum size of an FPDU in the PeSIT protocol 
 is six bytes (length of the header). If a CRC is applied, the minimum 
 size of an FPDU becomes eight bytes (length of a header with its CRC)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>12</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Concatenated FPDU with invalid header</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>13</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of an NSDU that is larger than that negotiated</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>14</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received FPDU does not conform: an error has 
 been detected in the phase byte</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>15</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of the received RelCONNECT FPDU does not conform: 
 an error has been detected in the source or target identifier content. 
 The source identifier must be null. The target identifier must be the 
 source identifier of the CONNECT FPDU</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>16</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received FPDU does not conform: the size indicated 
 is greater than the length of the received network message</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>17</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Header of a received SERVICE phase FPDU does not conform: 
 an error has been detected in the source or target identifier in the header</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>18</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Received FPDU of unknown type</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>19</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Received FPDU of a phase inconsistent with its type</p>
         </td>
      </tr>
</table>

### <span id="CFT_Numeric_codes___OFTP__ODETTE__protocol"></span>Transfer CFT Numeric codes - OFTP (ODETTE) protocol

These codes, specific to the ODETTE protocol and internal to the Transfer CFT,
indicate the source of the failure. This code forms the DIAGP protocol diagnostic
code. Values are expressed in hexadecimal.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Error code</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td width="19.396%">
            <p>0101</p>
         </td>
         <td width="80.604%">
            <p>Application area allocation error</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="19.396%">
            <p>0102</p>
         </td>
         <td width="80.604%">
            <p>Unknown event during network connection</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0150</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Protocol release error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0151</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Invalid restart value</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0152</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>CREDIT value error:</p>
            <p>1. Reception of a CDT FPDU but the "credit" has 
 not been used up</p>
            <p>2. Reception of a CDT FPDU but the negotiated "credit" 
 value is 0</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0202</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Restart position negotiation. The position returned by 
 the partner is higher than the proposed position</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0203</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Restart option proposed by the requester and that required 
 by the server (RESYNC parameter) are incompatible</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0204</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Compression negotiation. The compression value returned 
 by the partner is greater than the proposed value</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0205</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Network buffer length negotiation. The buffer size requested 
 by the partner is less than 128 or greater than that proposed</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0206</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>CREDIT negotiation. The "credit" value requested 
 by the partner is out of bounds</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0207</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Transfer DIRECTION negotiation. The value requested by 
 the partner and the SRIN (or SROUT) parameter value are incompatible</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0208</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>PAD option negotiation (special logic). The partner requests 
 "special logic" whilst the PAD parameter is set to "NO" 
 (default value)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0250</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Restart position error. Reception of a restart request 
 (SFID FPDU) but the "no restart" option has been previously 
 negotiated</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0301</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>During the protocol recognition phase the <span>Transfer CFT</span> does 
 not receive the expected string: "ODETTE FTP READY"</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0350</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>The total length of "subrecords" forming the 
 FPDU is different from the FPDU size specified in the SDATAIN field</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0351</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Invalid size for subrecord sent</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0401</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>A restart is requested by the partner but the restart option 
 is not set (RESYNC parameter)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0402</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of a "CREATE CONF NEG" FPDU: creation 
 of the receive file refused by the partner</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0501</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of an "ABORT" FPDU: transfer interrupted 
 by the partner</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0550</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>The SRUSIZE parameter value is less than 128, which is 
 forbidden by the protocol</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0551</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Invalid restart parameter value</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0601</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>IDF incompatibility. The received NIDF value does not correspond 
 to the IDF requested (RECV IDF=xxxx command). </p>
            <p>Note: the only valid 
 value for the IDF parameter of the RECV request is "*"</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0650</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Reception of a negative A_SELECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0701</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Error during the file de-selection phase at the partner 
 end</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0750</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Internal monitor error: attempt to send a DATA FPDU but 
 the "credit" has been completely spent and the <span>Transfer CFT</span> is waiting 
 for a CDT FPDU</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0751</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Record size is greater than the size of the exchange buffer</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A00</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local SSRM FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A02</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local SSID FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A03</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local ASSID FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A04</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local SFID FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A05</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local EFID FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A06</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local ESID FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A07</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local CDT FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A08</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local CD FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A09</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>ocal EERP FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0A0A</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local DTF FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B00</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Formatting error in connection acknowledge FPDU</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B01</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local SFPA FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B02</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local SFNA FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B03</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local EFPA FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B04</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local EFNA FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="19.396%">
            <p>0B05</p>
         </td>
         <td colspan="1" rowspan="1" width="80.604%">
            <p>Local RTR FPDU formatting error</p>
         </td>
      </tr>
</table>

### <span id="CFT_Mnemonic_codes___Odette_protocol"></span>Transfer CFT Mnemonic codes - ODETTE protocol

These codes, specific to the ODETTE protocol and internal to the Transfer CFT,
indicate the source of the fault.

This code forms the "XXX HHHH"-type DIAGP protocol diagnostic
code. Values are expressed in mnemonic form.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Error code</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr valign="top">
         <td width="26.821%">
            <p>CDT</p>
         </td>
         <td width="73.179%">
            <p>Error during "credit" negotiation</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="26.821%">
            <p>DAT</p>
         </td>
         <td width="73.179%">
            <p>Synchronization problem in "credit" and "data" 
 exchanges</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>FMT</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Internal FPDU formatting error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>IDF</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Received NIDF incompatible with sent IDF</p>
            <p>Note: only the RECV 
 IDF=* command is valid in ODETTE</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>LDT</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Error in the network buffer size negotiation phase</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>MSG</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Error when acknowledging the EERP message</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>PAD</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Special logic negotiation error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>POS</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Restart point negotiation error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>RST</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Restart option negotiation error</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>SFI</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Error during negotiation of a send file parameter (SFID 
 FPDU)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>SSI</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Error during negotiation of a session parameter (SSID FPDU)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="26.821%">
            <p>VER</p>
         </td>
         <td colspan="1" rowspan="1" width="73.179%">
            <p>Error in the protocol software release number (at present 
 this number is set to 1)</p>
         </td>
      </tr>
</table>

### <span id="FPDU_Mnemonic_codes___PeSIT_protocol"></span>FPDU Mnemonic codes - PeSIT protocol

This code forms the "XXX NNN" or "XXX iNNN" DIAGP
protocol diagnostic code in the PeSIT protocol; it represents the XXX
part. Values are expressed in mnemonic form.

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Code</th>
         <th>FPDU</th>
      </tr>
   </thead>
      <tr valign="top">
         <td width="39.212%">
            <p>ABO</p>
         </td>
         <td width="60.788%">
            <p>ABORT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ACF</p>
         </td>
         <td width="60.788%">
            <p>Ack CLOSE REMOTE FILE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ACO</p>
         </td>
         <td width="60.788%">
            <p>Ack CONNECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ACR</p>
         </td>
         <td width="60.788%">
            <p>Ack CREATE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>AID</p>
         </td>
         <td width="60.788%">
            <p>Ack IDT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ADS</p>
         </td>
         <td width="60.788%">
            <p>Ack DESELECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>AMG</p>
         </td>
         <td width="60.788%">
            <p>Ack MESSAGE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>AOF</p>
         </td>
         <td width="60.788%">
            <p>Ack OPEN REMOTE FILE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ARD</p>
         </td>
         <td width="60.788%">
            <p>Ack READ</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ASE</p>
         </td>
         <td width="60.788%">
            <p>Ack SELECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ASY</p>
         </td>
         <td width="60.788%">
            <p>Ack SYNC</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>ATE</p>
         </td>
         <td width="60.788%">
            <p>Ack TRANSFER END</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>AWR</p>
         </td>
         <td width="60.788%">
            <p>Ack WRITE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>CON</p>
         </td>
         <td width="60.788%">
            <p>CONNECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>CRE</p>
         </td>
         <td width="60.788%">
            <p>Ack CREATE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>CRF</p>
         </td>
         <td width="60.788%">
            <p>CLOSE REMOTE FILE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>DMG</p>
         </td>
         <td width="60.788%">
            <p>Start of MESSAGE</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>DSE</p>
         </td>
         <td width="60.788%">
            <p>DESELECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="39.212%">
            <p>DTE</p>
         </td>
         <td width="60.788%">
            <p>DATA TRANSFER END</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>DTF</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>DATA</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>FMG</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>End of MESSAGE</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>IDT</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>TRANSFER INTERRUPT</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>MMG</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>Middle of MESSAGE</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>MSG</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>MESSAGE</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>ORF</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>OPEN REMOTE FILE</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>RCO</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>Release CONNECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>RDF</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>READ</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>RST</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>RESTART</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>SEL</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>SELECT</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>SYN</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>CHECK</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>TFE</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>TRANSFER END</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="39.212%">
            <p>WRI</p>
         </td>
         <td colspan="1" rowspan="1" width="60.788%">
            <p>WRITE</p>
         </td>
      </tr>
</table>
