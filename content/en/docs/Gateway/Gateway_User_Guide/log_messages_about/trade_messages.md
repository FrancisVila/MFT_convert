{
    "title": "Trade messages (TRADE)",
    "linkTitle": "TRADE",
    "weight": "520"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

This topic lists TRADE log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE101I"></span>101</p>         </td>
         <td><p>TRADE I TRACE [%1]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic message information, details in the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE102E"></span>102</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E OPENERR [%1] Couldn't open file %2 (%3)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer file could not be opened.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File directory</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE103E"></span>103</p>         </td>
         <td><p>TRADE E READERR [%1] Invalid file format %2 (%3)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received file has an unexpected format.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File directory</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE104E"></span>104</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ACK [%1] Invalid MIC returned ('%2') expected '%3' [%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment does not contain the expected MIC.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Received MIC</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Expected MIC</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE105E"></span>105</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ACK [%1] Invalid signature returned ('%2') expected '%3' [%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment does not contain the expected signature (S/MIME only).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Received signature</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Expected signature</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE106E"></span>106</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ACK [%1] Invalid content type returned ('%2') expected '%3' [%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment does not contain the expected Content-Type (S/MIME only).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Received Content-type</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Expected Content-type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE107E"></span>107</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ACK [%1] Invalid content id returned ('%2') expected '%3' [%4]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment does not contain the expected Content-Id (S/MIME only).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Received Content-Id</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Expected Content-Id</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE108E"></span>108</p>         </td>
         <td><p>TRADE E ACK [%1] Invalid %3 originator '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment contains invalid originator.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE109E"></span>109</p>         </td>
         <td><p>TRADE E ACK [%1] Invalid %3 destination '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received acknowledgment contains invalid destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact your exchange partner</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE110E"></span>110</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E RECV_ERR [%1] Transfer has been already received ([%2]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Duplicated transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Already received transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE111I"></span>111</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ACK [%1] acknowledgment found: [%2]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An acknowledgment has been found for the received transfer (only logged for AS2 synchronous acknowledgment requests).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE112I"></span>112</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I NO_ACK [%1] not yet acknowledged</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No acknowledgment has been found for the received transfer (only logged for AS2 synchronous acknowledgment requests).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE113I"></span>113</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ACK [%1] acknowledges transfer [%2]</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A valid acknowledgment has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE114E"></span>114</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ACK [%1] acknowledged transfer not found</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An unknown acknowledgment has been received. Acknowledged transfer could not be found.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE115E"></span>115</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E SECURITY [%1] Invalid acknowledgment URL requested (%2)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received transfer has an invalid acknowledgment request.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>URL acknowledgment requested</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Trading Partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE116E"></span>116</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E SECURITY [%1] Received file is not signed</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received file is not signed.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Trading Partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE117E"></span>117</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E SECURITY [%1] Received file is not ciphered</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Received file is not encrypted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Trading Partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE118E"></span>118</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E SECURITY [%1] Requested acknowledgment doesn't match trading partner configuration</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested acknowledgment security (signed/unsigned/none) does not match trading partner configuration.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check Trading Partner configuration.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE120I"></span>120</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I DECODED [%1] %2 %3 file received from '%4' to '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incoming file for local partner has been correctly unpacked</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Packaging format (S/MIME, AS1, AS3, AS3)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE121I"></span>121</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I DECODED [%1] %2 %3 file received from '%4' to remote partner '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Incoming file for remote partner has correctly been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Packaging format (S/MIME, AS1, AS3, AS3)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE122E"></span>122</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ERROR [%1] Decoding error: %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A PassPort PS SECS error occurred while decoding.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE123I"></span>123</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODED [%1] %2 %3 file encoded from '%4' to '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Outgoing file has been packed correctly.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Packaging format (S/MIME, AS1, AS3, AS3)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE124W"></span>124</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE W ACK [%1] acknowledges transfer [%2] with error '%3'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A negative acknowledgment has been received.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Acknowledged transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to error message received.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE125I"></span>125</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODED [%1] %2 %3 file to send from '%4' to '%5'</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A routed file is ready to be sent.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Packaging format (S/MIME, AS1, AS3, AS3)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>File or receipt depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Originator</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Destination</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE126E"></span>126</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E DECODE [%1] Signature cannot be trusted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>This message is displayed when the signature cannot be verified. Usually this message is displayed when the signature certificate does not correspond with the expected certificate.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE127I"></span>127</p>         </td>
         <td><p>TRADE I ACK [%1] should acknowledge transfer [%2]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new packaging task has been started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer ID of ACK message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Transfer ID of message to be acknowledged</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE130I"></span>130</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODE [%1] Preparing %2 to send</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new packaging task has been started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE131I"></span>131</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODE [%1] Start encoding %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File is to be encoded.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE132I"></span>132</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODE [%1] End encoding %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File has been encoded correctly.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE133E"></span>133</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ENCODE [%1] Encoding %2 aborted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Failed to encode file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If present, refer to the corresponding log message 134.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE134E"></span>134</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E ERROR [%1] Encoding error: %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A PassPort PS SECS error occurred while encoding.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Error message</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to the error message.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE140I"></span>140</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I ENCODE [%1] Extracting information from encoded %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new task has been started to check a routed file content.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE141I"></span>141</p>         </td>
         <td><p>TRADE I INFO [%1] Originator '%2' is partner '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trading Partner object found for the originator of the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Partner identification name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Matching Trading Partner object</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE142I"></span>142</p>         </td>
         <td><p>TRADE I INFO [%1] Destination '%2' is partner '%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 1</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trading Partner object found for the destination of the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Partner identification name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Matching Trading Partner object</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE143W"></span>143</p>         </td>
         <td><p>TRADE W INFO [%1] Destination '%2' does not match partner'%3'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The destination of the transfer has only been partially matched by a Trading Partner object. Some of the expected properties do not match (for example, allowed direction for the transfer).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Partner identification name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Trading Partner object</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE144E"></span>144</p>         </td>
         <td><p>TRADE E INFO [%1] Originator '%2' not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No Trading Partner object has been found for the originator of the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Partner identification name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE145E"></span>145</p>         </td>
         <td><p>TRADE E INFO [%1] Destination '%2' not found</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>No Trading Partner object has been found for the destination of the transfer.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Partner identification name</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE146"></span>146</p>         </td>
         <td><p>TRADE I INFO [%1] Message Id: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message Id (x_message_id) for outgoing and incoming transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>Message id of the transfer         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE147"></span>147</p>         </td>
         <td><p>TRADE I INFO [%1] Receipt reply to transfer [%2]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Transfer id to which the ack is sent (x_reply_to_xfer), for outgoing receipt transfers.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier of the receipt</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td>Transfer identifier of the original transfer         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE150I"></span>150</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I DECODE [%1] Start analyzing received %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A new unpacking task has been started.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE151I"></span>151</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I DECODE [%1] Start decoding %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Start unpacking the received file.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE152I"></span>152</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE I DECODE [%1] End decoding %2</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File has been unpacked correctly.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE153E"></span>153</p>         </td>
         <td><p><span style="font-weight: bold;">TRADE E DECODE [%1] Decoding %2 aborted</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error - Log level 2</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Failed to decode.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File or receipt, depending on the file being handled</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>If present, refer to the corresponding log message 122.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE154W"></span>154</p>         </td>
         <td><p>TRADE W DECODE [%1] Duplicated file %2 has been deleted</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The duplicate file indicated in the message has been deleted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>File that was deleted</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE160E"></span>160</p>         </td>
         <td><p>TRADE E SMAPI [%1] Invalid signing certificate for %3 partner '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid signing certificate for partner. The cryptographic operation cannot continue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Trade partner name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol format</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE161E"></span>161</p>         </td>
         <td><p>TRADE E SMAPI [%1] Invalid ciphering certificate for %3 partner '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Invalid ciphering certificate for partner. The cryptographic operation cannot continue.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Trade partner name</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Protocol format</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE170E"></span>170</p>         </td>
         <td><p>TRADE E ERROR  [%1] Couldn't read dynamic information for '%2'</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Gateway could not find the EDI originator and destination. A timeout may have occurred when retrieving the information from PassPort.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Transfer identifier</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Check the value of the <span class="code">vsite_query_timeout</span> parameter in the <span class="code">pelsetup.def</span> file. This parameter specifies the waiting timeout value (in seconds) when retrieving information from PassPort. The default value is 20 seconds.</p>
<p>If necessary, increase the value of the <span class="code">vsite_query_timeout</span> parameter.</p>
<p>For information about editing the <span class="code">pelsetup.def</span> file, refer to <a href="../../configuration_start_here/t_gw_config_conffile_paras_modify">Modifying conffile parameters</a>.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="TRADE201E"></span>201</p>         </td>
         <td><p>TRADE E TRACE [%1]</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Generic error message, details in the message.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Message</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
