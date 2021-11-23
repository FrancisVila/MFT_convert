{
    "title": "FTP specific user exits",
    "linkTitle": "FTP specific exits",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Protocols

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <strong><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">using custom user exits</span>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

<span id="ExitFtpGetAppli"></span>

## Get Application object for FTP: ExitFtpGetAppli

### Purpose

This exit function is designed to use the Application if the Remote Site parameter <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>).

### Syntax

You can find this exit in the <span class="code">exitftp.c</span> source file. It has the following syntax:

int <span style="font-weight: bold;">ExitFtpGetAppli</span>(

          char **dest\_alias,  **/\* Remote Site \*/

          char **filename,  **/\* FTP file name \*/

          short **data\_code**,  /\* transfer data\_code \*/

          char **appli\_name,  **/\* Application from P\_APPLI site command \*/

          char **destination,  **/\* alias name of final destination \*/

          char **originator,  **/\* alias name of origin \*/

          char **buffer,  **/\* buffer to store Application name \*/

          int **len**);  /\* max buffer length \*/

 

If the Remote Site parameter <span style="font-weight: bold;">Application method</span> (<span class="code">get\_appli\_method</span>) is set to <span style="font-style: italic;">User exit</span> (<span style="font-style: italic;">AIE</span>), the Gateway server calls this function immediately after receiving an FTP <span class="code" style="font-weight: bold;">STOR</span> or <span class="code" style="font-weight: bold;">STOU</span> command.

The function gives an example using a look-up table from the transfer data code and destination alias name. The result must be stored in the <span class="code">buffer</span> parameter whose size is **len** bytes.

The function can return three values:

-   0: Application found and stored in the buffer parameter
-   1: No application found and the default FTP internal application is used
-   2: No application found and the transfer is rejected

<span id="ExitFtpSetReturnCode"></span>

## Customize FTP: ExitFtpSetReturnCode

### Purpose

This feature launches customized actions on receipt of an FTP command on the server side. It is implemented with a user exit function that is called for each FTP command received (except for <span class="code">USER</span>, <span class="code">PASS</span> and <span class="code">SYST</span>).

You can use the exit function to:

-   Let Gateway continue with its normal process
-   Supply a return code and message so that Gateway skips the command processing and responds immediately with the code and message supplied by the exit

Advantages of this feature:

-   It simulates a positive completion return code for commands that are not supported
-   It forces a negative completion return code for commands that are not permitted

### Syntax

You can find this exit in the <span class="code">exitftp.c</span> source file. It has the following syntax:

int <span style="font-weight: bold;">ExitFtpSetReturnCode</span>(

          int <span style="font-weight: bold;">ftp\_ref</span>,  /\* identifier of the FTP FT \*/

          char <span style="font-weight: bold;">ftp\_cmd</span>,  /\* received FTP command \*/

          int <span style="font-weight: bold;">ftp\_code</span>,  /\* response code to send \*/

          char <span style="font-weight: bold;">ftp\_msg</span>);  /\* response to send \*/

The return value of this function is always 0.

This table describes the input and output parameters:

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Type         </th>
<th class="HeadE-Column1-Header1">Parameters         </th>
<th class="HeadD-Column1-Header1">Comments         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Input</p>         </td>
         <td><p>ftp_ref</p>         </td>
         <td><p>Reference of the actual control connection for that command.</p>         </td>
      </tr>
      <tr>
         <td><p>ftp_cmd</p>         </td>
         <td><p>Full command received, including its parameters, but without CRLF.</p>         </td>
      </tr>
      <tr>
         <td><p>Output</p>         </td>
         <td><p>ftp_code</p>         </td>
         <td><p>Mandatory</p>
<p>States the code that must be returned in response to the above command:</p>
<ul>
<li>0: If the exit function allows Gateway to process the command normally</li>
<li>non-0: If the command will not be processed and Gateway will immediately respond with this <span class="code">ftp_code</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>ftp_msg</p>         </td>
         <td><p><span style="font-style: italic;">Optional</span> (only used if the returned ftp_code value is not 0)</p>
<p>In addition, if <span class="code">ftp_msg</span> does not contain any message (<span class="code">strlen(ftp_msg)</span> is 0), Gateway uses the standard message associated with the <span class="code">ftp_code</span>.</p>
<p>This parameter should be used with caution. The message must not exceed 200 characters.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="default_exit_example"></span>

### Default exit function examples

This is the code supplied by default with Gateway. It allows Gateway to operate as if there were no exit function.


    int ExitFtpSetReturnCode(int ftp_ref, char *ftp_cmd, 
                             int *ftp_code, char *ftp_msg)
    {
         *ftp_code = 0;
          ftp_msg[0] = 0;
     
    if (*ftp_code > 0)
       LogPrintf(LOG_INFO, "EXITFTP (%d) reply code set to %d for \ 
                     command \"%s\"\n", ftp_ref, *ftp_code, ftp_cmd);
     
    return(0);
    }

#### Example 1: Simulating a positive completion response

This example shows how to simulate a positive completion for commands that are not implemented in Gateway.


    int ExitFtpSetReturnCode(int ftp_ref, char *ftp_cmd,
                             int *ftp_code, char *ftp_msg)
    {
         *ftp_code = 0;
         ftp_msg[0] = 0;
     
         if (memcmp(ftp_cmd, "MKD", 3) == 0)
            *ftp_code = 257;
         else if (memcmp(ftp_cmd, "RMD", 3) == 0)
            *ftp_code = 250;
         else if (memcmp(ftp_cmd, "CWD", 3) == 0)
            *ftp_code = 250;
         else if (memcmp(ftp_cmd, "CDUP", 4) == 0)
            *ftp_code = 200;
         if (*ftp_code > 0)
            LogPrintf(LOG_INFO, "EXITFTP (%d) reply code set to %d for \
                      command \"%s\"\n", ftp_ref, *ftp_code, ftp_cmd);
     
       return(0);
    }

#### Example 2: Forcing a negative completion response

This example shows how to force a negative completion for some commands. If you decide that files should never be received on the Gateway server, a simple way to do this is to intercept <span class="code" style="font-weight: bold;">STOR</span> and <span class="code" style="font-weight: bold;">STOU</span> commands and respond with a 502 (command not implemented) or 532 (need account for storing file) return code. In addition, the <span class="code">ftp\_msg</span> parameter is used to reply with a non-standard message.


    int ExitFtpSetReturnCode(int ftp_ref, char *ftp_cmd, 
                             int *ftp_code, char *ftp_msg)
    {
       *ftp_code = 0;
       ftp_msg[0] = 0;
    if ((memcmp(ftp_cmd, "STOR", 4) == 0) ||
           (memcmp(ftp_cmd, "STOU", 4) == 0))
       {
          *ftp_code = 502;
          strcpy(ftp_msg, "Sorry this server does not accept \
                           store commands");
       }   
    if (*ftp_code > 0)
          LogPrintf(LOG_INFO, "EXITFTP (%d) reply code set to %d for \
                    command \"%s\"\n", ftp_ref, *ftp_code, ftp_cmd);
    return(0);
    }

Related topics

[Internal user exits](../../../customizing_gw_about/user_exits_about/user_exits_internal)

 

The topic contains information about the following FTP specific user exits:

-   [ExitFtpGetAppli](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitFtpGetAppli)
-   [ExitFtpSetReturnCode](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitFtpSetReturnCode)
-   [ExitFtpRespPasv](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitFtpRespPasv)
-   [ExitFtpCmdPort](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitFtpCmdPort)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
