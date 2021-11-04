{
    "title": "Send  a message",
    "linkTitle": "Sending a MESSAGE",
    "weight": "240"
}You can use the SEND MESSAGE command to send a message to a designated partner, for example small amounts of content that are not considered sensitive content.

-   The message length in the PeSIT protocol has a maximum value of 4096 bytes
-   The message can be extracted from the Catalog file, and redirected to a specified file (fout parameter), using the DISPLAY command:

**Example**


    CFTUTIL SEND part=PART, idm=MSG, type=message, msg=’hello’CFTUTIL DISPLAY content=msg, fout=msgfile, direct=recv, idt=IDT

**Result**

The resulting msgfile will contain the message 'hello'.

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The <span class="code">&lt;TransferCFTinstallation&gt;\runtime\conf</span> folder contains the <span class="code">dspcnf.xml</span> file, a DISPLAY command template, which includes a specific filter <span class="code">templatel id='msg'</span> that enables message extraction.         </td>
      </tr>
   </tbody>
</table>

### Sending messages

<table>
   <th>
      <tr>
<th><p>Parameters</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ida">IDA</a> </p>         </td>
         <td><p>Local transfer identifier assigned by the user or user application.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idm">IDM</a> </p>         </td>
         <td><p>Message identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a> </p>         </td>
         <td><p>Transfer partner identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> =
MESSAGE</p>         </td>
         <td><p>Characterizes a message send request.</p>         </td>
      </tr>
      <tr>
         <td><p>OPTIONAL PARAMETERS
for <a href="../send_command_basics">SEND</a></p>         </td>
         <td><p>The optional common parameters form the SEND subset, used for sending a message (but not applicable to files).</p>         </td>
      </tr>
   </tbody>
</table>

#### Example

A message using the identifier ANDREW.


    SEND
    IDM = ANDREW,
    MSG = ‘ANDREW: call PETER ’,


    PART = HQ,
    TYPE = MESSAGE,