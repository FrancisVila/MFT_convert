{
    "title": "FTP reply codes",
    "linkTitle": "FTP reply codes",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

## FTP code explanations

The RFC 959 reply codes are explained below:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>1yz</p>         </td>
         <td><p>Positive Preliminary reply</p>
<p>The requested action is being initiated. Expect another reply before proceeding with a new command. (The user-process sending another command before the completion reply would violate protocol, but server-FTP processes should queue any commands that arrive while a preceding command is in progress.)</p>
<p>This type of reply can be used to indicate that the command was accepted and the user-process may now recognize the data connections, for implementations where simultaneous monitoring is difficult.</p>
<p>The server-FTP process can send at most, one 1yz reply per command.</p>         </td>
      </tr>
      <tr>
         <td><p>2yz</p>         </td>
         <td><p>Positive Completion reply</p>
<p>The requested action has been successfully completed. A new request may be initiated.</p>         </td>
      </tr>
      <tr>
         <td><p>3yz</p>         </td>
         <td><p>Positive Intermediate reply</p>
<p>The command has been accepted, but the requested action is suspended, pending receipt of further information. The user should send another command specifying this information.</p>
<p>This reply is used in command sequence groups.</p>         </td>
      </tr>
      <tr>
         <td><p>4yz</p>         </td>
         <td><p>Transient Negative Completion reply</p>
<p>The command was not accepted and the requested action did not take place, but the error condition is temporary and the action may be requested again.</p>
<p>The user should return to the beginning of the command sequence, if any. It is difficult to assign a meaning to transient, particularly when two distinct sites (Server- and User-processes) have to agree on the interpretation.</p>
<p>Each reply in the 4yz category might have a slightly different time value, but the intent is that the user-process should try again. A rule of thumb in determining if a reply fits into the 4yz or the 5yz (Permanent Negative) category is that replies are 4yz if the commands can be repeated without any change in command form or in properties of the User or Server (for example, the command is spelled the same with the same arguments used; the user does not change his file access or user name; the server does not put up a new implementation).</p>         </td>
      </tr>
      <tr>
         <td><p>5yz</p>         </td>
         <td><p>Permanent Negative Completion reply</p>
<p>The command was not accepted and the requested action did not take place. The User-process is discouraged from repeating the exact request (in the same sequence).</p>
<p>Even some permanent error conditions can be corrected, so you may want to re-initiate the command sequence by direct action at some point in the future (for example, after the spelling has been changed, or the user has altered his directory status,...).</p>         </td>
      </tr>
   </tbody>
</table>

## Second digit definitions

The following function groupings are encoded in the second digit:

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>x0z</p>         </td>
         <td><p><strong>Syntax</strong></p>
<p>These replies refer to syntax errors, syntactically correct commands that do not fit any functional category. They are un-implemented or superfluous commands.</p>         </td>
      </tr>
      <tr>
         <td><p>x1z</p>         </td>
         <td><p>Information</p>
<p>These are replies to requests for information, such as status or help.</p>         </td>
      </tr>
      <tr>
         <td><p>x2z</p>         </td>
         <td><p>Connections</p>
<p>Replies referring to the control and data connections.</p>         </td>
      </tr>
      <tr>
         <td><p>x3z</p>         </td>
         <td><p>Authentication and accounting</p>
<p>Replies for the login process and accounting procedures.</p>         </td>
      </tr>
      <tr>
         <td><p>x4z</p>         </td>
         <td><p>File system</p>
<p>These replies indicate the status of the Server file system in relation to the requested transfer or other file system action.</p>         </td>
      </tr>
   </tbody>
</table>

## Third digit definitions

The third digit gives a finer gradation of meaning in each of the function categories.

<span id="FTP_reply_code_list"></span>

## FTP reply code list

The following is a list of FTP reply codes as defined in RFC 959, displayed in numeric order.

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">110</span></p>         </td>
         <td><p>Restart marker reply</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>In this case, the text is exact and not left to the particular implementation. It should read as follows:</p>
<p>MARK yyyy = mmmm</p>
<p>Where yyyy is User-process data stream marker, and mmmm server's equivalent marker (note the spaces between markers and "=").</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">120</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Service ready in nnn minutes.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">125</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Data connection already open; transfer starting.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">150</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File status ok; about to open data connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p>200</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Command is ok.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">202</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Command not implemented, superfluous at this site.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">211</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>System status, or system help reply.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">212</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Directory status.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">213</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>File status.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">214</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Help message on how to use the server, or the meaning of a particular non-standard command.  This reply is aimed at the user.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">215</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>NAME system type.</p>
<p>Where NAME is an official system name from the list in the Assigned Numbers document.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">220</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Service ready for new user.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">221</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Service closing control connection.</p>
<p>Logged out if appropriate.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">225</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Data connection open; no transfer in progress.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">226</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Closing data connection.</p>
<p>Requested file action successful (for example, file transfer or file abort).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">227</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Entering Passive Mode (h1,h2,h3,h4,p1,p2).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">230</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>User logged in, proceed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">250</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested file action ok, completed.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">257</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>"PATHNAME" created.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">331</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>User name ok, need password.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">332</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Need account for login.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">350</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested file action pending further information.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">421</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Service not available, closing control connection.</p>
<p>This may be a reply to any command if the service knows it must shut down.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">425</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Cannot open data connection.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">426</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Connection closed; transfer aborted.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">450</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested file action not taken.</p>
<p>File unavailable (for example, file busy).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">451</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested action aborted: local error in processing.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">452</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested action not taken.</p>
<p>Insufficient storage space in system.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">500</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Syntax error, command unrecognized.</p>
<p>This may include errors such as 'the command line is too long'.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">501</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Syntax error in parameters or arguments.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">502</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Command not implemented.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">503</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Bad sequence of commands.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">504</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Command not implemented for that parameter.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">530</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Not logged in.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">550</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested action not taken.</p>
<p>File unavailable (for example, file not found).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">551</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested action aborted: page type unknown.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">552</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested file action aborted.</p>
<p>Exceeded storage allocation (for current directory or dataset).</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;">553</span></p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Requested action not taken.</p>
<p>File name not allowed.</p>         </td>
      </tr>
   </tbody>
</table>

## Command-reply correspondence table

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">COMMAND         </th>
<th class="HeadE-Column1-Header1">SUCCESS         </th>
<th class="HeadD-Column1-Header1">FAIL         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>USER</p>         </td>
         <td><p>230,330</p>         </td>
         <td><p>430-432,500-505</p>         </td>
      </tr>
      <tr>
         <td><p>PASS</p>         </td>
         <td><p>230</p>         </td>
         <td><p>430-432,500-505</p>         </td>
      </tr>
      <tr>
         <td><p>BYE</p>         </td>
         <td><p>231,232</p>         </td>
         <td><p>430-432,500-505</p>         </td>
      </tr>
      <tr>
         <td><p>BYTE</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>SOCK</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>TYPE</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>MODE</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>RETR</p>         </td>
         <td><p>250</p>         </td>
         <td><p>450,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>Secondary Reply</p>         </td>
         <td><p>252</p>         </td>
         <td><p>452</p>         </td>
      </tr>
      <tr>
         <td><p>STOR</p>         </td>
         <td><p>250</p>         </td>
         <td><p>451,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>Secondary Reply</p>         </td>
         <td><p>252</p>         </td>
         <td><p>452,453</p>         </td>
      </tr>
      <tr>
         <td><p>APPE</p>         </td>
         <td><p>250</p>         </td>
         <td><p>451,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>Secondary Reply</p>         </td>
         <td><p>252</p>         </td>
         <td><p>452,453</p>         </td>
      </tr>
      <tr>
         <td><p>RNFR</p>         </td>
         <td><p>200</p>         </td>
         <td><p>450,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>RNTO</p>         </td>
         <td><p>253</p>         </td>
         <td><p>450,451,500-505</p>         </td>
      </tr>
      <tr>
         <td><p>DELE</p>         </td>
         <td><p>254</p>         </td>
         <td><p>450,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>LIST</p>         </td>
         <td><p>250</p>         </td>
         <td><p>450,453,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>Secondary Reply</p>         </td>
         <td><p>252</p>         </td>
         <td><p>452</p>         </td>
      </tr>
      <tr>
         <td><p>ALLO</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>STAT</p>         </td>
         <td><p>100,150,151</p>         </td>
         <td><p>450,451,500-506</p>         </td>
      </tr>
      <tr>
         <td><p>REST</p>         </td>
         <td><p>200</p>         </td>
         <td><p>500-506</p>         </td>
      </tr>
      <tr>
         <td><p>ABOR</p>         </td>
         <td><p>201,202</p>         </td>
         <td><p>500-505</p>         </td>
      </tr>
      <tr>
         <td><p>Spontaneous Replies</p>         </td>
         <td><p>0xx,300,301,</p>
<p>251,255</p>         </td>
         <td><p>400,401,434-436</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
