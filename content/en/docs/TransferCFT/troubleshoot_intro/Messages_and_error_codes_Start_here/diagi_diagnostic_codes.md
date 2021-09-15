{
    "title": "DIAGI - Diagnostic codes",
    "linkTitle": "DIAGI - Diagnostic codes",
    "weight": "440"
}# <span id="title"></span>DIAGI - Diagnostic codes

## <span id="Internal_diagnostic_codes"></span>Transfer CFT internal diagnostic codes

Diagnostic codes provide general information on the cause of the error. It
is independent of the operating system and of the network access method
used for the transfer. Some codes are specific to a protocol. If so, this
is indicated in the label.

## Diagnostic code values

DIAGI codes with a value between 001 and 499 indicate a local issue; values
between 501 and 999 correspond to a fault reported by the partner.

This means that when you troubleshooting, if the DIAGI code is greater than 500 it refers to a remote issue. To find the actual DIAG, subtract 500 from the displayed code. If the DIAG is 916, for example, the issue is a remote problem corresponding to DIAG 416 (Maximum number of transfers reached).

## <span id="Event_column_in_diagnostic_codes"></span>Event column in diagnostic codes

The Event column explains the
possible cause of the transfer error. Brief information on the type of error which caused
the transfer failure:

-   SYS: System error
-   NET: Error detected
    by the network layers (Transfer CFT layers, manufacturer or network layers)
-   PROT: Fault
    detected by the file transfer protocol
-   FILE: Transferred
    file access error returned by the operating system
-   DATA: Error
    accessing Transfer CFT basic data: parameter, partners, catalog, communication,
    log, statistics and secondary indirection files (lists of partners, files,
    and so on)
-   PARAM: Transfer
    execution error following a parameter setting error
-   AUTH: Transfer
    denied following an authorization check by Transfer CFT
-   OVER: The
    transfer cannot be executed because the monitor's resources are saturated
    or a parameter setting limit has been exceeded
-   OUT: The transfer
    request is aborted after the maximum number of retries
-   USER: The
    transfer is interrupted following an action by the operator

<!-- -->

-   SSL: Incident
    detected by the secured protocol SSL 

## <span id="Behavior_column_in_diagnostic_codes"></span>Consequence column in diagnostic codes

The Consequence column provides
information on the Transfer CFT behavior following a transfer failure.
The resulting status of the transfer D, H or K:

-   D: the transfer
    can still be executed using the RESTART, NEXT, RETRY or COMMUT mechanisms
-   H or K: the transfer
    is aborted, the error procedure

Further transfer attempts

For the D status, the following are possible to execute
the transaction:

-   RESTART: the transfer
    has been interrupted. The monitor waits for a period fixed by the WSCAN
    parameter (CFTCAT command) before trying to restart the transfer with
    the same access data. It increments the restart counter for the protocol,
    the counter limit being determined by the RESTART parameter (CFTPROT command).
-   NEXT: the transfer
    has been interrupted. The monitor waits for a period fixed by the WSCAN
    parameter (CFTCAT command) before trying to restart the transfer with
    the same access data. It does not increment the restart counter. There
    is therefore no limit to the number of retries following this error.
-   RETRY: the transfer
    has been interrupted. Transfer CFT waits for a period fixed by the RETRY\*
    parameters before trying to restart the transfer, without changing the
    partner access data (same protocol, same network address. It increments
    the retry counter specific to the partner access data, the counter limit
    being determined by the RETRYM parameter (CFTnetwork command).
-   COMMUT (switching):
    the transfer has been interrupted. The monitor waits for a period fixed
    by the WSCAN parameter (CFTCAT command) before trying to restart the transfer.
    It ignores the transfer access data and tries a "switching"
    path to reach the partner: another IP address, another protocol or a
    backup partner.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Protocol switching also means 
 communication system (network) switching. The switching mechanism does 
 not provide for use of other network resources (CFTNET commands associated 
 via the CLASS) for a given protocol (CFTPROT command). Problems associated 
 with network resources are masked by the common network access method 
 which manages them.         </td>
      </tr>
</table>

In the case of an H or K status the transfer is aborted, the error procedure can be executed:

-   ABORT: the transfer
    is aborted
-   Execution
    of the error procedure if the transfer switches to the K or H status:
    -   EXECE: the procedure is executed. This is the procedure
        defined by CFTPARM EXEC\*E parameters. If these parameters are not set,
        the procedure is not executed.

The "No CAT" indication specifies that no
catalog entry had been created for the transfer when the error occurred.
The transfer request is rejected.<span id="Internal_diagnostic_codes_table"></span>

DIAGI - Internal diagnostic codes
table

The following table makes references to DIAGP. For details, please see the [DIAGP section.](../general_protocol_diagnostics)

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>DIAGI Code</th>
         <th>Event</th>
         <th>Consequence</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>0</p>
         </td>
         <td>
            <p>The transfer has terminated correctly</p>
         </td>
         <td>
            <p>Execution of normal EXECRF or EXECSF end of transfer procedures</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>001</p>
         </td>
         <td>
            <p>SYS: Error creating the message queue or allocating the 
 memory</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>002</p>
         </td>
         <td>
            <p>Context definition error</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>003</p>
         </td>
         <td>
            <p>SYS - Context allocation error</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>004         </td>
         <td>MQCONN           </td>
         <td>          </td>
      </tr>
      <tr>
         <td>005         </td>
         <td>MQOPEN         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>006         </td>
         <td>MQPUT         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>
            <p>100</p>
         </td>
         <td>
            <p>FILE - File input/output error</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>101</p>
         </td>
         <td>
            <p>FILE - Error creating the receive file</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>102</p>
         </td>
         <td>
            <p>1.FILE - Error allocating the transfer 
 file</p>
            <p> </p>
         </td>
         <td>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>2.FILE - The receive 
 file cannot be allocated (FDISP=OLD case)</p>
         </td>
         <td>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>103</p>
         </td>
         <td>
            <p>1.FILE - The file cannot be deleted before 
 the receive file is created (FDISP = DELETE case)</p>
         </td>
         <td>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>2.FILE - Error 
 deleting the sent file, if a deletion has been requested (FACTION = DELETE)</p>
         </td>
         <td>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>104</p>
         </td>
         <td>
            <p>1. FILE - Error opening the transfer file 
 </p>
            <p>2. FILE - The 
 receive file cannot be erased (FDISP = ERASE case): file opening problem</p>
            <p>3. FILE - Prior 
 to reception, the receive file could not be opened to check that it was 
 empty (FDISP = VERIFY case)</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>105</p>
         </td>
         <td>
            <p>1. FILE - Error closing the transfer 
 file</p>
            <p>2. FILE - The 
 receive file cannot be erased (FDISP = ERASE case: file closing problem</p>
            <p>3. FILE - Prior 
 to reception, the receive file could not be closed after checking that 
 it was empty (FDISP = VERIFY case)</p>
            <p>4. FILE - The 
 sent file cannot be deleted following an erase request (FACTION = ERASE 
 case)</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>106</p>
         </td>
         <td>
            <p>FILE - Error recording the current position in the transfer 
 file (synchronization point setting)</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>107</p>
         </td>
         <td>
            <p>FILE - Error setting the pointer to a re-synchronization 
 point in the file (for a transfer restart)</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>108</p>
         </td>
         <td>
            <p>1. FILE - Send file read error in data transfer phase</p>
            <p>2. FILE - Prior to reception, the receive file could 
 not be read to check that it was empty (FDISP = VERIFY case)</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>109</p>
         </td>
         <td>
            <p>FILE - Data write error in the receive file</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>110</p>
         </td>
         <td>
            <p>1. FILE - The send file does not exist</p>
            <p>2. FILE - The receive file to be created does not 
 exist, even though the FDISP parameter requires it (FDISP=OLD). DIAGP 
 is then set to NO OLD</p>
         </td>
         <td>
            <p>H status - ABORT, EXECE in requester mode</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>111</p>
         </td>
         <td>
            <p>FILE - Insufficient space to create the file</p>
         </td>
         <td>
            <p>H status - ABORT in requester mode, EXECE in requester 
 mode </p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td>112         </td>
         <td>Nonexistent unit         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>113</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - The file to be created already exists, even though 
 the FDISP parameter prohibits it (FDISP = NEW). DIAGP is then set 
 to NO NEW</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE in requester mode</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>114</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Data write error in the receive file: file space 
 full</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>If there is a <a href="../protocol_diagnostic_codes">DIAGP</a> for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>115</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. FILE - The transfer owner is not authorized to 
 access the file</p>
            <p>2. FILE - The file cannot be deleted before the receive 
 file has been created (FDISP = DELETE case)Protected file</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE in requester mode </p>
            <p>Please see the <a href="internal_a_m_start here.htm">Access management </a>sections for more information.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>3. FILE - The sent file cannot be deleted following 
 a deletion request</p>
            <p>(FACTION = DELETE case) Protected file</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Please see the <a href="internal_a_m_start here.htm">Access management </a>sections for more information.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>120</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Counter check error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>121</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>USER - Interruption by the operator</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>122</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SYS - Error allocating memory when the transfer is executed</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RESTART</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>123</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Error setting the pointer to a resynchronization point in the file: the restart point requested by the partner is incorrect. </p>
            <p>This can occur when the synchronized points are not flushed from the catalog (if the CFTCAT's <code>updat </code>parameter is greater than 1, the UCONF<span>cft.server.catalog.sync.enable</span> is set to <span>No</span>, or both of these are true) due to an unexpected event such as a process, system, or disk crash.</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>124</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Error: transfer aborted</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>126</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - LRECL error (record length)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>127</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - The receive file is not empty (FDISP = VERIFY case)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>128</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. FILE - Error deselecting the file</p>
            <p>2. FILE - Error deselecting the receive file</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>3. FILE - Error accessing the send file (allocating 
 or opening), subsequent to a file erase request (FACTION = ERASE)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE  unless there is an 
 allocation error in sender server mode</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>129</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Error during file decompression </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>130</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Error during file compression</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>131</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - IDF different on ODETTE SELECT</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>132</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Error accessing the parameter setting indirection 
 file (list of files, list of partners)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT </p>
            <p>If the file does not exist, no transfer is executed. Only 
 the generic request remains in the catalog. If an error occurs while reading 
 the indirection file, the transfers generated for the items (files or 
 partners) that have already been read are executed</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>133</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - The FOR parameter in the CFTDEST command is invalid</p>
            <p>1. FOR=LOCAL when in the switching mode</p>
            <p>2. FOR=COMMUT when not in the switching mode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No catalog entry. Check the CFTDEST object in the configuration.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>134</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - CFTEXIT call error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Check the information in the cftlog and the cft.out files.</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>135</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. FILE - The send file is locked</p>
            <p> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>2. FILE - The receive file is locked</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>136</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Duplication of the temporary file</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> or <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>137</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - The file exists, the "rename" operation 
 is therefore impossible</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> or <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>138</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. FILE - No temporary file has been defined in the 
 send mode and the transfer requires the COPY mechanism. No transfer is 
 triggered and the generic request remains in the catalog</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State K - ABORT</p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> or <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
            <p> </p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> or <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>2. FILE - No temporary file has been defined in the 
 receive mode for a file with versions or for a transfer requiring deconcatenation 
 (COPY)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State K - ABORT, EXECE</p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> or <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>139         </td>
         <td>Incorrect attributes file         </td>
         <td>
            <p>Check the cftlog file and the diagp/diagc in the catalog record.</p>
            <p>
Also, check the FLRECL/FRECFM parameters in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>142</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - The "rename" operation failed</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Check the WFNAME parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> command.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>144</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>MVS transfer busy</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State D - Retry</p>
            <p>Specific to z/OS environments.</p>
         </td>
      </tr>
      <tr>
         <td>145         </td>
         <td>
<ol>
               <li value="1">The SEND file is outside of the workingdir tree.
                          </li>
               <li value="2">The temporary SEND file is outside of the workingdir tree.               </li>
</ol>
         </td>
         <td>
            <p>K status - ABORT</p>
            <p>Check the WORKINGDIR parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftsend">CFTSEND</a> object.</p>
         </td>
      </tr>
      <tr>
         <td>148         </td>
         <td>
            <p>1. The RECV file is outside of the workingdir tree.
           </p>
            <p> 2. The temporary RECV file is outside of the workingdir tree.
</p>
         </td>
         <td>
            <p>K status - ABORT</p>
            <p>Check the WORKINGDIR parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftrecv">CFTRECV</a> object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>150</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Could not access a file. This error may be due to one of several issues, for example the directory is empty, or  the file's name does not correspond to an applied filter.</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State K - ABORT. If the directory does not exist, no transfers 
 are triggered and only the generic request remains in the catalog. If 
 an error is detected when reading the directory, the transfers generated 
 for the items (directory menus) that have already been read are triggered.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>152</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Error during the concatenation phase at the start 
 of the transfer or during the de-concatenation phase at the send of the 
 transfer.</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State H - ABORT, EXECE</p>
            <p>Problem on homogeneous transfer issue. See <a href="../../../concepts/using_the_send_command/send_group_of_files_cl">Sending 
 a group of files </a></p>
            <p>Check the configuration - FNAME and WFNAME on the CFTSEND or CFTRECV object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>153</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - Error during the transfer. The file has been overwritten.</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State K - Short transfer cannot be restarted.</p>
         </td>
      </tr>
      <tr>
         <td>154         </td>
         <td>An error occurred when trying to transcode a file using NCHARSET parameter in the CFTSEND command before a send.          </td>
         <td>
            <p>Generates a DIAGI=730, DIAGP=ABO 399 on the remote side as the sender cannot transcode before sending.</p>
            <p>Check the diagp/diagc in the catalog to have more information.</p>
         </td>
      </tr>
      <tr>
         <td>155         </td>
         <td>This preprocessing error occurs when a preexec is specified, but launching the exec file failed (usually because the file was not found, but could be due to a busy or migrated file on z/OS [MVS]).
         </td>
         <td>
            <p>Generates:</p>
            <ul>
               <li>DIAGP: NO EXEC                </li>
               <li>DIAGC: PREEXEC LAUNCH ERROR               </li>
            </ul>
            <p>Check the PREEXEC parameter in the SEND, RECV, CFTSEND, and CFTRECV commands.</p>
         </td>
      </tr>
      <tr>
         <td>156         </td>
         <td>This error occurs if the maximum number of retries is reached when FACTION=RETRYRENAME.          </td>
         <td>
            <p>Generates: </p>
            <ul>
               <li>DIAGP: RETRYRENAME               </li>
               <li>Phasestep=K                </li>
            </ul>
            <p>Check these uconf values:</p>
            <ul>
               <li>cft.server.transfer.rrename.retry_delay               </li>
               <li>cft.server.transfer.rrename.max_retries               </li>
            </ul>
            <p>File defined in the FNAME parameter in the CFTRECV object should not exist when the retry occurs. Transfer can be restarted.</p>
         </td>
      </tr>
      <tr>
         <td>158         </td>
         <td>
            <p>There was an error while replacing Transfer CFT variables. </p>
            <p>The script referenced by <span>&amp;fname</span> in the CFTS68E   message is not executed. </p>
         </td>
         <td>In the script &amp;fname, modify  the variable &lt;var&gt; indicated in  the CFTS68E message.         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>160</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Handles the event 'no outstanding 
 transfer or implicit declaration'.</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No catalog entry is created.</p>
         </td>
      </tr>
      <tr>
         <td>200         </td>
         <td>An error occurred on a child transfer of this parent (generic) transfer. Refer to the child transfer in error for more information.         </td>
         <td>State K - ABORT,EXECE         </td>
      </tr>
      <tr>
         <td>203         </td>
         <td>PROF=SIT non-priority transfer          </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>220</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - FPDU reception</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>221</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Int/ext type match error: the type of a PI is not 
 consistent with its conversion type in the external format (for example, 
 a PI in DATE format to be converted to the STRING format)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>222</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Mandatory PI missing in FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>223</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Invalid PI length</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>224</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Invalid PGI length</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>225</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - PGI missing from the FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>226</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - PGI embedded in another PGI</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>230</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Protocol error. A protocol error has been detected: 
 DIAGP is set to the PeSIT or ODETTE code of the error detected</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>Contact the Support team for this type of unexpected error. Prior to doing so though, please collect as much information as possible regarding the transfer in error, including the remote partner information (product, configuration,...). </p>
            <p>Note that the 230 diagnostic codes may have different diagnostic protocols formats:</p>
            <ul>
               <li>diagp = eEEsSS: An unexpected internal error when the event "EE" occurs during the "SS" state.               </li>
               <li>diagp = PDU iNN: The PDU parameter "NN" is not correct.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>231</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Invalid action</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>232</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Event not found. An interaction not recognized by 
 the protocol mechanisms has been received in a given transfer context</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>233 </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Message send operation refused by the protocol used. 
 The following protocols do not support message send operations: PESIT SIT, PESIT EXT, ODETTE</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>This may require a trace. Please see <a href="../../traces_in_cft">How to use ATM traces</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>240</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Time-out expired (RTO parameter)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RETRY/COMMUT</p>
            <p>For more information, see <a href="../../admin_troubleshooting_server/admin_troubleshooting_runtime/troubleshoot_rto">Troubleshoot 240 or 740 RTO</a>.</p>
         </td>
      </tr>
      <tr>
         <td>241         </td>
         <td>Transfer time-out - requester         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>241         </td>
         <td>Transfer time-out - server          </td>
         <td>          </td>
      </tr>
      <tr>
         <td>243         </td>
         <td>Network connection time-out                  </td>
         <td>          </td>
      </tr>
      <tr>
         <td>244         </td>
         <td> Pre-connection time-out                     </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>260</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL - Security problem</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K state - ABORT</p>
            <p>DIAGP=PKI with I, E or S nnn</p>
            <p>nnn = SSL code alert </p>
            <p>See <a href="#ssl">SSL alert errors</a> and <a href="../../admin_troubleshooting_server/troubleshoot_security">Troubleshoot security errors</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>261</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL - Error linked to an internal PKI</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K state - ABORT</p>
            <p>DIAGP=PKI I nnn</p>
            <p>nnn = SSL code alert</p>
            <p>See <a href="#ssl">SSL alert errors</a> and <a href="../../admin_troubleshooting_server/troubleshoot_security">Troubleshoot security errors</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>262</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL - Error linked to the PKI system</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K state - ABORT</p>
            <p>DIAGP=PKIS nnn</p>
            <p>nnn = SSL code alert</p>
            <p>See <a href="#ssl">SSL alert errors</a> and <a href="../../admin_troubleshooting_server/troubleshoot_security">Troubleshoot security errors</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>263</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL - Error linked to an external PKI</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K state - ABORT</p>
            <p>DIAGP=PKIE nnn</p>
            <p>nnn = SSL code alert</p>
            <p>See <a href="#ssl">SSL alert errors</a> and <a href="../../admin_troubleshooting_server/troubleshoot_security">Troubleshoot security errors</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>278</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SSL - Invalid security profile</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K state - ABORT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>301</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>NET - Network addressing error (IP address) at the time 
 of connection</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - COMMUT</p>
            <p>The transfer will be retried for a minimum period equal 
 to the WSCAN parameter of the CFTCAT command. The next partner address 
 in the HOST parameter list (CFTTCP command) will be used for the 
 next retry. </p>
            <ul>
               <li>If the invalid address is the last one in the list, the next 
 protocol in the PROT parameter list (CFTPART command) will be used for 
 the next retry.                </li>
               <li>If the protocol used is the last in the list, the transfer 
 is either switched to the backup partner (IPART parameter of the CFTPART 
 command) or aborted (K status) with code 405, while maintaining the 
 diagnostic code of the last retry               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>302</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>NET - Network link broken (cut-off, time-out) outside the 
 connection phase. DIAGP is then set to VNRELI</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RETRY/COMMUT</p>
            <p>Up to "RETRYM" retries are performed for the 
 transfer and the access data. If the number of retries reaches the value 
 in the RETRYM parameter, <span>Transfer CFT</span> switches the access data. 
 </p>
            <p>The partner access data for the next retry will relate to the next HOST 
 parameter (CFTNET command), or the next PROT parameter (CFTPART command). 
 The restart counter is reset to 0. </p>
            <p>If the protocol used is the last in 
 the list, the transfer is either switched to the backup partner (IPART 
 parameter of the CFTPART command) or aborted with code 405, while maintaining 
 the diagnostic code (<a href="../general_protocol_diagnostics">DIAGP</a>) of the last retry</p>
            <p>See <a href="../../common_transfer_issues">Troubleshooting common transfer issues</a> for more information.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>303</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>NET - Network parameter error at the time of connection</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - COMMUT</p>
            <p>The transfer is retried using the 
 next protocol in the PROT parameter list (CFTPART command) as the new 
 partner access point.</p>
            <p> If the protocol used is the last in the list, the 
 transfer is either switched to the backup partner (IPART parameter of 
 the CFTPART command) or aborted (K status) with code 405, while maintaining 
 the diagnostic code of the last 
 retry.</p>
            <p>Cannot connect to the remote partner due to a local connection rejection. When using SFTP, check that the remote SAP value in CFTPART object is defined and is correct.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>350</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The user requesting the transfer is not authorized to perform 
 it</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State H</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>351</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The remote  requester is not authorized to use the transfer. 
 The transfer was in the H state. The monitor is running in the server/sender 
 mode</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State H</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>352</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The remote  requester is not authorized to create a transfer. 
 The monitor is running in the server/sender mode and the transfer was 
 to be created via a CFTSEND IMPL=YES</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State H</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>401</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Embedded broadcast list explicitly refused</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>For an explicit multi-partner request 
 (PART parameter in the CFTDEST command), a single partner, itself defined 
 as a partner list, aborts the request; only the generic list request set 
 to the K status remains in the catalog. No transfer is executed. </p>
            <p>For a multi-partner request via an indirection file (FNAME 
 parameter in the CFTDEST command), only the requests prior to the error 
 are executed</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>402</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - The PROT parameter of the CFTPART command does 
 not belong to the active protocol list (PROT parameter of the CFTPARM 
 command)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>403</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM: Invalid password</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No CAT</p>
            <p>The diagi = 403 is displayed only in the cftlog file</p>
            <p>CFTH22E NPART=PARTSSL rejected DIAGI=403 &lt;HOST=@IP_address&gt;</p>
            <p>On the requester the transfer status is D with diagi = 909 and the diagp = RCO 301, therefore  the transfer is retried up to RETRYM times.</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>404</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM: Open mode not authorized</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No CAT (in server mode)</p>
            <p>Check that the FNAME=&amp;NFNAME in the CFTSEND or CFTRECV object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>405</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>OUT: Transfer CFT has tried all possible partner access 
 points: HOST, PROT, IPART</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT, EXECE</p>
            <p>Check the configuration of the CFTPART and CFTTCP objects.</p>
            <p>Before reaching 405 diagi, multiple retries were executed. Check the cftlog file for informtion related to this transfer.</p>
            <p>After correcting the transfer, you can restart the transfer.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>406</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. OUT - Maximum number of retries reached (RESTART 
 parameter).</p>
            <p>DIAGP is set to MAXRST</p>
            <p>2. AUTH - The required start time for execution of 
 the transfer is outside the authorized time slot (OMINTIME / OMAXTIME); 
 there is no other possible protocol for this partner. DIAGP is set to 
 CALL OUT</p>
            <p>3. AUTH - The network resource associated with the 
 protocol does not accept outgoing calls; there is no other possible protocol 
 for this partner</p>
            <p>DIAGP is set to L 0B 022</p>
            <p>4. PARAM - There is no CFTN command for the 
 partner and for the last protocol in the list (CFTPART PROT parameter). 
 DIAGP is set to MAXRST</p>
            <p>5. OVER - Transfer CFT has reached the limit (RESTART 
 parameter) of authorized retries for the last partner protocol (CFTPART 
 PROT parameter). DIAGP is set to MAXRST</p>
            <p>6. PARAM - The SROUT parameter of the protocol cannot 
 be used to execute the transfer; there is no other possible protocol for 
 this partner. DIAGP is set to SROUT</p>
         </td>
         <td colspan="1" rowspan="1">
            <p> </p>
            <p> </p>
            <p>K status - ABORT, EXECE</p>
            <p> </p>
            <p> </p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>408</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - PART parameter not described by a CFTPART command</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>If a single CFTPART command is missing from an explicit 
 multi-partner request (PART parameter in the CFTDEST command), 
 the request is aborted. Only the generic list request, set to the K status, 
 remains in the catalog.</p>
            <p>No transfer is executed.</p>
            <p>For a multi-partner request via 
 an indirection file (FNAME parameter in the CFTDEST command), only transfers 
 with no partner defined are halted</p>
            <p>The other transfers are executed</p>Complete broadcasting (or collection) is unsuccessful without operator 
 intervention (partner definition and transfer retry). The end of transfer procedure is not executed.         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>409</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Unknown NPART parameter</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT</p>
            <p>Check the correspondence between the PROT, NSPART, and NRPART parameters in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftpart">CFTPART</a> object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>410</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Unknown CFTPROT command</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>Check that the PROT value in the  <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftpart">CFTPART</a> matches an active protocol PROT parameter of <a href="../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftparm">CFTPARM</a> object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>411</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>AUTH - File identifier (IDF) not authorized </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>If the IDF for one of the partners in an explicit multi-partner 
 request (PART parameter in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftdest">CFTDEST</a> command) is not authorized, the 
 request is aborted; only the generic list request set to the K status 
 remains in the catalog</p>
            <p>No transfer is executed</p>
            <p>For a multi-partner request via 
 an indirection file (FNAME parameter in the CFTDEST command), only transfers, 
 the IDFs of which are not authorized for the partner (CFTAUTH command) 
 are set to halted</p>
            <p>The other transfers remain active. </p>
            <p>However, 
 complete broadcasting (or collection) is unsuccessful without operator 
 intervention (grant authorization to the partners and retry the transfer); 
 the end of transfer procedure will not be executed</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>412</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>DATA - Catalog access error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p> As the 
 file could not be accessed, there is no change in the status or in the catalog DIAGI. </p>
            <p>The  CFTT21E should display in the log and contain GCS and GCR information that may be helpful for Axway support to diagnos the issue.</p>
            <p>For example, this type of error could be caused by  a corrupted catalog. If so, you could import and export the records to repair this.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>413</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>AUTH - File identifier not authorized</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT</p>
            <p>Check the SAUTH/RAUTH parameters in the <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftpart">CFTPART</a> object and the associated <a href="../../../c_intro_userinterfaces/web_copilot_ui/flow_def_intro/cftauth">CFTAUTH</a> objects.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>414</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. AUTH - The start time for execution of the transfer 
 is outside the authorized time slot (MAXTIME / MAXDATE of the SEND / RECV 
 command)</p>
            <p>DIAGP is then set to OUT TIME</p>
            <p>2. PARAM - The outgoing time slot of the partner is 
 null (OMINTIME / OMAXTIME)</p>
            <p>There is no intermediate partner</p>
            <p>DIAGP is then set to CALL OUT</p>
            <p>3. AUTH - No outgoing call authorized for the network 
 resource (CFTnetwork CNXOUT=0)</p>
            <p>DIAGP is then set to NO CALL</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
            <p>See <a href="../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftnet">CFTNET 
 - Network resources</a> and <a href="../../../admin_intro/admin_config_commands/network_resource_concepts"> Network 
 resources </a>for more information on network resource depletion prevention.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>415</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>OVER - Maximum number of partners reached</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>416</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. OVER - Maximum number of transfers reached (MAXTRANS 
 parameter)</p>
            <p>The transfer cannot be executed</p>
            <p>DIAGP is then set to MAXTRANS</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
            <p> </p>
            <p>Please see <a href="../../../concepts/about_parallel_transfers/prevent_network_depletion">Network resource depletion prevention (NRDP)</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>2. OVER - Maximum number of connections reached for 
 the network resource</p>
            <p>The transfer cannot be executed</p>
            <p>DIAGP is then set to MAXCNX</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
            <p>This status corresponds to a transfer refusal by the <span>Transfer CFT</span> protocol 
 task, even though the scheduler has not reached the MAXTRANS 
 limit.</p>
            <p>This occurs when the protocol task maintains active connections 
 after transfers have ended. Please see <a href="../../../concepts/about_parallel_transfers/prevent_network_depletion">Network resource depletion prevention (NRDP)</a>.</p>
            <p> </p>
            <p>WSCAN related behavior</p>
            <p>Technically, the next retry is triggered <b>wscan</b> minutes after the previous try. However, sometimes you may have a <span>Transfer CFT</span> log where the 416 diagnostic codes are not evenly distributed (by the same time intervals). This may occur if the scheduling task believes resources are available and schedules a retry, but in reality the resource is taken.</p>
            <p> </p>
            <p><i>Unix only </i>- If the runtime path is too long,  a diag 416 issue occurs and a message similar to the following displays in the <span>cft.out</span>: </p>
<blockquote>
            <p>CFTTCPS S_socket : start_soc : bind afunix</p>
            <p>CFTTCPS Invalid argument</p>
</blockquote>
            <p>If this error occurs, modify the path to the socket  in the <a href="../../../admin_intro/uconf/uconf_directory">UCONF </a><span>cft.unix.stcp.afunix</span> parameter according to the operating system limit as shown below:</p>
            <ul>
               <li>AIX: 1023               </li>
               <li>HP-UX: 92               </li>
               <li>Linux: 108               </li>
               <li>Solaris: 108               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>417</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. OVER - Maximum number of file tasks reached (MAXTASK 
 parameter)</p>
            <p>The transfer cannot be executed</p>
            <p>2. SYS- Insufficient system resources available to 
 execute an EXIT task</p>
            <p>The transfer cannot be executed</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>418</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>OVER - The total number of transfers in progress exceeds 
 one of the CNXIN, CNXOUT or CNXINOUT parameters for the partner</p>
            <p>The transfer cannot be executed</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RESTART</p>
            <p>If the number of retries exceeds the value of the RESTART 
 parameter (CFTPROT command), Transfer CFT switches to the access data of 
 the next protocol for this partner. See <a href="../../../concepts/about_parallel_transfers/multi_node_simultaneous_transfers">Configure multi-node simultaneous transfers</a>.</p>
            <p>See also, <a href="../../../concepts/about_parallel_transfers/faq">Frequently asked questions</a> and <a href="../../../concepts/about_parallel_transfers/multi_node_simultaneous_transfers">Configure multi-node simultaneous transfers</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>419</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>DATA - The transfer to be retried is not in the catalog 
 at the server end</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>ABORT</p>
            <p>Check the information in the cftlog file.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>420</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>DATA - On reception of a REPLY-type message, the original 
 transfer concerned by this reply is not found in the catalog at the server 
 end</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>ABORT</p>
         </td>
      </tr>
      <tr>
         <td rowspan="2">
            <p>421</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. SYS - Error executing a <span>Transfer CFT</span>file task</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>2. SYS - Error executing a <span>Transfer CFT</span> EXIT task</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>423</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>SYS or PARAM - EXIT task creation error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT</p>
            <p> Check the diagp and the cftlog file for more information on the context.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>424</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - CFTXLATE command not found for this transfer direction 
 and the source and target alphabets</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT</p>
            <p>Check  the XLATE value in the CFTSEND/CFTRECV object and the associated CFTXLATE object.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>426</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>USER (Directory Exit) - Error in the Directory Exit task</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No CAT (server mode)</p>
            <p>State K - ABORT (requester mode)</p>
         </td>
      </tr>
      <tr>
         <td>428         </td>
         <td>Incoming address verified by the VERIFY parameter in the CFTTCP object  was not accepted.         </td>
         <td>
            <p> No CAT</p>
            <p>Check the incoming address in the cftlog file

and compare it to the host value in the CFTTCP object; the check is done on the VERIFY value (in terms of digits).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>430</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PARAM - Transfer is inactive on the requester side</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>State D - ACT</p>
            <p>Check the partner's state.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>431</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>USER (Security) - CFTAPPL card is absent</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No CAT</p>
            <p>Transfer is not started and  there is no entry in the catalog. Additionally, the diagi is displayed only in cftlog file.</p>
         </td>
      </tr>
      <tr>
         <td>432         </td>
         <td>Duplicate transfer error         </td>
         <td>Check the DUPLICAT parameter value in the CFTSEND or CFTRECV object.         </td>
      </tr>
      <tr>
         <td>433         </td>
         <td>User/password error         </td>
         <td>Check the SPASSWD/RPASSWD parameter values in the CFTSEND or CFTRECV object.         </td>
      </tr>
      <tr>
         <td>434         </td>
         <td>AUTH - File identifier (default IDF) is not authorized           </td>
         <td>
            <p>K status - ABORT</p>
            <p>When cft.default_idf.enable = Yes , the default IDF is not authorized.</p>
         </td>
      </tr>
      <tr>
         <td>435         </td>
         <td>WORKDIR         </td>
         <td>
            <p>The  CFTSEND and CFTRECV models with the same ID have different working directories defined.</p>
            <p>SFTP issue. Check the workingdir value for both the CFTSEND id=&lt;ID&gt; with IMPL=YES and CFTRECV  id=&lt;ID&gt;.</p>
         </td>
      </tr>
      <tr>
         <td>436         </td>
         <td>KEY         </td>
         <td>
            <p>The client key does not correspond to the server key.</p>
            <p>SFTP issue. </p>
            <p>Check the CLIPUBKEY value in the CFTSSH direct=Client setting. This should correspond to an identifier in the local PKI database.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>451</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. PROT - (PeSIT) Reception of a protocol connection 
 refusal (AckCONNECT FPDU). (Odette) Reception of a protocol connection 
 refusal (ESID). <a href="../protocol_diagnostic_codes">DIAGP</a> is then set to RELEASE</p>
            <p>2. PROT - (PeSIT) (Odette) Violation of the protocol 
 specifications (unknown FPDU, or invalid contents for example). DIAGP 
 is then set to ACO in or RCO in ennsnn</p>
            <p>3. PROT - (PeSIT)(Odette) Connection time-out reached 
 without response (DISCTC parameter of the CFTPROT command). DIAGP is then 
 set to TIMEOUT</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RESTART</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>452</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) (Odette) Reception of a negative message 
 confirmation FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>453</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) (Odette) Reception of a negative create 
 confirmation FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>454</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Reception of a negative select confirmation 
 FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>455</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) (Odette) Reception of a negative deselect 
 confirmation FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>456</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Reception of a negative open confirmation 
 FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>457         </td>
         <td>Reception of a negative closed confirmation         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>458         </td>
         <td>Reception of a negative read confirmation         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>459</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Reception of a negative write confirmation 
 FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>460</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Reception of a negative end of transfer 
 confirmation FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>461         </td>
         <td>Received an abort with diagnostics         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>462         </td>
         <td>No data sent on network         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>463         </td>
         <td>Logon entry not recognized         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>499         </td>
         <td>( ODETTE) CD okay         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="3">
            <p>Codes with a value between 001 and 499 indicate a local issue; values 
 between 501 and 999 correspond to a fault reported by the partner.</p>
            <p>Therefore when troubleshooting if the code is greater than 500 it refers to a remote  issue. To find the actual DIAG, subtract 500 from the displayed code. If the DIAG is 916, for example, the issue is a remote  problem corresponding to DIAG 416 (maximum number of transfers reached). </p>
         </td>
      </tr>
      <tr>
         <td>500         </td>
         <td>Constant to add to a remote  code         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>600</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) (Odette) Transfer aborted by the remote  
 end: file input/output error - PeSIT / Odette code: See <a href="../general_protocol_diagnostics">DIAGP.</a></p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status- ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>604</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: file 
 opening error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>605</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: file 
 closing error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>610</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) (Odette) Transfer aborted by the 
 remote  end: the file to be read does not exist</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>611</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: insufficient 
 space to create the file</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>613</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: the 
 file to be created already exists</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>614</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: file 
 space full</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>620</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Transfer aborted by the remote  end: counter 
 control error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>621</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Transfer aborted by the remote  end: interruption 
 by the operator</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>626</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) (Odette) Transfer aborted by the remote  
 end: error in record length</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>635</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>FILE - (PeSIT) Transfer aborted by the remote  end: file 
 access conflict</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td>657         </td>
         <td>Errno         </td>
         <td>Too many open files in the CFTSFTP process.         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>660</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>REC (PeSIT) - Error 660, ASE 
 205 on the requester side</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H state - Transfer aborted by the remote  end: no outstanding 
 transfer</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>720</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. PROT - (PeSIT) Protocol abort by the remote  end: 
 incorrect FPDU (transmission error)</p>
            <p>2. PROT - (Odette) Protocol abort by the remote  end: 
 negotiation error</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>722</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Protocol abort by the remote  end: missing 
 PI</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>730</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>1. PROT - Protocol error</p>
            <p>2. PROT - (PeSIT) Transfer aborted by the remote peer (i.e. the Partner Side) 
 due to protocol error - PeSIT code: See <a href="../general_protocol_diagnostics">DIAGP.</a></p>
            <p>3. PROT - (Odette) Reception of an ESID FPDU</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>740</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>NET - (PeSIT) Transfer aborted by the remote  end: time-out 
 - PeSIT code: 317</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RETRY</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>850</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Protocol rejection by the remote  end: authorization 
 problem</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H Status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>904</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Protocol rejection by the remote  end: transfer 
 denied (open mode, authorizations for example)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>909</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT only) Protocol rejection by the remote  end: 
 requester identifier unknown</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RESTART</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>916</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT only) Maximum number of transfers reached 
 at the partner end (MAXTRANS parameter)</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - NEXT</p>
            <p>See <a href="../../../concepts/about_parallel_transfers/multi_node_simultaneous_transfers">Configure multi-node simultaneous transfers</a>.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>919</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Restart context not available</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>920</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - (PeSIT) Protocol rejection by the remote  end: on 
 reception of a REPLY-type message, the partner does not find the transfer 
 concerned by this reply in its catalog</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>D status - RESTART</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>925</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Call collect refused by the remote  system</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>No CAT</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>928</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Invalid caller number</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>H status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>930</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Partner is inactive on the server side</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>ACT status</p>
         </td>
      </tr>
      <tr>
         <td>933         </td>
         <td>Error in  password management parameter RPASSWD or SPASSWD: non-authorized requester identification         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>963</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Protocol pre-connection phase rejected by the remote  
 end (PeSIT LOGON): LOGON string rejected</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT, EXECE</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>970</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>PROT - Protocol pre-connection phase rejected by the remote  
 end (PeSIT LOGON): password expired</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>K status - ABORT, EXECE</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="SSL"></span>SSL alert errors

<table>
   <col/>
   <tbody>
      <tr>
         <td>
            <p>H status - ABORT, EXECE in requester mode</p>
            <p>If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information.</p>
         </td>
      </tr>
   </tbody>
</table>
