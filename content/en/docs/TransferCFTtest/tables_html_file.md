


============================== table nb count(1) ============================================


| Parameter  | Description  |
| --- | --- |
| [CONTENT = BRIEF ùùù_insert_pipe_here_ùùù FULL ùùù_insert_pipe_here_ùùù DEBUG ] | Result display mode.<br/> • FULL: All contents display<br/> • DEBUG: All contents and additional general information display<br/> • BRIEF: a 79-character entry is displayed for each certificate. Additionally, when using the BRIEF value to display content:<br/> • Items display showing a clear parent/child relationship<br/> • If a certificate is marked as **Expired** (!), all of its children are labeled **Parent expired** (?)<br/> • If a certificate's parent is missing, the line displays either a question mark (**?**) if the issuer is filtered, or an exclamation mark (**!**) if the issuer is missing<br/> The <a href="#FMODEL%C2%A0d">FMODEL display example</a> features these elements.<br/> |
| [ID = {*, string1..8}] | Unique local identifier of the certificate(s) to be displayed.<br/> The * and ? wildcard characters are accepted for the ID parameter value. |
| [ INUM = {number0...99} ]  | Internal number for the intermediate certificates in an imported chain of certificates (in the PKI database).<br/> You can use this option to select a specific intermediate certificate. |
| [TYPE = ALL ùùù_insert_pipe_here_ùùù USER ùùù_insert_pipe_here_ùùù ROOT ùùù_insert_pipe_here_ùùù INTER ùùù_insert_pipe_here_ùùù KEY ùùù_insert_pipe_here_ùùù CERT ùùù_insert_pipe_here_ùùù ùùù_insert_pipe_here_ùùù ENTITY ] | Type of certificate to display:<br/> • ALL: all certificates<br/> • USER: user certificates<br/> • ROOT: root authority certificates<br/> • INTER: intermediate authority certificates<br/> • KEY: list PKIKEY items<br/> • CERT: list ROOT, INTER, and USER certificates for PKICER only<br/> • ENTITY: any entity identifier created using PKIENTITY command |
| [STATE = ALL ùùù_insert_pipe_here_ùùù ACT ùùù_insert_pipe_here_ùùù INACT ùùù_insert_pipe_here_ùùù EXPIRED] | Status of the certificates to display:<br/> • ALL: all statuses<br/> • ACT: all activated certificates<br/> • INACT: all deactivated certificates<br/> • EXPIRED: all expired certificates |
| FMODEL | The path to the file containing the models. If no model is found, the default format, which is the same as for the DISPLAY command, is used.<br/> <blockquote> **Note**<br/> Note: Transfer CFT 3.7 and higher uses the dspcnf.xml model fileby default. To have the display format from a previous version, use FMODEL=NONE.<br/> </blockquote>  |
| ROOTCID  | The certificate authority ID. See an example in ROOTCID.  |
| HELP  | Provides helps for the available fields for the different elements, or lists the available MODELS for the given file. Values include:<br/> • NONE (default)<br/> • FIELDS<br/> • MODELS |



============================== table nb count(2) ============================================


| Authentication method  | copilot.restapi.authentication_method  | Details  |
| --- | --- | --- |
| Operating System  | system  | The user/password is checked against the operating system.<br/> <blockquote> **Note**<br/> Note: We strongly recommend that you set copilot.misc.createprocessasuser=yes when using the system option.<br/> </blockquote> **Unix**<br/> You must use <code>cftsu </code>to create users as a superuser is required (sudo or root privilege) to create a group and assign a user to a group. Refer to Using system users UNIX for details.<br/> • Create a group &quot;group1&quot;: groupadd group1<br/> • Add user &quot;user1&quot; to group &quot;group1&quot;: usermod -a -G group1 user1<br/> **Windows**<br/> You require a superuser (administrative user account) to create a group and assign a user to a group.<br/> • Create a group &quot;group1&quot;: net localgroup group1 /add<br/> • Add user &quot;user1&quot; to group &quot;group1&quot;: net localgroup group1 user1 /add<br/> <blockquote> **Note**<br/> Note: For a user belonging to a domain, use: domain\user1 instead of user1<br/> </blockquote>  |
| Access Management  | am  | This methods uses an indirection towards the Access Management system. The user/password is checked by the configured access management system: {{&lt; TransferCFTtest/suitevariablesFlowManager &gt;}}, PassPort AM, or internal AM. |
| xfbadm database<br/> (UNIX and HP NonStop exclusively) | xfbadm  | The user/password is checked using the xfbadm base (see the <a href="../use_cft_utilities">xfbadmusr and xfbadmgrp utilities</a>).<br/> A user that can execute xfbadmusr/xfbadmgrp utilities can create users and groups after executing the <code>profile </code>from the runtime directory.<br/> • Create a group &quot;group1&quot; with gid=200: xfbadmgrp add -G group1 -p group1_pw -g 200<br/> • From the user prompt, to add a user &quot;user1&quot; to group &quot;group1&quot;enter: xfbadmusr add -l user1 -p user1_pw -u AUTO -g 200 |



============================== table nb count(3) ============================================


| DIAGI Code  | Event  | Consequence  |
| --- | --- | --- |
| 0 | The transfer has terminated correctly | Execution of normal EXECRF or EXECSF end of transfer procedures |
| 001 | SYS: Error creating the message queue or allocating the memory | H status - ABORT, EXECE |
| 002 | Context definition error | H status - ABORT, EXECE |
| 003 | SYS - Context allocation error | H status - ABORT, EXECE |
| 004  | MQCONN  |   |
| 005  | MQOPEN  |   |
| 006  | MQPUT  |   |
| 100 | FILE - File input/output error | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 101 | FILE - Error creating the receive file | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 102 | 1.FILE - Error allocating the transfer file<br/>  | H status - ABORT, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 102  | 2.FILE - The receive file cannot be allocated (FDISP=OLD case) | H status - ABORT, EXECE<br /> The file is deleted.<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 103 | 1.FILE - The file cannot be deleted before the receive file is created (FDISP = DELETE case) | H status - ABORT, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 103  | 2.FILE - Error deleting the sent file, if a deletion has been requested (FACTION = DELETE) | H status - ABORT, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 104 | 1. FILE - Error opening the transfer file<br/> 2. FILE - The receive file cannot be erased (FDISP = ERASE case): file opening problem<br/> 3. FILE - Prior to reception, the receive file could not be opened to check that it was empty (FDISP = VERIFY case) | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 105 | 1. FILE - Error closing the transfer file<br/> 2. FILE - The receive file cannot be erased (FDISP = ERASE case: file closing problem<br/> 3. FILE - Prior to reception, the receive file could not be closed after checking that it was empty (FDISP = VERIFY case)<br/> 4. FILE - The sent file cannot be deleted following an erase request (FACTION = ERASE case) | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 106 | FILE - Error recording the current position in the transfer file (synchronization point setting) | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 107 | FILE - Error setting the pointer to a re-synchronization point in the file (for a transfer restart) | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 108 | 1. FILE - Send file read error in data transfer phase<br/> 2. FILE - Prior to reception, the receive file could not be read to check that it was empty (FDISP = VERIFY case) | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 109 | FILE - Data write error in the receive file | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 110 | 1. FILE - The send file does not exist<br/> 2. FILE - The receive file to be created does not exist, even though the FDISP parameter requires it (FDISP=OLD). DIAGP is then set to NO OLD | H status - ABORT, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 111 | FILE - Insufficient space to create the file | H status - ABORT in requester mode, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 112  | Nonexistent unit  |   |
| 113 | FILE - The file to be created already exists, even though the FDISP parameter prohibits it (FDISP = NEW). DIAGP is then set to NO NEW | H status - ABORT, EXECE in requester mode<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 114 | FILE - Data write error in the receive file: file space full | H status - ABORT, EXECE<br/> If there is a DIAGP for this, it is system specific. For these errors, check the DIAGC or the log for more information. |
| 115 | 1. FILE - The transfer owner is not authorized to access the file<br/> 2. FILE - The file cannot be deleted before the receive file has been created (FDISP = DELETE case)Protected file | H status - ABORT, EXECE in requester mode<br/> Please see the Access management sections for more information. |
| -&quot;-  | 3. FILE - The sent file cannot be deleted following a deletion request<br/> (FACTION = DELETE case) Protected file | H status - ABORT, EXECE<br/> Please see the Access management sections for more information. |
| 120 | PROT - Counter check error | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 121 | USER - Interruption by the operator | H status - ABORT, EXECE |
| 122 | SYS - Error allocating memory when the transfer is executed | D status - RESTART |
| 123 | FILE - Error setting the pointer to a resynchronization point in the file: the restart point requested by the partner is incorrect.<br/> This can occur when the synchronized points are not flushed from the catalog (if the CFTCAT's <code>updat </code>parameter is greater than 1, the UCONF<code>cft.server.catalog.sync.enable</code> is set to <code>No</code>, or both of these are true) due to an unexpected event such as a process, system, or disk crash.<br/> <br/> You should set the following values to ensure that a restart is possible:<br/> <code>cft.server.catalog.sync.enable = Yes</code><br/> <code>CFTCAT id=xxxx,updat=1</code><br/> <code>CFTPROT id=xxx, schkw=1,rchkw=1</code> | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 124 | PROT - Error: transfer aborted | H status - ABORT, EXECE<br/> {{% TransferCFTtest/snippets/trace_needed%}}  |
| 126 | FILE - LRECL error (record length) | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 127 | FILE - The receive file is not empty (FDISP = VERIFY case) | H status - ABORT, EXECE |
| 128 | 1. FILE - Error deselecting the file<br/> 2. FILE - Error deselecting the receive file | H status - ABORT, EXECE<br/> H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| - &quot; -  | 3. FILE - Error accessing the send file (allocating or opening), subsequent to a file erase request (FACTION = ERASE) | H status - ABORT, EXECE unless there is an allocation error in sender server mode<br/> This may require a trace. Please see How to use ATM traces. |
| 129 | FILE - Error during file decompression | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 130 | FILE - Error during file compression | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 131 | PROT - IDF different on ODETTE SELECT | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 132 | PARAM - Error accessing the parameter setting indirection file (list of files, list of partners) | K status - ABORT<br/> If the file does not exist, no transfer is executed. Only the generic request remains in the catalog. If an error occurs while reading the indirection file, the transfers generated for the items (files or partners) that have already been read are executed |
| 133 | PARAM - The FOR parameter in the CFTDEST command is invalid<br/> 1. FOR=LOCAL when in the switching mode<br/> 2. FOR=COMMUT when not in the switching mode | No catalog entry. Check the CFTDEST object in the configuration. |
| 134 | FILE - CFTEXIT call error | H status - ABORT, EXECE<br/> Check the information in the cftlog and the cft.out files. |
| 135 | 1. FILE - The send file is locked<br/>  |  • D status - RESTART<br /> Check that the file is not locked by another process.<br/><br/> • H status - ABORT, EXECE<br /> Check that the file is not locked by another process.<br/> |
| - &quot; -  | 2. FILE - The receive file is locked |  • D status - RESTART<br /> Check that the file is not locked by another process.<br/><br/> • H status - ABORT, EXECE<br /> Check that the file is not locked by another process.=<br/> |
| 136 | FILE - Duplication of the temporary file | H status - ABORT, EXECE<br/> Check the WFNAME parameter in the CFTSEND or CFTRECV command. |
| 137 | FILE - The file exists, the &quot;rename&quot; operation is therefore impossible | H status - ABORT, EXECE<br/> Check the WFNAME parameter in the CFTSEND or CFTRECV command. |
| 138 | 1. FILE - No temporary file has been defined in the send mode and the transfer requires the COPY mechanism. No transfer is triggered and the generic request remains in the catalog | State K - ABORT<br/> Check the WFNAME parameter in the CFTSEND or CFTRECV command.<br/> <br/> Check the WFNAME parameter in the CFTSEND or CFTRECV command.<br/>  |
| - &quot; -  | 2. FILE - No temporary file has been defined in the receive mode for a file with versions or for a transfer requiring deconcatenation (COPY) | State K - ABORT, EXECE<br/> Check the WFNAME parameter in the CFTSEND or CFTRECV command.<br/>  |
| 139  | Incorrect attributes file  | Check the cftlog file and the diagp/diagc in the catalog record.<br/> Also, check the FLRECL/FRECFM parameters in the CFTRECV object. |
| 142 | FILE - The &quot;rename&quot; operation failed | H status - ABORT, EXECE<br/> Check the WFNAME parameter in the CFTRECV command. |
| 144 | MVS transfer busy | State D - Retry<br/> Specific to z/OS environments. |
| 145  |  • The SEND file is outside of the workingdir tree. &lt;/li&gt;<br/> • The temporary SEND file is outside of the workingdir tree. | K status - ABORT<br/> Check the WORKINGDIR parameter in the CFTSEND object. |
| 148  | 1. The RECV file is outside of the workingdir tree. &lt;/p&gt;<br/> 2. The temporary RECV file is outside of the workingdir tree. | K status - ABORT<br/> Check the WORKINGDIR parameter in the CFTRECV object. |
| 150 | PARAM - Could not access a file. This error may be due to one of several issues, for example the directory is empty, or the file's name does not correspond to an applied filter. | State K - ABORT. If the directory does not exist, no transfers are triggered and only the generic request remains in the catalog. If an error is detected when reading the directory, the transfers generated for the items (directory menus) that have already been read are triggered. |
| 152 | FILE - Error during the concatenation phase at the start of the transfer or during the de-concatenation phase at the send of the transfer. | State H - ABORT, EXECE<br/> Problem on homogeneous transfer issue. See Sending a group of files.<br/> Check the configuration - FNAME and WFNAME on the CFTSEND or CFTRECV object. |
| 153 | FILE - Error during the transfer. The file has been overwritten. | State K - Short transfer cannot be restarted. |
| 154  | An error occurred when trying to transcode a file using NCHARSET parameter in the CFTSEND command before a send.  | Generates a DIAGI=730, DIAGP=ABO 399 on the remote side as the sender cannot transcode before sending.<br/> Check the diagp/diagc in the catalog to have more information. |
| 155  | This preprocessing error occurs when a preexec is specified, but launching the exec file failed (usually because the file was not found, but could be due to a busy or migrated file on z/OS [MVS]).  | Generates:<br/> • DIAGP: NO EXEC<br/> • DIAGC: PREEXEC LAUNCH ERROR<br/> Check the PREEXEC parameter in the SEND, RECV, CFTSEND, and CFTRECV commands. |
| 156  | This error occurs if the maximum number of retries is reached when FACTION=RETRYRENAME.  | Generates:<br/> • DIAGP: RETRYRENAME<br/> • Phasestep=K<br/> Check these uconf values:<br/> • cft.server.transfer.rrename.retry_delay<br/> • cft.server.transfer.rrename.max_retries<br/> File defined in the FNAME parameter in the CFTRECV object should not exist when the retry occurs. Transfer can be restarted. |
| 158  | There was an error while replacing Transfer CFT variables.<br/> The script referenced by <code>&amp;fname</code> in the CFTS68E message is not executed. | In the script &amp;fname, modify the variable &lt;var&gt; indicated in the CFTS68E message.  |
| 160 | Handles the event 'no outstanding transfer or implicit declaration'. | No catalog entry is created. |
| 200  | An error occurred on a child transfer of this parent (generic) transfer. Refer to the child transfer in error for more information.  | State K - ABORT,EXECE  |
| 203  | PROF=SIT non-priority transfer  |   |
| 220 | PROT - FPDU reception | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 221 | PROT - Int/ext type match error: the type of a PI is not consistent with its conversion type in the external format (for example, a PI in DATE format to be converted to the STRING format) | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 222 | PROT - Mandatory PI missing in FPDU | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 223 | PROT - Invalid PI length | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 224 | PROT - Invalid PGI length | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 225 | PROT - PGI missing from the FPDU | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 226 | PROT - PGI embedded in another PGI | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 230 | PROT - Protocol error. A protocol error has been detected: DIAGP is set to the PeSIT or ODETTE code of the error detected | H status - ABORT, EXECE<br/> Contact the Support team for this type of unexpected error. Prior to doing so though, please collect as much information as possible regarding the transfer in error, including the remote partner information (product, configuration,...).<br/> Note that the 230 diagnostic codes may have different diagnostic protocols formats:<br/> • diagp = eEEsSS: An unexpected internal error when the event &quot;EE&quot; occurs during the &quot;SS&quot; state.<br/> • diagp = PDU iNN: The PDU parameter &quot;NN&quot; is not correct. |
| 231 | PROT - Invalid action | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 232 | PROT - Event not found. An interaction not recognized by the protocol mechanisms has been received in a given transfer context | H status - ABORT, EXECE<br/> This may require a trace. Please see How to use ATM traces. |
| 233  | PROT - Message send operation refused by the protocol used. The following protocols do not support message send operations: PESIT SIT, PESIT EXT, ODETTE | K status - ABORT<br/> This may require a trace. Please see How to use ATM traces. |
| 240 | PROT - Time-out expired (RTO parameter) | D status - RETRY/COMMUT<br/> For more information, see Troubleshoot 240 or 740 RTO. |
| 241  | Transfer time-out - requester  |   |
| 241  | Transfer time-out - server  |   |
| 243  | Network connection time-out  |   |
| 244  | Pre-connection time-out  |   |
| 260 | SSL - Security problem | K state - ABORT<br/> DIAGP=PKI with I, E or S nnn<br/> nnn = SSL code alert<br/> See <a href="#SSL">SSL alert errors</a> and Troubleshoot security errors. |
| 261 | SSL - Error linked to an internal PKI | K state - ABORT<br/> DIAGP=PKI I nnn<br/> nnn = SSL code alert<br/> See <a href="#SSL">SSL alert errors</a> and Troubleshoot security errors. |
| 262 | SSL - Error linked to the PKI system | K state - ABORT<br/> DIAGP=PKIS nnn<br/> nnn = SSL code alert<br/> See <a href="#SSL">SSL alert errors</a> and Troubleshoot security errors. |
| 263 | SSL - Error linked to an external PKI | K state - ABORT<br/> DIAGP=PKIE nnn<br/> nnn = SSL code alert<br/> See <a href="#SSL">SSL alert errors</a> and Troubleshoot security errors. |
| 278 | SSL - Invalid security profile | K state - ABORT |
| 301 | NET - Network addressing error (IP address) at the time of connection | D status - COMMUT<br/> The transfer will be retried for a minimum period equal to the WSCAN parameter of the CFTCAT command. The next partner address in the HOST parameter list (CFTTCP command) will be used for the next retry.<br/> • If the invalid address is the last one in the list, the next protocol in the PROT parameter list (CFTPART command) will be used for the next retry.<br/> • If the protocol used is the last in the list, the transfer is either switched to the backup partner (IPART parameter of the CFTPART command) or aborted (K status) with code 405, while maintaining the diagnostic code of the last retry |
| 302 | NET - Network link broken (cut-off, time-out) outside the connection phase. DIAGP is then set to VNRELI | D status - RETRY/COMMUT<br/> Up to &quot;RETRYM&quot; retries are performed for the transfer and the access data. If the number of retries reaches the value in the RETRYM parameter, {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} switches the access data.<br/> The partner access data for the next retry will relate to the next HOST parameter (CFTNET command), or the next PROT parameter (CFTPART command). The restart counter is reset to 0.<br/> If the protocol used is the last in the list, the transfer is either switched to the backup partner (IPART parameter of the CFTPART command) or aborted with code 405, while maintaining the diagnostic code (DIAGP) of the last retry<br/> See Common transfer issues for more information. |
| 303 | NET - Network parameter error at the time of connection | D status - COMMUT<br/> The transfer is retried using the next protocol in the PROT parameter list (CFTPART command) as the new partner access point.<br/> If the protocol used is the last in the list, the transfer is either switched to the backup partner (IPART parameter of the CFTPART command) or aborted (K status) with code 405, while maintaining the diagnostic code of the last retry.<br/> Cannot connect to the remote partner due to a local connection rejection. When using SFTP, check that the remote SAP value in CFTPART object is defined and is correct. |
| 350 | The user requesting the transfer is not authorized to perform it | State H |
| 351 | The remote requester is not authorized to use the transfer. The transfer was in the H state. The monitor is running in the server/sender mode | State H |
| 352 | The remote requester is not authorized to create a transfer. The monitor is running in the server/sender mode and the transfer was to be created via a CFTSEND IMPL=YES | State H |
| 401 | PARAM - Embedded broadcast list explicitly refused | K status - ABORT<br/> For an explicit multi-partner request (PART parameter in the CFTDEST command), a single partner, itself defined as a partner list, aborts the request; only the generic list request set to the K status remains in the catalog. No transfer is executed.<br/> For a multi-partner request via an indirection file (FNAME parameter in the CFTDEST command), only the requests prior to the error are executed |
| 402 | PARAM - The PROT parameter of the CFTPART command does not belong to the active protocol list (PROT parameter of the CFTPARM command) | K status - ABORT |
| 403 | PARAM: Invalid password | No CAT<br/> The diagi = 403 is displayed only in the cftlog file<br/> CFTH22E NPART=PARTSSL rejected DIAGI=403 &lt;HOST=@IP_address&gt;<br/> On the requester the transfer status is D with diagi = 909 and the diagp = RCO 301, therefore the transfer is retried up to RETRYM times.<br/>  |
| 404 | PARAM: Open mode not authorized | No CAT (in server mode)<br/> Check that the FNAME=&amp;NFNAME in the CFTSEND or CFTRECV object. |
| 405 | OUT: Transfer CFT has tried all possible partner access points: HOST, PROT, IPART | K status - ABORT, EXECE<br/> Check the configuration of the CFTPART and CFTTCP objects.<br/> Before reaching 405 diagi, multiple retries were executed. Check the cftlog file for informtion related to this transfer.<br/> After correcting the transfer, you can restart the transfer. |
| 406 | 1. OUT - Maximum number of retries reached (RESTART parameter).<br/> DIAGP is set to MAXRST<br/> 2. AUTH - The required start time for execution of the transfer is outside the authorized time slot (OMINTIME / OMAXTIME); there is no other possible protocol for this partner. DIAGP is set to CALL OUT<br/> 3. AUTH - The network resource associated with the protocol does not accept outgoing calls; there is no other possible protocol for this partner<br/> DIAGP is set to L 0B 022<br/> 4. PARAM - There is no CFTN command for the partner and for the last protocol in the list (CFTPART PROT parameter). DIAGP is set to MAXRST<br/> 5. OVER - Transfer CFT has reached the limit (RESTART parameter) of authorized retries for the last partner protocol (CFTPART PROT parameter). DIAGP is set to MAXRST<br/> 6. PARAM - The SROUT parameter of the protocol cannot be used to execute the transfer; there is no other possible protocol for this partner. DIAGP is set to SROUT |  <br/> <br/> K status - ABORT, EXECE<br/> <br/> <br/>  |
| 408 | PARAM - PART parameter not described by a CFTPART command | K status - ABORT<br/> If a single CFTPART command is missing from an explicit multi-partner request (PART parameter in the CFTDEST command), the request is aborted. Only the generic list request, set to the K status, remains in the catalog.<br/> No transfer is executed.<br/> For a multi-partner request via an indirection file (FNAME parameter in the CFTDEST command), only transfers with no partner defined are halted<br/> The other transfers are executed<br/> Complete broadcasting (or collection) is unsuccessful without operator intervention (partner definition and transfer retry). The end of transfer procedure is not executed.  |
| 409 | PARAM - Unknown NPART parameter | H status - ABORT<br/> Check the correspondence between the PROT, NSPART, and NRPART parameters in the CFTPART object. |
| 410 | PARAM - Unknown CFTPROT command | K status - ABORT<br/> Check that the PROT value in the CFTPART matches an active protocol PROT parameter of CFTPARM object. |
| 411 | AUTH - File identifier (IDF) not authorized | K status - ABORT<br/> If the IDF for one of the partners in an explicit multi-partner request (PART parameter in the CFTDEST command) is not authorized, the request is aborted; only the generic list request set to the K status remains in the catalog<br/> No transfer is executed<br/> For a multi-partner request via an indirection file (FNAME parameter in the CFTDEST command), only transfers, the IDFs of which are not authorized for the partner (CFTAUTH command) are set to halted<br/> The other transfers remain active.<br/> However, complete broadcasting (or collection) is unsuccessful without operator intervention (grant authorization to the partners and retry the transfer); the end of transfer procedure will not be executed |
| 412 | DATA - Catalog access error | As the file could not be accessed, there is no change in the status or in the catalog DIAGI.<br/> The CFTT21E should display in the log and contain GCS and GCR information that may be helpful for Axway support to diagnos the issue.<br/> For example, this type of error could be caused by a corrupted catalog. If so, you could import and export the records to repair this. |
| 413 | AUTH - File identifier not authorized | H status - ABORT<br/> Check the SAUTH/RAUTH parameters in the CFTPART object and the associated CFTAUTH objects. |
| 414 | 1. AUTH - The start time for execution of the transfer is outside the authorized time slot (MAXTIME / MAXDATE of the SEND / RECV command)<br/> DIAGP is then set to OUT TIME<br/> 2. PARAM - The outgoing time slot of the partner is null (OMINTIME / OMAXTIME)<br/> There is no intermediate partner<br/> DIAGP is then set to CALL OUT<br/> 3. AUTH - No outgoing call authorized for the network resource (CFTnetwork CNXOUT=0)<br/> DIAGP is then set to NO CALL | K status - ABORT<br/> See CFTNET - Network resources and Network resources for more information on network resource depletion prevention. |
| 415 | OVER - Maximum number of partners reached | D status - NEXT |
| 416 | 1. OVER - Maximum number of transfers reached (MAXTRANS parameter)<br/> The transfer cannot be executed<br/> DIAGP is then set to MAXTRANS | D status - NEXT<br/> <br/> Please see Network resource depletion prevention (NRDP). |
| - &quot; -  | 2. OVER - Maximum number of connections reached for the network resource<br/> The transfer cannot be executed<br/> DIAGP is then set to MAXCNX | D status - NEXT<br/> This status corresponds to a transfer refusal by the {{&lt; TransferCFTtest/axwayvariablesComponentLongName &gt;}} protocol task, even though the scheduler has not reached the MAXTRANS limit.<br/> This occurs when the protocol task maintains active connections after transfers have ended. Please see Network resource depletion prevention (NRDP).<br/> <br/> WSCAN related behavior<br/> Technically, the next retry is triggered **wscan** minutes after the previous try. However, sometimes you may have a {{&lt; TransferCFTtest/axwayvariablesComponentLongName &gt;}} log where the 416 diagnostic codes are not evenly distributed (by the same time intervals). This may occur if the scheduling task believes resources are available and schedules a retry, but in reality the resource is taken.<br/> <br/> *Unix only* - If the runtime path is too long, a diag 416 issue occurs and a message similar to the following displays in the <code>cft.out</code>:<br/> <blockquote> <code>CFTTCPS S_socket : start_soc : bind afunix</code><br/> <code>CFTTCPS Invalid argument</code><br/> </blockquote> If this error occurs, modify the path to the socket in the UCONF <code>cft.unix.stcp.afunix</code> parameter according to the operating system limit as shown below:<br/> • AIX: 1023<br/> • HP-UX: 92<br/> • Linux: 108<br/> • Solaris: 108 |
| 417 | 1. OVER - Maximum number of file tasks reached (MAXTASK parameter)<br/> The transfer cannot be executed<br/> 2. SYS- Insufficient system resources available to execute an EXIT task<br/> The transfer cannot be executed | D status - NEXT |
| 418 | OVER - The total number of transfers in progress exceeds one of the CNXIN, CNXOUT or CNXINOUT parameters for the partner<br/> The transfer cannot be executed | D status - RESTART<br/> If the number of retries exceeds the value of the RESTART parameter (CFTPROT command), Transfer CFT switches to the access data of the next protocol for this partner. See Active/active mulit-node tuning.<br/> See also, Frequently asked questions and Configure multi-node simultaneous transfers. |
| 419 | DATA - The transfer to be retried is not in the catalog at the server end | ABORT<br/> Check the information in the cftlog file. |
| 420 | DATA - On reception of a REPLY-type message, the original transfer concerned by this reply is not found in the catalog at the server end | ABORT |
| 421 | 1. SYS - Error executing a {{&lt; TransferCFTtest/suitevariablesTransferCFTName &gt;}}file task | D status - NEXT |
| - &quot; -  | 2. SYS - Error executing a {{&lt; TransferCFTtest/suitevariablesTransferCFTName &gt;}} EXIT task | K status - ABORT |
| 423 | SYS or PARAM - EXIT task creation error | H status - ABORT<br/> Check the diagp and the cftlog file for more information on the context. |
| 424 | PARAM - CFTXLATE command not found for this transfer direction and the source and target alphabets | H status - ABORT<br/> Check the XLATE value in the CFTSEND/CFTRECV object and the associated CFTXLATE object. |
| 426 | USER (Directory Exit) - Error in the Directory Exit task | No CAT (server mode)<br/> State K - ABORT (requester mode) |
| 428  | Incoming address verified by the VERIFY parameter in the CFTTCP object was not accepted.  | No CAT<br/> Check the incoming address in the cftlog file and compare it to the host value in the CFTTCP object; the check is done on the VERIFY value (in terms of digits). |
| 430 | PARAM - Transfer is inactive on the requester side | State D - ACT<br/> Check the partner's state. |
| 431 | USER (Security) - CFTAPPL card is absent | No CAT<br/> Transfer is not started and there is no entry in the catalog. Additionally, the diagi is displayed only in cftlog file. |
| 432  | Duplicate transfer error  | Check the DUPLICAT parameter value in the CFTSEND or CFTRECV object.  |
| 433  | User/password error  | Check the SPASSWD/RPASSWD parameter values in the CFTSEND or CFTRECV object.  |
| 434  | AUTH - File identifier (default IDF) is not authorized  | K status - ABORT<br/> When cft.default_idf.enable = Yes , the default IDF is not authorized. |
| 435  | WORKDIR  | The CFTSEND and CFTRECV models with the same ID have different working directories defined.<br/> SFTP issue. Check the workingdir value for both the CFTSEND id=&lt;ID&gt; with IMPL=YES and CFTRECV id=&lt;ID&gt;. |
| 436  | KEY  | The client key does not correspond to the server key.<br/> SFTP issue.<br/> Check the CLIPUBKEY value in the CFTSSH direct=Client setting. This should correspond to an identifier in the local PKI database. |
| 451 | 1. PROT - (PeSIT) Reception of a protocol connection refusal (AckCONNECT FPDU). (Odette) Reception of a protocol connection refusal (ESID). DIAGP is then set to RELEASE<br/> 2. PROT - (PeSIT) (Odette) Violation of the protocol specifications (unknown FPDU, or invalid contents for example). DIAGP is then set to ACO in or RCO in ennsnn<br/> 3. PROT - (PeSIT)(Odette) Connection time-out reached without response (DISCTC parameter of the CFTPROT command). DIAGP is then set to TIMEOUT | D status - RESTART |
| 452 | PROT - (PeSIT) (Odette) Reception of a negative message confirmation FPDU | H status - ABORT, EXECE |
| 453 | PROT - (PeSIT) (Odette) Reception of a negative create confirmation FPDU | H status - ABORT, EXECE |
| 454 | PROT - (PeSIT) Reception of a negative select confirmation FPDU | H status - ABORT, EXECE |
| 455 | PROT - (PeSIT) (Odette) Reception of a negative deselect confirmation FPDU | H status - ABORT, EXECE |
| 456 | PROT - (PeSIT) Reception of a negative open confirmation FPDU | H status - ABORT, EXECE |
| 457  | Reception of a negative closed confirmation  |   |
| 458  | Reception of a negative read confirmation  |   |
| 459 | PROT - (PeSIT) Reception of a negative write confirmation FPDU | H status - ABORT, EXECE |
| 460 | PROT - (PeSIT) Reception of a negative end of transfer confirmation FPDU | H status - ABORT, EXECE |
| 461  | Received an abort with diagnostics  |   |
| 462  | No data sent on network  |   |
| 463  | Logon entry not recognized  |   |
| 499  | ( ODETTE) CD okay  |   |



============================== table nb count(4) ============================================


| 500  | Constant to add to a remote code  |   |
| --- | --- | --- |
| 600 | FILE - (PeSIT) (Odette) Transfer aborted by the remote end: file input/output error - PeSIT / Odette code: See DIAGP. | H status- ABORT, EXECE |
| 604 | FILE - (PeSIT) Transfer aborted by the remote end: file opening error | H status - ABORT, EXECE |
| 605 | FILE - (PeSIT) Transfer aborted by the remote end: file closing error | H status - ABORT, EXECE |
| 610 | FILE - (PeSIT) (Odette) Transfer aborted by the remote end: the file to be read does not exist | H status - ABORT, EXECE |
| 611 | FILE - (PeSIT) Transfer aborted by the remote end: insufficient space to create the file | H status - ABORT, EXECE |
| 613 | FILE - (PeSIT) Transfer aborted by the remote end: the file to be created already exists | H status - ABORT, EXECE |
| 614 | FILE - (PeSIT) Transfer aborted by the remote end: file space full | H status - ABORT, EXECE |
| 620 | PROT - (PeSIT) Transfer aborted by the remote end: counter control error | H status - ABORT, EXECE |
| 621 | PROT - (PeSIT) Transfer aborted by the remote end: interruption by the operator | H status - ABORT, EXECE |
| 626 | PROT - (PeSIT) (Odette) Transfer aborted by the remote end: error in record length | H status - ABORT, EXECE |
| 635 | FILE - (PeSIT) Transfer aborted by the remote end: file access conflict | H status - ABORT, EXECE |
| 657  | Errno  | Too many open files in the CFTSFTP process.  |
| 660 | REC (PeSIT) - Error 660, ASE 205 on the requester side | H state - Transfer aborted by the remote end: no outstanding transfer |
| 720 | 1. PROT - (PeSIT) Protocol abort by the remote end: incorrect FPDU (transmission error)<br/> 2. PROT - (Odette) Protocol abort by the remote end: negotiation error | H status - ABORT, EXECE |
| 722 | PROT - (PeSIT) Protocol abort by the remote end: missing PI | H status - ABORT, EXECE |
| 730 | 1. PROT - Protocol error<br/> 2. PROT - (PeSIT) Transfer aborted by the remote peer (i.e. the Partner Side) due to protocol error - PeSIT code: See DIAGP.<br/> 3. PROT - (Odette) Reception of an ESID FPDU | H status - ABORT, EXECE |
| 740 | NET - (PeSIT) Transfer aborted by the remote end: time-out - PeSIT code: 317 | D status - RETRY |
| 850 | PROT - (PeSIT) Protocol rejection by the remote end: authorization problem | H Status - ABORT, EXECE |
| 904 | PROT - (PeSIT) Protocol rejection by the remote end: transfer denied (open mode, authorizations for example) | H status - ABORT, EXECE |
| 909 | PROT - (PeSIT only) Protocol rejection by the remote end: requester identifier unknown | D status - RESTART |
| 916 | PROT - (PeSIT only) Maximum number of transfers reached at the partner end (MAXTRANS parameter) | D status - NEXT<br/> See Active/active mulit-node tuning. |
| 919 | Restart context not available | H status - ABORT, EXECE |
| 920 | PROT - (PeSIT) Protocol rejection by the remote end: on reception of a REPLY-type message, the partner does not find the transfer concerned by this reply in its catalog | D status - RESTART |
| 925 | Call collect refused by the remote system | No CAT |
| 928 | Invalid caller number | H status - ABORT, EXECE |
| 930 | PROT - Partner is inactive on the server side | ACT status |
| 933  | Error in password management parameter RPASSWD or SPASSWD: non-authorized requester identification  |   |
| 963 | PROT - Protocol pre-connection phase rejected by the remote end (PeSIT LOGON): LOGON string rejected | K status - ABORT, EXECE |
| 970 | PROT - Protocol pre-connection phase rejected by the remote end (PeSIT LOGON): password expired | K status - ABORT, EXECE |



============================== table nb count(5) ============================================


| Code | Description |
| --- | --- |
| 0 | Close notify |
| 10 | Unexpected message |
| 20 | Bad record MAC |
| 21 | Decryption failed |
| 22 | Record overflow |
| 30 | Decompression failure |
| 40 | Handshake failure |
| 41 | No certificate |
| 42 | Bad certificate |
| 43 | Unsupported certificate |
| 44 | Certificate revoked |
| 45 | Certificate expired |
| 46 | Certificate unknown |
| 47 | Illegal parameter |
| 48 | Unknown CA (<a href="http://en.wikipedia.org/wiki/Certificate_authority">Certificate authority</a>) |
| 49 | Access denied |
| 50 | Decode error |
| 51 | Decrypt error |
| 60 | Export restriction |
| 70 | Protocol version |
| 71 | Insufficient security |
| 80 | Internal error |
| 90 | User canceled |
| 100 | No renegotiation |
| 110 | Unsupported extension |
| 111 | Certificate unobtainable |
| 112 | Certificate unobtainable |
| 113 | Bad certificate status response |
| 114 | Bad certificate hash value |



============================== table nb count(6) ============================================


| Function  | Windows  | UNIX  | z/OS  | IBM i  | HP NS  | OpenVMS  |
| --- | --- | --- | --- | --- | --- | --- |
| should we add Azure Blob?  |   |   |   |   |   |   |
| should we add Am S3?  |   |   |   |   |   |   |
| Google Cloud storage  | 3.9  | 3.8  | -  | -  | -  | -  |
| Flow Manager  | 3.3.2  | 3.3.2  | 3.3.2  | 3.3.2  | 3.3.2  | -  |
| Flow Manager SaaS  | 3.6  | 3.6  | 3.6  | 3.6  | 3.6  | -  |
| Using tracking with<br/> Edge Agent | 3.5  | 3.5  | 3.5  | 3.5  | 3.5  | 3.5  |
| SAML  | 3.5  | 3.5  | 3.6  | 3.6 SP1  | 3.5  | -  |
| REST API  | 3.2.4  | 3.2.4  | 3.2.4  | 3.2.4  | 3.2.4  | 3.9  |
| Browser-based user interface  | 3.3.2  | 3.3.2  | 3.3.2  | 3.3.2  | 3.3.2  | 3.9  |
| Central Governance  | 3.1.3  | 3.1.3  | 3.1.3  | 3.1.3  | 3.2.4  | -  |
| Folder monitoring  | 3.1.2  | 3.1.2  | 3.1.3<sup>4</sup>  | 3.1.3<sup>4</sup>  | 3.2.4  | 3.1.3  |
| Secure Relay  | 3.1.2  | 3.1.2  | 3.1.3  | 3.1.3  | -  | -  |
| Multi-node architecture  | 3.0.1  | 3.0.1<sup>1</sup>  | 3.0.1  | -  | -  | 3.0.1  |
| TrustedFile (PGP S-MIME CMS)  | 3.0.1<sup>3</sup>  | 3.0.1<sup>1</sup>  | 3.0.1  | -  | -  | -  |
| PassPort AM  | 2.7.1  | 2.7.1<sup>1</sup>  | 3.0.1  | 3.0.1  | 3.2.4  | 2.7.1  |
| SFTP  | 3.4  | 3.4 <sup>5</sup>  | 3.5 <sup>6</sup>  | 3.9  | 3.6<sup>6</sup>  | -  |
| IPv6  | 2.7.1  | 2.7.1<sup>1</sup>  | 2.7.1  | 2.7.1  | 3.3.2  | 2.7.1  |
| pTCP  | 2.7.1  | 2.7.1<sup>1</sup>  | -  | -  | -  | -  |
| UDT (excluding multi-node)  | 2.7.1  | 2.7.1<sup>2</sup>  | -  | -  | -  | -  |
| SOCKS  | 2.7.1  | 2.7.1  | 3.0.1  | 2.7.1  | 3.3.2  | 2.7.1  |
| Heartbeat functionality  | 2.7.1  | 2.7.1  | 2.7.1  | 2.7.1  | 3.2.4  | 2.7.1  |
| Bandwidth control  | 3.0.1  | 3.0.1  | 3.0.1  | 3.0.1  | 3.3.2  | 3.0.1  |
| System users (USERCTRL)  | 2.7.0  | 2.6.2  | 3.2.2  | 3.1.3  | -  | -  |



============================== table nb count(7) ============================================


| Functionality  | Central Governance<br /> or Flow Manager | Transfer CFT user interface<br />  |
| --- | --- | --- |
| Administration | X  | X  |
| Configuration  | X*  | X  |
| Monitor transfers  | X  | X  |
| Manage transfers  | -  | X  |
| Monitor the log  | X  | X  |
| Manage certificates  | X  | X  |
| End-to-end monitoring  | X  | -  |



============================== table nb count(8) ============================================


| Operating system  | Tested and supported  | Not supported  |
| --- | --- | --- |
| AIX  | GPFS (recommended), NFSv4  | NFSv3, CXFS, VeritasSF  |
| HP-UX  | NFSv4  | NFSv3, CXFS, VeritasSF  |
| Linux-x86  | GPFS (recommended), NFSv4, GFS2, AWS EFS  | NFSv3, CXFS, ACFS, OCFSv1, OCFSv2, QFS, VeritasSF  |
| OpenVMS  | RMS  |   |
| Solaris  | NFSv4  | NFSv3, CXFS, QFS, VeritasSF  |
| Windows-x86  | SMB/CIFS, GPFS  | CXFS, NFS  |
| z/OS  | Sharing DASD across Sysplex  |   |



============================== table nb count(9) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| ssl.certificates.ca_cert_bundle  | string  | Path to the CA certificate bundle. This path can point to either a file containing the CA certificates (for example, <code>/etc/ssl/certs/ca-certificates.crt</code>) or to a directory containing the CA certificates (for example, <code>/etc/ssl/certs/</code>), which are stored individually with their filenames in a hash format.<br/> You can refer to the <a href="https://curl.haxx.se/docs/manpage.html#--cacert">cURL man page</a> for information on the <code>cacert </code>and <code>capath </code>options.<br/> <blockquote> **Note**<br/> Note: You can set this parameter on UNIX systems, however it is not applicable on Windows.<br/> </blockquote> If the certificate bundle is not available on your system, you can download it from: <a href="https://curl.haxx.se/docs/caextract.html">curl.haxx.se/docs/caextract.html</a> (see <a href="https://curl.haxx.se/ca/cacert.pem">cacert.pem</a>). |



============================== table nb count(10) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| aws.credentials  | node  | List of <a href="#storageaccount">STORAGEACCOUNT</a> values where each STORAGEACCOUNT consists of an access key pair.  |
| aws.credentials.&lt;storageaccount&gt;.access_key_id  | string  | Access key ID, a 20-character, alphanumeric sequence. |
| aws.credentials.&lt;storageaccount&gt;.secret_access_key  | passwd  | Secret access key, a 40-character sequence. |



============================== table nb count(11) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| aws.credentials.&lt;storageaccount&gt;.region  | string  | Region to use; this value overrides the parsing of the WORKINGDIR and the config/env settings.<br/> When using the endpoint format for WORKINGDIR, you can use this parameter to set the AWS Signature Version 4 region to something other than the default (us-east-1). |



============================== table nb count(12) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| aws.credentials.&lt;storageaccount&gt;.encryption_type  | string  | Type of server-side encryption to use:<br/> • None: No encryption on Amazon S3 objects<br/> • sse-s3: Server-side encryption with AES 256<br/> • sse-kms: Server-side encryption with Key Management Service<br/> See the <a href="#globally_encrypt">example</a> for details on encrypting files. |
| aws.credentials.&lt;storageaccount&gt;.encryption_key_id  | string  | Key identifier for SSE-KMS encryption use; you must provide the full ID of the encryption key for the server. |



============================== table nb count(13) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| aws.credentials.&lt;storageaccount&gt;.acl  | string  | Type of ACL policy to apply to files when uploading a file to AWS:<br/> • private<br/> • public-read<br/> • public-read-write<br/> • aws-exec-read<br/> • authenticated-read<br/> • bucket-owner-read<br/> • bucket-owner-full-control |



============================== table nb count(14) ============================================


| Parameter  | Type  | Description  |
| --- | --- | --- |
| aws.credentials.&lt;storageaccount&gt;.proxy_scheme  | string  | Proxy scheme to use (HTTP or HTTPS).  |
| aws.credentials.&lt;storageaccount&gt;.proxy_host  | string  | Proxy IP address or FQDN.  |
| aws.credentials.&lt;storageaccount&gt;.proxy_port  | string  | Proxy port.  |
| aws.credentials.&lt;storageaccount&gt;.proxy_username  | string  | Proxy user name.  |
| aws.credentials.&lt;storageaccount&gt;.proxy_password  | password  | Proxy password.  |



============================== table nb count(15) ============================================


| Parameter<span id="storageaccount"></span>  | Type  | Description  |
| --- | --- | --- |
| fname  | string (key)  | The fname field corresponds to the S3 services key.  |
| workingdir  | string  | There are two supported formats. For either, the workingdir field must start with <code>s3://</code> and be followed by the designated items in the order listed:<br/> • <code>s3://bucket.region</code><br /> • the bucket name<br/> • a period (.)<br/> • the region<br/> <br/> • <code>s3://http[s]://endpoint[:port]/bucket</code><br /> • http:// or https:// for secure communication<br/> • the endpoint, which can be an IP address or the server's hostname<br/> • a colon (:) and port (if not using the default of 80 for HTTP, 443 for HTTPS)<br/> • a slash (/)<br/> • the bucket name<br/>  |
| storageaccount  | string  | Points to the access key identifier(s) and the access key secret(s) stored in UCONF. See also storageaccount.  |



============================== table nb count(16) ============================================


| V23 format<br/> V24 format<br/> Error | CFTT00E CFT request warning _ &amp;str<br/> CFTT00E CFT request warning - &amp;str |
| --- | --- |
| Explanation | An error may have occurred during a request sent to the Transfer CFT. The &amp;str message label specifies the possible type of error:<br/> • Unknown protocol request: Internal error of the Transfer CFT, which receives an unexpected protocol event<br/> • Unknown oper request: The operator command received is unknown<br/> • Not computable state: The transfer is not possible (status other than &quot;D&quot; (Available)<br/> • Transfer for myself rejected: The target of the transfer is the local site (CFTPARM PART field) The Transfer CFT therefore refuses to activate a transfer to itself<br/> • Logger currently unreachable: A SWITCH command, switching log files, was attempted while the LOG task (CFT log) was not (or no longer) active<br/> • Ignored (Catalog Full): The catalog was 100% full and so the last SEND (or RECV) command could not be processed; if it was submitted via the Transfer CFT communication file, it is stored in the file and the associated communication process stops (for more information, refer to the CFTC01W message)<br/> • Request syntax error: There is a syntax error in the request; inform Product Support<br/> • Catalog request unknown :The request is invalid<br/> • Unknown process request: An internal Transfer CFT error was detected; inform Product Support<br/> • Unknown file request: An internal Transfer CFT error was detected; inform Product Support<br/> • Transfer already in progress: An attempt was made to restart a transfer in progress; the transfer was not restarted<br/> • File already transferred: An attempt was made to restart a terminated transfer; the transfer was not restarted<br/> • &amp;file: A read error was detected on the authorizations file (&amp;file); inform Product Support<br/> • Access Exit Task unreachable: &amp;diagp: The directory exit task cannot be accessed (DIAGP specifies the cause); inform Product Support<br/> • Request Ignored : time-out: The request was not processed by the Transfer CFT (end time limit exceeded)<br/> • Unable to attach Client mailbox: Attachment to the client application was rejected<br/> • Unable to send data to Client mailbox: Data cannot be sent to the client application |



============================== table nb count(17) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT01E"></span>CFTT01E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open mode not allowed<br/> CFTT01E IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open mode not allowed |
| --- | --- |
| Explanation | A transfer request was made in OPEN mode, but this mode is not supported for the partner concerned. |
| Consequence | The transfer is denied. The corresponding catalog entry is set to the KEEP status. |
| Action | Transfer the files with this partner in closed mode. |



============================== table nb count(18) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT02E"></span>CFTT02E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Transfer Area Full<br/> CFTT02E _ Transfer Area Full &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | A new transfer request was made but the maximum number of transfers allowed at the same time has been reached. |
| Consequence | The transfer is not executed. |
| Action | Wait for a decrease in the number of transfers or increase the maximum number of authorized transfers (this increase can only be made by the technicians responsible for porting and customizing the Transfer CFT product). |



============================== table nb count(19) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT03E"></span>CFTT03E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max retry Reached<br/> CFTT03E _ Max retry Reached &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The Transfer CFT has performed all retry actions to establish the link with the partner.<br/> • The transfer activation retry counter for this protocol has exceeded the value of the RESTART parameter (CFTPROT command) In this case there have been no other network connection attempts and there are no more protocols in this partner's protocol list In this case the DIAGI code is set to 406<br/> • The physical connection has resulted in an invalid network address. It is the last address for this protocol; there is no backup partner. The internal diagnostic code (DIAGI) is set to 405. When the catalog is displayed, it overrides the value 301 signifying an invalid address<br/> • The physical connection has resulted in a fatal network error. In this case the DIAGI code is set to 303; the DIAGP value defines the source of the error<br/> • The last physical connection attempted according to the values of the RETRYM, RETRYN and RETRYW parameters has failed. It is the last protocol in this partner's protocol list; there is no backup partner<br/> Note: the internal diagnostic code (DIAGI) is set to 405. When the catalog is displayed, it overrides the value 302 signifying a non-fatal network error. |
| Consequence | The transfer is refused. The corresponding catalog entry is set to the KEEP status. |
| Action | Determine the error according to the DIAGI value. Analyze the DIAGP code. |



============================== table nb count(20) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT05E"></span>CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart Failed<br/> CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart Failed |
| --- | --- |
| Explanation | A file transfer restart request is not possible (the restart identifier is unknown, for example). |
| Consequence | The transfer is not restarted. |
| Action | Try a new transfer. |



============================== table nb count(21) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT06W"></span>CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner switching IPART=&amp;part<br/> CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner switching IPART=&amp;part |
| --- | --- |
| Explanation | The partner (&amp;part) cannot be reached within the authorized time slot (OMINTIME, OMAXTIME). |
| Consequence | The transfer will be retried via the intermediate partner IPART. |



============================== table nb count(22) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT07W"></span>CFTT07W Ending Transfer Task &amp;n Failed _ A transfer Running<br/> CFTT07W Ending Transfer Task &amp;n Failed _ A transfer Running |
| --- | --- |
| Explanation | Attempt to delete a transfer task for which not all transfers have been completed. &amp;n designates an internal Transfer CFT task number incremented each time a transfer task is activated. |



============================== table nb count(23) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT08E"></span>CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No prot available<br/> CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No prot available |
| --- | --- |
| Explanation | The maximum number of retries authorized for a transfer using the &amp;prot protocol has been reached (see the Transfer CFT CFTPROT RESTART parameter). |
| Consequence | The entry corresponding to the transfer in the catalog is set to KEEP. |
| Action | Analyze the causes of the broken communication link. |



============================== table nb count(24) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT09E"></span>CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Maximum cv affected<br/> CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Maximum cv affected |
| --- | --- |
| Explanation | All virtual circuits associated with a partner in server mode have already been allocated |
| Consequence | The transfer is refused locally. |
| Action | Wait for virtual circuits to be freed or increase the maximum number of virtual circuits (see the Transfer CFT Online documentation CNXIN and CNXINOUT parameters). |



============================== table nb count(25) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT10E"></span>CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not authorized<br/> CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not authorized |
| --- | --- |
| Explanation | The &amp;prot protocol is not authorized for this partner. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check Transfer CFT parameter settings. |



============================== table nb count(26) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT11E"></span>CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ &amp;net not found<br/> CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ &amp;net not found |
| --- | --- |
| Explanation | The network characteristics associated with the partner and for the &amp;n class of resources have not been found in the Transfer CFT partner file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings. |



============================== table nb count(27) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT12W"></span>CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out of time to call<br/> CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out of time to call |
| --- | --- |
| Explanation | A transfer request was made outside the time slot authorized for this partner. |
| Consequence | The transfer is not executed (remains in the D state). |
| Action | Execute a new transfer within the time slot authorized for this partner. |



============================== table nb count(28) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT13I"></span>CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host)<br/> CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host) |
| --- | --- |
| Explanation | Information message for each dialno (or host) switch and protocol. |



============================== table nb count(29) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT14E"></span>CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not found<br/> CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not found |
| --- | --- |
| Explanation | The &amp;part partner was not found in the Transfer CFT partner file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings.<br/> Check the {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} parameter settings. |



============================== table nb count(30) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT15E"></span>CFTT15E NPART=&amp;part _ Not found<br/> CFTT15E NPART Not found &lt;NPART=%s&gt; |
| --- | --- |
| Explanation  | The network identifier of the &amp;part partner was not found in the Transfer CFT partner file.  |
| Consequence  | The transfer is not executed. The corresponding catalog entry is set to KEEP.  |
| Action  | Check the Transfer CFT parameter settings.  |
| V23 format<br/> V24 format<br/> Error | CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters<br/> CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters |
| Explanation | The network identifier of the &amp;part partner was not found in the Transfer CFT partner file. A protocol limitation may have truncated the partner to 24 characters. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings and limit the partner ID to 24 characters.  |



============================== table nb count(31) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT16E"></span>CFTT16E PART=&amp;part IDF=&amp;idf _ No implicit send<br/> CFTT16E PART=&amp;part IDF=&amp;idf _ No implicit send |
| --- | --- |
| Explanation | The partner has made a selection request and no file is ready to be sent (SEND on HOLD or implicit SEND). |
| Consequence | The transfer is not executed (no catalog record is created). |
| Action | Prepare a transfer (SEND state=hold) or declare an implicit send in the Transfer CFT parameter settings.<br/> Prepare a transfer (SEND state=hold) or declare an implicit send in the {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} parameter settings. |



============================== table nb count(32) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT17I"></span>CFTT17I PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ STATE=HOLD<br/> CFTT17I PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ STATE=HOLD |
| --- | --- |
| Explanation | A transfer request was voluntarily put on Hold (see Transfer CFT Concepts, Send on Hold). |
| Consequence | The transfer is not executed and is on hold for a possible reception request. |



============================== table nb count(33) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT18E"></span>CFTT18E PART=&amp;part IDF=&amp;idf CFTAUTH id=&amp;id _ Not found<br/> CFTT18E PART=&amp;part IDF=&amp;idf CFTAUTH id=&amp;id _ Not found |
| --- | --- |
| Explanation | The identifier of the list of files authorized for a partner (see CFTPART ) was not found in the Transfer CFT parameter file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings.<br/> Check the {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} parameter setting. |



============================== table nb count(34) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT19E"></span>CFTT19E PART=&amp;part _ Invalid remote password &amp;str *<br/> CFTT19E PART=&amp;part _ Invalid remote password &amp;str * |
| --- | --- |
| Explanation | Transfer request was made and the partner sent an invalid password.<br/> *where &amp;str = supplied password is incorrect |
| Consequence | The connection is refused. |
| Action | Execute a new transfer with a valid password. |



============================== table nb count(35) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT20E"></span>CFTT20E PART=&amp;part _ PVC not allowed<br/> CFTT20E PART=&amp;part _ PVC not allowed |
| --- | --- |
| Explanation | The call collect connection request received is not authorized for this partner. |
| Consequence | The connection is refused.  |



============================== table nb count(36) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT21E"></span>CFTT21E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Catalog access failed &amp;scs ,&amp;cr<br/> CFTT21E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Catalog access failed &amp;scs ,&amp;cr |
| --- | --- |
| Explanation | During a transfer (or a transfer request) an undetermined Transfer CFT catalog access error was detected (input/output error for example). |
| Consequence | The transfer is interrupted (or not executed). |
| Action | Analyze the &amp;scs code and inform Product Support if necessary. |



============================== table nb count(37) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT22E"></span>CFTT22E &amp;str PART=&amp;part IDF=&amp;idf IDT=&amp;idt_ &amp;str<br/> CFTT22E _&amp;str &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; &amp;str |
| --- | --- |
| Explanation | Connection refused due to user authentication failure (rpasswd, spasswd error).<br/> The &amp;str provides additional information.<br/> For more information, see Password management. |
| Consequence | The transfer is not executed. |
| Action | Check the &amp;str, correct, and retry. |



============================== table nb count(38) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT23E"></span>CFTT23E PART=&amp;part Shutdown in progress _ &amp;str<br/> CFTT23E PART=&amp;part Shutdown in progress _ &amp;str |
| --- | --- |
| Information | A Transfer CFT shutdown is in progress, the request sent is not processed (the &amp;str message specifies the type of request).<br/> Connect in being refused: connection request from one of its partners. |



============================== table nb count(39) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT24E"></span>CFTT24E PART=&amp;part PROT=&amp;prot _ Invalid call number &amp;n<br/> CFTT24E PART=&amp;part PROT=&amp;prot _ Invalid call number &amp;n |
| --- | --- |
| Explanation | The called number received (server end) is not in the list of numbers defined (and authorized) for this partner (&amp;n represents the unauthorized number). |
| Consequence | The connection is refused. |



============================== table nb count(40) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT25E"></span>CFTT25E PART=&amp;part IDF=&amp;idf _ IDF not authorized<br/> CFTT25E PART=&amp;part IDF=&amp;idf _ IDF not authorized |
| --- | --- |
| Explanation | During a transfer request the identifier of the file to be transferred is not authorized for this partner (server or requester end). |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Request that another file be sent or authorize this identifier. |



============================== table nb count(41) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT26E"></span>CFTT26E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max transfer tasks<br/> CFTT26E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max transfer tasks |
| --- | --- |
| Explanation | A new transfer request was made but the maximum number of transfer processes has been reached (as has the maximum number of transfers per process). |
| Consequence | The transfer is not executed and remains in the D state. |
| Action | Wait for a decrease in the number of transfers or increase the maximum number of authorized processes or the maximum number of transfers per process. This increase can only be made by the technicians responsible for porting and customizing the Transfer CFT product. |



============================== table nb count(42) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT27E"></span>CFTT27E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Error &amp;scs writing starts<br/> CFTT27E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Error &amp;scs writing starts |
| --- | --- |
| Explanation | The statistics relating to the designated transfer could not be written in the accounting file. |
| Consequence | The accounting file is incomplete. |
| Action | Analyze the file access system code (&amp;scs) to determine the source of the error. |



============================== table nb count(43) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT28E"></span>CFTT28E No outgoing CV configured on Network<br/> CFTT28E No outgoing CV configured on Network |
| --- | --- |
| Explanation | An outgoing call attempt was made on a network resource configured with the CALL = IN parameter (CFTNET command). |
| Consequence | The requester transfer cannot be executed.<br/> The catalog entry is set to the K state with a protocol diagnostic code (DIAGP): &quot;L 0B 22&quot; - 0B meaning that network access is forbidden.<br/> If another protocol (CFTPROT) using another network resource (CFTNET) is declared for this partner (PROT parameter of the CFTPART command), Transfer CFT will make another attempt on this resource. |
| Action | Change the parameter settings so that the protocol designated for the partner points to a network resource available for outgoing calls. |



============================== table nb count(44) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT29E"></span>CFTT29E DEST= &amp;dest -Invalid use _Define for [BOTH/LOCAL/COMMUT] use only<br/> CFTT29E DEST= &amp;dest -Invalid use _Define for [BOTH/LOCAL/COMMUT] use only |
| --- | --- |
| Explanation | A broadcast list can be used (FOR = parameter) with the value:<br/> • LOCAL meaning that the partner list can only be used for a direct transfer.<br/> • COMMUT meaning that the partner list can only be used for store and forward operations.<br/> • BOTH meaning that the partner list is used locally and for store and forward operations. |



============================== table nb count(45) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT30E"></span>CFTT30E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max Exit tasks<br/> CFTT30E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max Exit tasks |
| --- | --- |
| Explanation | A new transfer request with an associated EXIT was requested but the maximum number of EXIT processes has been reached. |
| Consequence | The transfer is not executed (remains set to the D state). |
| Action | Wait for a decrease in the number of transfers or increase the maximum number of processes allowed. |



============================== table nb count(46) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT31W"></span>CFTT31W Ending Exit Task &amp;n Failed _ A transfer Running<br/> CFTT31W Ending Exit Task &amp;n Failed _ A transfer Running |
| --- | --- |
| Explanation | Attempt to delete an EXIT task in which not all transfers have been completed. &amp;n designates an internal Transfer CFT task number incremented each time a transfer task is activated. |



============================== table nb count(47) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT32E"></span>CFTT32E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner not found<br/> CFTT32E _ Partner not found &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The identifier of the &amp;part partner was not found in the Transfer CFT partner file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings. |



============================== table nb count(48) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT33E"></span>CFTT33E PART = &amp;dest IDF = &amp;idf IDT = &amp;idt _ Illegal use of CFTDEST<br/> CFTT33E _ Illegal use of CFTDEST &lt;IDTU=&amp;idtu PART=&amp;part &amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The identifier of a partner mentioned in a list (CFTDEST command) is itself a list identifier. As list embedding is not allowed, the transfer with this partner is interrupted.<br/> Transfers with the previous partners in the list are nevertheless activated, but only for an explicit list (FNAME parameter of the CFTDEST command). |
| Consequence | The transfer is interrupted with a DIAGI 401. |
| Action | Change the partners list to show all the partners on one level. |



============================== table nb count(49) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT34E"></span>CFTT34E PART = &amp;part IDF = &amp;idf _ &amp;cause<br/> CFTT34E _ &amp;cause&lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf&gt; |
| --- | --- |
| Explanation | Access error on an external file describing a list of items:<br/> • Partners list: CFTDEST FNAME=#filename,<br/> • File group: SEND FNAME=#filename,<br/> Possible values of &amp;cause are:<br/> • Allocating external file &amp;file<br/> • Opening external file &amp;file<br/> • Reading external file &amp;file<br/> The file processing phase (allocation, opening or reading) is specified in the message. |
| Consequence | The external file cannot be read - the corresponding transfers are not activated. |
| Action | Correct the file access problem. |



============================== table nb count(50) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT35W"></span>CFTT35W PART=&amp;part IDF=&amp;idf IDT=&amp;idt DELETE file &amp;fname Failed _&amp;str<br/> CFTT35W DELETE file &amp;fname Failed _&amp;str &lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | A DELETE command is executed on a catalog request (in receive mode and in a non-terminated H or K state).<br/> The receive file corresponding to this request could not be deleted.<br/> “ ” (no label): The file cannot be deleted; inform Product Support<br/> • Allocate file error: File allocation error<br/> • Open file error File open error<br/> • Close file error: File closing error<br/> • Free file error: File release error<br/> • Allocate memory error: Memory allocation error |
| Consequence | The request is deleted from the catalog but the user is notified that the &amp;wfname file was not deleted. |



============================== table nb count(51) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT36W"></span>CFTT36W PART=&amp;part IDF=&amp;idf IDT=&amp;idt ERASE file &amp;fname Failed &amp;str<br/> CFTT36W ERASE file &amp;fname Failed &amp;str &lt;IDTU=&amp;idtu PART = &amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | A DELETE command is executed on a catalog request (in receive mode and in a non-terminated state).K or H<br/> The purge of the received file that corresponds with this request could not be carried out:<br/> • Allocate file error: File allocation error<br/> • Open file error : File open error<br/> • Close file error: File clofile close error<br/> • Free file error: File release error<br/> • Allocate memory error: Memory allocation error |
| Consequence | The request is deleted from the catalog but the user is notified that the &amp;fname file has not been purged. |



============================== table nb count(52) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT37I"></span>CFTT37I PART=&amp;part _ Not found and ignored for CFTDEST &amp;id<br/> CFTT37I _ Not found and ignored for CFTDEST &amp;id &lt;IDTU=&amp;idtu PART=&amp;part&gt; |
| --- | --- |
| Explanation | The NOPART parameter for the CFTDEST command can have on of the following values: ABORT (default), CONTINUE, or IGNORE.<br/> • ABORT: Transfer CFT continues functioning as it was before the request for change. No transfer is generated if a partner does not exist in the list of partners defined in the PART parameter. If the list of partners is defined in the PART parameter. If the list of partners is defined in a file (FNAME parameter) the transfers carried out for the only for existing partners and the treatment is identical to that for the NOPART=CONTINUE option.<br/> • CONTINUE: If the partner does not exist, Transfer CFT indicates this in a message in the LOG. CFTT32E PART=idpart Not found. Pass the transfer in SFK diagi 408 and continue the transfers for the other partners. The generic post remains in the K state and the end of transfer procedure is not executed.<br/> • IGNORE: • If a partner does not exist in the list, Transfer CFT ignores the partner (there is no transfer) and moves on to the next partner.<br/> • A message is displayed in the LOG CFTT37I PART=idpart _ Not found and ignored for CFTDEST iddest<br/> • The generic job passes to the T state and is under the end of transfer procedure.<br/>  |



============================== table nb count(53) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT38I"></span>CFTT38I PART=&amp;part _ Dynamic partner: &amp;npart<br/> CFTT38I _Dynamic partner: &amp;npart &lt; PART=&amp;part DIAG=&amp;diag&gt; |
| --- | --- |
| Information | When receiving an incoming call from an unknown source (no local partner description corresponding to the &amp;part network name received), the &amp;npart dynamic partner creation mechanism is triggered. |



============================== table nb count(54) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT39E"></span>CFTT39E PART=&amp;part DIAG=&amp;diag _ Access Exit Connect Reject<br/> CFTT39E _ Access Exit Connect Reject &lt;PART=&amp;part DIAG=&amp;diag&gt; |
| --- | --- |
| Explanation | The connection is refused by the directory EXIT task; &amp;diag contains the field in the communication structure updated by the EXIT. |
| Consequence | The transfer is aborted with the following diagnostics codes: 403, 409, 410, 411, 414, 415, 416, 418, 425, 426. |



============================== table nb count(55) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT40E"></span>CFTT40E PART=&amp;part DIAG=&amp;diag _ Access Exit Error<br/> CFTT40E _ Access Exit Error &lt;PART=&amp;part DIAG=&amp;diag&gt; |
| --- | --- |
| Explanation | An error has been detected in the directory EXIT task. |
| Consequence | The transfer is aborted with the following possible diagnostics codes: 134, 423. |



============================== table nb count(56) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT42E"></span>CFTT42E part&amp;PART=&lt;Partner switching IPART=PART not available<br/> CFTT42E _ Partner switching IPART=PART not available &lt;PART=&amp;part&gt; |
| --- | --- |
| Explanation | The IPART value must be different than the PART value. |



============================== table nb count(57) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT44E"></span>CFTT44E PART=&amp;part IDF=&amp;idf _ &amp;str directory &amp;file<br/> CFTT44E _ &amp;str directory &amp;file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf&gt; |
| --- | --- |
| Explanation | The file selection phase is indicated in the message, where &amp;str can be allocating, opening, empty, or reading. A directory access error has been detected when sending a list of file names or a group of files based on a selection.<br/> SEND FNAME = # FIL* or SEND FNAME = # DIR*. |
| Consequence | If the directory could not be accessed (allocating, opening or empty), no transfers are triggered.<br/> If the directory could not be read when selecting the files in the directory, all transfers preceding the error are triggered. |



============================== table nb count(58) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT44W"></span>CFTT44W PART=&amp;part IDF=&amp;idf _ &amp;str directory &amp;file (file not found ignored)<br/> CFTT44W _ &amp;str directory &amp;file &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf&gt; (file not found ignored) |
| --- | --- |
| Explanation | The file selection phase is indicated in the message, where &amp;str can be allocating, opening, empty, or reading.<br/> A directory access error has been detected when sending a list of file names or a group of files based on a selection.<br/> SEND FNAME = # FIL* or SEND FNAME = # DIR*. |
| Consequence | If the directory is empty, Transfer CFT ignores the fact that the file is not found, and passes the transfer to the X phase. |
| Action  | Ignore this error.  |



============================== table nb count(59) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT45E"></span><br/> CFTT45E PART=&amp;part _ Partner switching IPART=&amp;ipart not found<br/> CFTT45E _ Partner switching not found &lt;PART=&amp;part IPART=&amp;ipart&gt; |
| --- | --- |
| Explanation | The intermediate partner (IPART) was not found. |
| Consequence | The transfer cannot be performed. |



============================== table nb count(60) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT46W"></span>CFTT46W PART=&amp;part ,IDF=&amp;idf ,IDT=&amp;idt _ Part inactive: mode &amp;str<br/> CFTT46W _ Part inactive: mode &amp;str &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The transfer attempt for partner &amp;part cannot succeed as the partner is inactive in &amp;str mode:<br/> • &amp;str= requester or<br/> • &amp;str = server |



============================== table nb count(61) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT47E"></span>CFTT47E PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;id _ Cannot find SSL security profil<br/> CFTT47E _ Cannot find SSL security profil &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot&gt; |
| --- | --- |
| Explanation | The attempted transfer the &amp;part partner cannot be performed because the security profile was not found. For more information on SSL definition for CFTPART, see the SSL parameter description. |
| Consequence | The transfer can not be carried out. |



============================== table nb count(62) ============================================


| V23 format<br /> V24 format<br /> Warning | <span id="CFTT47W"></span>CFTT47W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot SSLid=&amp;id DIRECT=CLIENT _ Cannot find SSL security profil<br/> CFTT47W _ Cannot find SSL security profil &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROTOCOL=&amp;prot SSLID=&amp;id DIRECT=CLIENT&gt;<br/> CFTT47W PART=&amp;part SSLid=&amp;id DIRECT=SERVER _ No SSL security profile for additional checks<br/> CFTT47W _ No SSL security profile for additional checks &lt;PART=&amp;part SSLID=&amp;id DIRECT=SERVER&gt; |
| --- | --- |
| Explanation | The transfer attempt for partner &amp;part uses a non-existent CFTSSL (&amp;sslid). |
| Action | Check the configuration and add the missing profile. |



============================== table nb count(63) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT48E"></span>CFTT48E PART=&amp;part SSL=&amp;id _ Server Session rejected reason=&amp;reason<br/> CFTT48E _ Server Session rejected reason=&amp;reason &lt;PART=&amp;part SSL=&amp;ssl&gt; |
| --- | --- |
| Explanation | The attempted transfer the &amp;part partner cannot be performed because the security profile is not valid, with as an internal reason (&amp;reason). |
| Consequence | The transfer can not be carried out. |
| Action | Note the REASON (&amp;reason) value and contact the product support team if necessary. |



============================== table nb count(64) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT49W"></span>CFTT49W Unable to send data to Synchronous task<br/> CFTT49W Unable to send data to Synchronous task |
| --- | --- |
| Explanation | Synchronous communication task is inaccessible. |



============================== table nb count(65) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT50E"></span>CFTT50E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Duplicate transfer with IDTU=<br/> CFTT50E _ Duplicate transfer with IDTU=&amp;idtu &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | A duplicate transfer occurred. IDTU=&amp;idtu is the previously performed transfer.<br/> For more information, see the DUPLICAT field details. |



============================== table nb count(66) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT51I"></span>CFTT51I PART=&amp;part ,&amp;str session opened<br/> CFTT51I PART=&amp;part ,&amp;str session opened |
| --- | --- |
| Explanation | The session is open, the connection request has been accepted (requester side (&amp;str= requester if not secured, &amp;str=SSL requester) or server (&amp;str = server if not secured , &amp;str=SSL server if secured)). |



============================== table nb count(67) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT52I"></span>CFTT52I PART=&amp;part ,&amp;str session closed<br/> CFTT52I PART=&amp;part ,&amp;str session closed |
| --- | --- |
| Explanation | The session is closed: requester side (&amp;str = requester if not secured, &amp;str = SSL requester if secured) or server (&amp;str = server if not secured , &amp;str = SSL server if secured). |



============================== table nb count(68) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT53I"></span>CFTT53I PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;str file &amp;str1<br/> CFTT53I &amp;str file &amp;str1 &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The file is selected (&amp;str1 = selected) or created (&amp;str1 = created) either by the requester (&amp;str = requester) or by the server (&amp;str = server). |



============================== table nb count(69) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT54I"></span>CFTT54I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str file deselected<br/> CFTT54I &amp;fname file deselected &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The file is deselected either by the requester (&amp;str = requester) or by the server (&amp;str = server). |



============================== table nb count(70) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT55I"></span>CFTT55I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str file opened<br/> CFTT55I &amp;fname file opened &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The file is opened either by the requester (&amp;str = requester) or by the server (&amp;str = server). |



============================== table nb count(71) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT56I"></span>CFTT56I PART=&amp;part IDF=&amp;idf IDT=&amp;idt ,&amp;str file closed<br/> CFTT56I &amp;fname file closed &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The file is closed either by the requester (&amp;str = requester) or by the server (&amp;str = server. |



============================== table nb count(72) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT57I"></span>CFTT57I PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids,&amp;str transfer started<br/> CFTT57I &amp;str transfer started &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids&gt; |
| --- | --- |
| Explanation | The transfer has been started either by the requester (&amp;str = requester) or by the server (&amp;str = server).<br/> <blockquote> **Note**<br/> Note: IDS refers to the session identifier.<br/> </blockquote>  |



============================== table nb count(73) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT58I"></span>CFTT58I PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids,&amp;str transfer ended<br/> CFTT58I &amp;str transfer ended &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt IDS=&amp;ids&gt; |
| --- | --- |
| Explanation | The transfer has been completed either by the requester (&amp;str = requester) or by the server (&amp;str = server).<br/> <blockquote> **Note**<br/> Note: IDS refers to the session identifier.<br/> </blockquote>  |



============================== table nb count(74) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT59I"></span>CFTT59I PART=&amp;part IDM=&amp;idf IDT=&amp;idt ,&amp;str &lt;messageùùù_insert_pipe_here_ùùùreply&gt; transferred<br/> CFTT59I &amp;str &lt;messageùùù_insert_pipe_here_ùùùreply&gt; transferred &lt;IDTU=&amp;idtu PART=&amp;part IDM=&amp;idm IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The message or the reply has been sent either by the requester (&amp;str = requester) or by the server (&amp;str = server). |



============================== table nb count(75) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT60I"></span>CFTT60I &amp;str<br/> CFTT60I IDTU=&amp;idtu &amp;str |
| --- | --- |
| Explanation | The &amp;str message is an information message, sent by the file EXIT associated with the transfer. |



============================== table nb count(76) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT61E"></span>CFTT61E PART=&amp;part IDM=&amp;idf IDT=&amp;idt local message reject &amp;diagi ,&amp;diagp<br/> CFTT61E local message transfer reject &lt;IDTU=&amp;idtu PART=&amp;part IDM=&amp;idm IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The local partner rejects the message transfer. |
| Consequence | The message transfer is not executed. |
| Action | Correct the error and try again. |



============================== table nb count(77) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT62E"></span>CFTT62E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT62E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The transfer was interrupted by the operator (&amp;diagp = &quot;OPER&quot;) or by the file EXIT (&amp;diagp represents the phase of the EXIT which prompted the interruption = &quot;ALLOC&quot;, &quot;OPEN&quot;, TRANS or CLOSE). |
| Consequence | The transfer is aborted. The corresponding catalog entry is set to HOLD (after a HALT command from the operator or an interrupt by the EXIT), KEEP (after a KEEP command from the operator). |
| Action | After an interruption by the operator, the transfer can be restarted manually (START command).<br/> After interruption by a file EXIT, the action is to be defined by the engineers responsible for this file EXIT. |



============================== table nb count(78) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT62E"></span><span id="CFTT63E"></span>CFTT63E IDTU=&amp;idtu MODE=&amp;str Transfer refused due to product key limitation until &amp;date<br/> CFTT63E _ Transfer refused due to product key limitation until &amp;date &lt;IDTU=&amp;idtu MODE=&amp;mode&gt; |
| --- | --- |
| Explanation | The license key is limiting the number of transfers in this time frame, where:<br/> • &amp;str : REQUESTER or SERVER |



============================== table nb count(79) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT64E"></span>CFTT64E PART=&amp;part IDF=&amp;idf _ Flow does not exist and cft.default_idf.enable is set to 'no'<br/> CFTT64E _ Flow does not exist and cft.default_idf.enable is set to 'no' &lt;PART=&amp;part IDF=&amp;idf&gt; |
| --- | --- |
| Explanation | The default IDF functionality is disabled for the command. |
| Consequence | The transfer is not executed and has the status K. The DIAGP also reflects this status. |
| Action | For parameter details, see UCONF: General unified configuration parameters. |



============================== table nb count(80) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT65E"></span>CFTT65E PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Protocol not available<br/> CFTT65E _ PROT=&amp;prot not available &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The &amp;prot protocol is not authorized for this partner.  |
| Consequence | The transfer is not executed, and the corresponding catalog entry is set to KEEP. DIAGI=410 ,DIAGP = NO PROT  |
| Action | Check the PROT value in the SEND or RECV transfer.  |



============================== table nb count(81) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT66E"></span>CFTT66E Maximum number of partners authorized by license key reached (using PART=&amp;part)<br/> CFTT66E Maximum number of partners authorized by license key reached (using PART=&amp;part) |
| --- | --- |
| Explanation | {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} license keys support either a limited or unlimited number of partners. The transfer is treated as if the partner does not exist.  |
| Consequence | An error occurred because you have reached the maximum number of partners allowed by your license key.  |
| Action | In a command line window, you can enter the command CFTUTIL ABOUT to check the number of partners that your license key authorizes. For additional information on license keys, contact an {{&lt; TransferCFTtest/axwayvariablesCompanyName &gt;}} sales representative.  |



============================== table nb count(82) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT66E"></span>CFTT68E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Unexpected AT phase/phasestep at restart, converting T to K<br/> CFTT68E _ Unexpected AT phase/phasestep at restart, converting T to K &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | If Transfer CFT was stopped abruptly when creating one or more child transfers for the current generic transfer, when you restart Transfer CFT you cannot manage these transfers (AT phase/phasestep).  |
| Consequence | The corresponding transfer entry in the catalog now switches to the K phasestep instead of the previous T phasestep.  |
| Action | You can continue to manage the affected transfer (those in K phasestep).  |



============================== table nb count(83) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT69E"></span>CFTT69E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Unexpected YE phase/phasestep at restart, converting E to H<br/> CFTT69E _ Unexpected YE phase/phasestep at restart, converting E to H IDTU=&amp;idtu, PART=&amp;part, IDF=&amp;idf, IDT=&amp;idt |
| --- | --- |
| Explanation | If Transfer CFT was stopped abruptly during the post-processing phase, when you restart Transfer CFT you cannot manage these transfers (YE phase/phasestep).  |
| Consequence | The corresponding transfer entry in the catalog now switches to the H phasestep instead of the previous E phasestep.  |
| Action | You can continue to manage the affected transfer (those in H phasestep).  |



============================== table nb count(84) ============================================


| V23 format<br/> V24 format<br/> Information  | <span id="CFTT70I"></span>CFTT70I The user &amp;user is connecting with method &amp;method<br/> CFTT70I The user &amp;user is connecting with method &amp;method |
| --- | --- |
| Explanation  | A client is trying to connect to the server.  |



============================== table nb count(85) ============================================


| V23 format<br/> V24 format<br/> Error  | <span id="CFTT70E"></span>CFTT70E The user &amp;user is not allowed to connect to the server<br/> CFTT70E The user &amp;user is not allowed to connect to the server |
| --- | --- |
| Explanation  | The user is not allowed to connect to the server, or the password or the authentication method is incorrect.  |
| Action  | Correct the user name or password, or add a public key.  |



============================== table nb count(86) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT71E"></span>CFTT71E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote creation reject &amp;diagi ,&amp;diagp<br/> CFTT71E remote creation reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The file was not created, the internal &amp;diagi code explains the reason for the rejection (see the chapter on internal Transfer CFT codes). |
| Consequence | The transfer is not executed. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(87) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT72E"></span>CFTT72E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote selection reject &amp;diagi ,&amp;diagp<br/> CFTT72E remote selection reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The file was not selected; the internal &amp;diagi code explains the reason for the rejection (see the topic on internal Transfer CFT codes). |
| Consequence | The transfer is not executed. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(88) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT72W"></span>CFTT72W PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote selection reject (file not found ignored) &amp;diagi ,&amp;diagp,<br/> CFTT72W remote selection reject (file not found ignored) &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp |
| --- | --- |
| Explanation | FILENOTFOUND=IGNORE The file was not selected because the file is not found. |
| Consequence | The transfer is aborted. |



============================== table nb count(89) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT73E"></span><br/> CFTT72E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote selection reject &amp;diagi ,&amp;diagp<br/> CFTT72E remote selection reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp |
| --- | --- |
| Explanation | FILENOTFOUND=ABORT The message was not sent. |
| Consequence | The message transfer is aborted. The corresponding catalog entry is put on HOLD. |



============================== table nb count(90) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT73E"></span>CFTT73E PART=&amp;part IDM=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT73E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The message was not sent. |
| Consequence | The message transfer is aborted. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(91) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT74E"></span>CFTT74E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT74E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The transfer was interrupted by the remote partner. |
| Consequence | The transfer is aborted, the corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(92) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT75E"></span>CFTT75E PART=&amp;part IDF=&amp;idf IDT=&amp;idt connect reject &amp;diagi ,&amp;diagp<br/> CFTT75E connect reject &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf ùùù_insert_pipe_here_ùùù IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The connection request was rejected by the partner. |
| Consequence | The transfer failed. If the called number was engaged or a network incident occurred (for example), the transfer will be retried several times (see the RETRYM, RETRYN and RETRYW parameters).<br/> If all retries fail, the transfer is not executed and the corresponding catalog entry is set to KEEP. |
| Action | Analyze the internal &amp;diagi error code for the transfer and try to correct it. |



============================== table nb count(93) ============================================


| V23 format<br/> V24 format<br/> Error | CFTT75E Incorrect user or password &lt;IDTU=&amp;idtuPART=&amp;part IDF=&amp;idf IDT=&amp;idf DIAGI=&amp;diagi&gt;<br/> CFTT75E Incorrect user or password &lt;IDTU=&amp;idtuPART=&amp;part IDF=&amp;idf IDT=&amp;idf DIAGI=&amp;diagi&gt; &lt;/p&gt; |
| --- | --- |
| Explanation | Cannot connect to the SFTP server because the user name or password is incorrect. |
| Action | Correct the user name or password. |



============================== table nb count(94) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT76E"></span>CFTT76E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT76E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The write transfer request is refused. |
| Consequence | The transfer is not executed. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(95) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT77E"></span>CFTT77E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT77E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The read transfer request is refused. |
| Consequence | The transfer is not executed. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(96) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT78E"></span>CFTT78E PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp<br/> CFTT78E &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | A problem was detected at the end of the transfer. |
| Consequence | The transfer has terminated but is not considered to be valid, the corresponding catalog entry is set to DISP (transfer to be restarted), on HOLD (the transfer may be restarted) or to KEEP. |
| Action | Automatically by Transfer CFT or manually by the user (correct the error, restart or try a new transfer). |



============================== table nb count(97) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT79E"></span>CFTT79E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote deselect reject &amp;diagi ,&amp;diagp<br/> CFTT79E remote deselect reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The file could not be deselected. |
| Consequence | The transfer is interrupted. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(98) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT80E"></span>CFTT80E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote open reject &amp;diagi ,&amp;diagp<br/> CFTT80E remote open reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The file could not be opened. |
| Consequence | The transfer is interrupted. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(99) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT81E"></span>CFTT81E PART=&amp;part IDF=&amp;idf IDT=&amp;idt remote close reject &amp;diagi ,&amp;diagp<br/> CFTT81E remote close reject &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | The file could not be closed. |
| Consequence | The transfer is interrupted. The corresponding catalog entry is put on HOLD. |
| Action | Correct the error and try again. |



============================== table nb count(100) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT82E"></span>CFTT82E PART=&amp;part [IDF=&amp;idf ùùù_insert_pipe_here_ùùù IDM=&amp;idm] IDT=&amp;idt transfer aborted &amp;diagi ,&amp;diagp<br/> CFTT82E transfer aborted &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf ùùù_insert_pipe_here_ùùù IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | A serious error was detected.<br/> ****Example****<br/> 19/02/19 16:01:37 CFTT82E Transfer aborted &lt;IDTU=A0000008 PART=PARIS_KEY IDF=AS3SR IDT=B1916013 DIAGI=110<br/> 19/02/19 16:01:37 CFTT82E+ DIAGP=00000002 DIAGC=File not found: zohs.bat&gt; |
| Consequence | The transfer is interrupted and the corresponding catalog entry is set to KEEP. |
| Action | Correct the error and try again. |



============================== table nb count(101) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT82W"></span>CFTT82W PART=&amp;part IDF=&amp;idf IDT=&amp;idt transfer aborted (file not found ignored) &amp;diagi ,&amp;diagp<br/> CFTT82W transfer aborted (file not found ignored) &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf ùùù_insert_pipe_here_ùùù IDM=&amp;idm] IDT=&amp;idt &amp;diagi ,&amp;diagp&gt; |
| --- | --- |
| Explanation | File not found error was detected. |
| Consequence | The transfer ignore the file not found problem and pass to X phase. |
| Action | Ignore the error. |



============================== table nb count(102) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT83I"></span>CFTT83I PART=&amp;part IDF=&amp;idf IDT=&amp;idt change direction(CD) for request<br/> CFTT83I change direction(CD) for request &lt;IDTU=&amp;idtu PART=&amp;part [IDF=&amp;idf ùùù_insert_pipe_here_ùùù IDM=&amp;idm] IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | This message is only displayed for the ODETTE protocol and a RECV command. It indicates that the remote partner has accepted its turn to transmit. |



============================== table nb count(103) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT86I"></span>CFTT86I PART=&amp;part IDS=&amp;ids Change direction(TURN) sent<br/> CFTT86I Change direction(TURN) sent &lt;PART=&amp;part IDS=&amp;ids&gt; |
| --- | --- |
| Explanation | For a PeSIT protocol in a DMZ profile, the token (TURN) has been sent to the partner &amp;part. |



============================== table nb count(104) ============================================


| V23 format<br/> V24 format<br/> Information | CFTT86I FNAME=&amp;fname S=ByteCount<br/> CFTT86I FNAME=&amp;fname S=ByteCount |
| --- | --- |
| Explanation | Name of the file sent or received and the number of bytes in the file. This message completes the CFTT54I message. Name of the file sent or received and the number of bytes in the file. This message completes the CFTT54I message. |



============================== table nb count(105) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT87I"></span>CFTT87I PART=&amp;part IDS=&amp;ids Change direction(TURN) received<br/> CFTT87I Change direction(TURN) received&lt;PART=&amp;part IDS=&amp;ids&gt; |
| --- | --- |
| Explanation | For the PeSIT protocol in a DMZ profile, the token (TURN) has been received by the partner &amp;part, where IDS is the reference for the session context. |



============================== table nb count(106) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT88I"></span>CFTT88I+IDT=&amp;idt WORKINGDIR=&amp;workingdir FNAME=&amp;fname NBC=&amp;n DURATION=&amp;time<br/> CFTT88I+&lt;IDTU=&amp;idtu WORKINGDIR=&amp;workingdir FNAME=&amp;fname NBC=&amp;n DURATION==&amp;time&gt; |
| --- | --- |
| Explanation | This message completes the message CFTT54I.<br/> The following fields indicated:<br/> • WORKINGDIR: if the WORKINGDIR is not defined, this field is empty<br/> • fname: name of the file sent<br/> • n: number of bytes in the file<br/> • time: transfer duration in seconds |



============================== table nb count(107) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT89I"></span>CCFTT89I PART=&amp;part IDF=&amp;idf IDT=&amp;idt [FACTION on FNAME ] or [NACTION on NFNAME]=&amp;fname : &amp;str+&quot;deleted&quot; or &quot;erased&quot;<br/> CFTT89I [FACTION on FNAME ] or [NACTION on NFNAME] =&amp;fname : &amp;str+&quot;deleted&quot; or &quot;erased&quot; &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation |  • FACTION=ERASE or DELETE erased or deleted the file (FNAME) as follows: • When using the SEND command, the action occurred after the transfer completed.<br/> • When using the RECV command, the action occurred before the transfer.<br/> <br/> • NACTION=DELETE was used in a RECV command, which deleted the file (NFNAME) at the end of the transfer. This option is only available when using SFTP. |
| Information  | CFTT89I [FACTION on FNAME ] or [NACTION on NFNAME]=&amp;srcfile archived as &amp;archivefile &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt;  |
| Explanation  |  • <a href="">FACTION</a>=ARCHIVE was used in a SEND command, which archived the file (FNAME) at end of the SEND transfer.<br/> • <a href="">NACTION</a>=ARCHIVE was used in a RECV command, which archived the file (NFNAME) at the end of the RECV transfer. This option is only available when using SFTP. |



============================== table nb count(108) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT90W"></span>CFTT90W IDF=&amp;idf IDT=&amp;idt [FACTION on FNAME ] or [NACTION on NFNAME]=&amp;fname : [erase or delete] failed cs<br/> CFTT90W IDF=&amp;idf IDT=&amp;idt [FACTION on FNAME ] or [NACTION on NFNAME]=&amp;fname : [erase or delete] failed cs |
| --- | --- |
| Explanation  | Failed to delete or erase the file (FNAME/NFNAME) and the transfer has completed (T state). This failure might occur if the file to be deleted or erased was being used, for example.<br/> When using the following commands:<br/> • SEND FACTION=ERASE or DELETE, the action occurs after the transfer completed.<br/> • RECV FACTION=ERASE or DELETE, the action occurs before the transfer.<br/> • RECV NACTION=DELETE, the action occurs after the transfer completed. Only available when using SFTP. |
| Action | Check the following:<br/> • FACTION: Manually delete or erase the remote file (FNAME).<br/> • NACTION: Manually delete the remote file (NFNAME). This option is only available when using SFTP. |
| Warning  | CFTT90W IDF=&amp;idf IDT=&amp;idt NARCHIVEFNAME undefined and NACTION=ARCHIVE  |
| Explanation  | If you have set NACTION=ARCHIVE, you must define the NARCHIVEFNAME.  |
| Action  | Define the NARCHIVEFNAME parameter. This parameter is only available when using SFTP.  |



============================== table nb count(109) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT91W"></span>CFTT91W PART=&amp;part IDS=&amp;ids Change direction(TURN) not supported by server<br/> CFTT91W Change direction (TURN) not supported by server PART=DMZ1 IDS=&amp;ids |
| --- | --- |
| Explanation | When using the DMZ mode, if the server does not accept the TURN, the session is closed by the requester without message. The IDS is the reference for this session context. |
| Action | This message is edited on LOG file. |



============================== table nb count(110) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT93W"></span> CFTT92I IDTU=&amp;idtu CTX=&amp;ctx IDT=&amp;idt<br/> CFTT92I &lt;IDTU=&amp;idtu CTX=&amp;ctx IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | Additional message for message CFTT57I, and is displayed only if ATM traces are activated.<br/> CTX=&amp;ctx provides the protocol context associated with the transfer. |



============================== table nb count(111) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT93W"></span>CFTT93W PART=&amp;part IDS=&amp;ids Negative ack not supported<br/> CFTT93W Negative ack not supported PART=&amp;part IDS=&amp;ids |
| --- | --- |
| Explanation | The final partner signals to the initial file sender that application errors were detected. This occurs via a negative acknowledgments sent in a PeSIT Hors SIT message, where IDS is the reference for the session context. |



============================== table nb count(112) ============================================


| V23 format<br/> V24 format<br/> Information  | <span id="CFTT94I"></span>CFTT94I PART=&amp;part IDF=&amp;idf IDT=&amp;idt FCHARSET=&amp;str NCHARSET=&amp;str<br/> CFTT94I &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt FCHARSET=&amp;str NCHARSET=&amp;str&gt; |
| --- | --- |
| Explanation  | This information message relates to the extended transcoding used for this transfer.  |



============================== table nb count(113) ============================================


| V23 format<br/> V24 format<br/> Error  | <span id="CFTT95E"></span>CFTT95E Incorrect user or password &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idtf DIAGI=&amp;diagi&gt;<br/> CFTT95E Incorrect user or password &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt DIAGI=&amp;diagi&gt; |
| --- | --- |
| Explanation  | Cannot connect to the SFTP server because the user name or password is incorrect.  |
| Action  | Correct the user name or password.  |



============================== table nb count(114) ============================================


| V23 format<br/> V24 format<br/> Information  | <span id="CFTT96I"></span> CFTT96I &amp;str transfer restarted &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt POS=&amp;pos IDS=&amp;ids&gt;<br/> CFTT96I &amp;str transfer restarted &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt POS=&amp;pos IDS=&amp;ids&gt; |
| --- | --- |
| Explanation  | The requester (&amp;str = requester) or the server (&amp;str = server) has restarted the transfer. &amp;pos is the file position during restart.  |



============================== table nb count(115) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT97E"></span>CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands&quot;,<br/> CFTT97E cmd prefix not allowed in procedure execution for SEND and RECV commands<br/>  |
| --- | --- |
| Explanation  |   |



============================== table nb count(116) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT98W"></span>CFTT98W PART=%-8.8s IDF=%-8.8s IDT=%.8s Rename ignored because WFNAME equals FNAME,<br/> CFTT98W Rename ignored because WFNAME equals FNAME &lt;IDTU=%.8s PART=%s IDF=%s IDT=%.8s&gt; |
| --- | --- |
| Explanation  | The configuration has the same WFNAME as the RECV FNAME and so the renaming is ignored.  |



============================== table nb count(117) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT01E"></span>CFTT01E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open mode not allowed<br/> CFTT01E IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Open mode not allowed |
| --- | --- |
| Explanation | A transfer request was made in OPEN mode, but this mode is not supported for the partner concerned. |
| Consequence | The transfer is denied. The corresponding catalog entry is set to the KEEP status. |
| Action | Transfer the files with this partner in closed mode. |



============================== table nb count(118) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT02E"></span>CFTT02E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Transfer Area Full<br/> CFTT02E _ Transfer Area Full &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | A new transfer request was made but the maximum number of transfers allowed at the same time has been reached. |
| Consequence | The transfer is not executed. |
| Action | Wait for a decrease in the number of transfers or increase the maximum number of authorized transfers (this increase can only be made by the technicians responsible for porting and customizing the Transfer CFT product). |



============================== table nb count(119) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT03E"></span>CFTT03E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Max retry Reached<br/> CFTT03E _ Max retry Reached &lt;IDTU=&amp;idtu PART=&amp;part IDF=&amp;idf IDT=&amp;idt&gt; |
| --- | --- |
| Explanation | The Transfer CFT has performed all retry actions to establish the link with the partner.<br/> • The transfer activation retry counter for this protocol has exceeded the value of the RESTART parameter (CFTPROT command) In this case there have been no other network connection attempts and there are no more protocols in this partner's protocol list In this case the DIAGI code is set to 406<br/> • The physical connection has resulted in an invalid network address. It is the last address for this protocol; there is no backup partner. The internal diagnostic code (DIAGI) is set to 405. When the catalog is displayed, it overrides the value 301 signifying an invalid address<br/> • The physical connection has resulted in a fatal network error. In this case the DIAGI code is set to 303; the DIAGP value defines the source of the error<br/> • The last physical connection attempted according to the values of the RETRYM, RETRYN and RETRYW parameters has failed. It is the last protocol in this partner's protocol list; there is no backup partner<br/> Note: the internal diagnostic code (DIAGI) is set to 405. When the catalog is displayed, it overrides the value 302 signifying a non-fatal network error. |
| Consequence | The transfer is refused. The corresponding catalog entry is set to the KEEP status. |
| Action | Determine the error according to the DIAGI value. Analyze the DIAGP code. |



============================== table nb count(120) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT05E"></span>CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart Failed<br/> CFTT05E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Restart Failed |
| --- | --- |
| Explanation | A file transfer restart request is not possible (the restart identifier is unknown, for example). |
| Consequence | The transfer is not restarted. |
| Action | Try a new transfer. |



============================== table nb count(121) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT06W"></span>CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner switching IPART=&amp;part<br/> CFTT06W PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Partner switching IPART=&amp;part |
| --- | --- |
| Explanation | The partner (&amp;part) cannot be reached within the authorized time slot (OMINTIME, OMAXTIME). |
| Consequence | The transfer will be retried via the intermediate partner IPART. |



============================== table nb count(122) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT07W"></span>CFTT07W Ending Transfer Task &amp;n Failed _ A transfer Running<br/> CFTT07W Ending Transfer Task &amp;n Failed _ A transfer Running |
| --- | --- |
| Explanation | Attempt to delete a transfer task for which not all transfers have been completed. &amp;n designates an internal Transfer CFT task number incremented each time a transfer task is activated. |



============================== table nb count(123) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT08E"></span>CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No prot available<br/> CFTT08E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _No prot available |
| --- | --- |
| Explanation | The maximum number of retries authorized for a transfer using the &amp;prot protocol has been reached (see the Transfer CFT CFTPROT RESTART parameter). |
| Consequence | The entry corresponding to the transfer in the catalog is set to KEEP. |
| Action | Analyze the causes of the broken communication link. |



============================== table nb count(124) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT09E"></span>CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Maximum cv affected<br/> CFTT09W PART=&amp;part IDF=&amp;idf IDT=&amp;idt PROT=&amp;prot _ Maximum cv affected |
| --- | --- |
| Explanation | All virtual circuits associated with a partner in server mode have already been allocated |
| Consequence | The transfer is refused locally. |
| Action | Wait for virtual circuits to be freed or increase the maximum number of virtual circuits (see the Transfer CFT Online documentation CNXIN and CNXINOUT parameters). |



============================== table nb count(125) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT10E"></span>CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not authorized<br/> CFTT10E PART=&amp;part PROT=&amp;prot _ Protocol not authorized |
| --- | --- |
| Explanation | The &amp;prot protocol is not authorized for this partner. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check Transfer CFT parameter settings. |



============================== table nb count(126) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT11E"></span>CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ &amp;net not found<br/> CFTT11EPART=&amp;part PROT=&amp;prot CLASS=&amp;n _ &amp;net not found |
| --- | --- |
| Explanation | The network characteristics associated with the partner and for the &amp;n class of resources have not been found in the Transfer CFT partner file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings. |



============================== table nb count(127) ============================================


| V23 format<br/> V24 format<br/> Warning | <span id="CFTT12W"></span>CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out of time to call<br/> CFTT12WPART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Out of time to call |
| --- | --- |
| Explanation | A transfer request was made outside the time slot authorized for this partner. |
| Consequence | The transfer is not executed (remains in the D state). |
| Action | Execute a new transfer within the time slot authorized for this partner. |



============================== table nb count(128) ============================================


| V23 format<br/> V24 format<br/> Information | <span id="CFTT13I"></span>CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host)<br/> CFTT13IPART=&amp;part (IDF=&amp;idf IDM=&amp;idm) IDT=&amp;idt _ Session parameters PROT=&amp;prot SAP=&amp;sap DIALNUM(or HOST)= &amp;dialnum (or &amp;host) |
| --- | --- |
| Explanation | Information message for each dialno (or host) switch and protocol. |



============================== table nb count(129) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT14E"></span>CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not found<br/> CFTT14E PART=&amp;part IDF=&amp;idf IDT=&amp;idt _ Not found |
| --- | --- |
| Explanation | The &amp;part partner was not found in the Transfer CFT partner file. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings.<br/> Check the {{&lt; TransferCFTtest/axwayvariablesComponentShortName &gt;}} parameter settings. |



============================== table nb count(130) ============================================


| V23 format<br/> V24 format<br/> Error | <span id="CFTT15E"></span>CFTT15E NPART=&amp;part _ Not found<br/> CFTT15E NPART Not found &lt;NPART=%s&gt; |
| --- | --- |
| Explanation  | The network identifier of the &amp;part partner was not found in the Transfer CFT partner file.  |
| Consequence  | The transfer is not executed. The corresponding catalog entry is set to KEEP.  |
| Action  | Check the Transfer CFT parameter settings.  |
| V23 format<br/> V24 format<br/> Error | CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters<br/> CFTT15E NPART=&amp;part _ Not found, possibly truncated to 24 characters |
| Explanation | The network identifier of the &amp;part partner was not found in the Transfer CFT partner file. A protocol limitation may have truncated the partner to 24 characters. |
| Consequence | The transfer is not executed. The corresponding catalog entry is set to KEEP. |
| Action | Check the Transfer CFT parameter settings and limit the partner ID to 24 characters.  |
