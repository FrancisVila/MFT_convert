{
    "title": "Sending a MESSAGE",
    "linkTitle": "Sending a MESSAGE",
    "weight": "250"
}# <span id="Sending_messages"></span>Send a message

You can use the SEND MESSAGE command to send a message to a designated partner, for example small amounts of content that are not considered sensitive content.

-   The message length in the PeSIT protocol has a maximum value of 4096 bytes
-   The message can be extracted from the Catalog file, and redirected to a specified file (fout parameter), using the DISPLAY command:

**Example**

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTUTIL SEND part=PART, idm=MSG, type=message, msg=’hello’            <p>CFTUTIL DISPLAY content=msg, fout=msgfile, direct=recv, idt=IDT</p>         </td>
      </tr>
   </tbody>
</table>

**Result**

The resulting msgfile will contain the message 'hello'.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">The <span>&lt;TransferCFTinstallation&gt;\runtime\conf</span> folder contains the <span>dspcnf.xml</span> file, a DISPLAY command template, which includes a specific filter <span>templatel id='msg'</span> that enables message extraction.         </td>
      </tr>
</table>

### Sending messages

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Parameters</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="25.296%">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/ida">IDA</a> </p>
         </td>
         <td width="74.704%">
            <p>Local transfer identifier assigned by the user or user application. 
 </p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="25.296%">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/idm">IDM</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="74.704%">
            <p>Message identifier.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="25.296%">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/part">PART</a> </p>
         </td>
         <td colspan="1" rowspan="1" width="74.704%">
            <p>Transfer partner identifier.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="25.296%">
            <p><a href="../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> = 
 MESSAGE</p>
         </td>
         <td colspan="1" rowspan="1" width="74.704%">
            <p>Characterizes a message send request.</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="25.296%">
            <p>OPTIONAL PARAMETERS 
 for  <a href="../send_command_basics">SEND</a></p>
         </td>
         <td colspan="1" rowspan="1" width="74.704%">
            <p>The optional common parameters form the SEND subset, used for sending a message (but not applicable to files).</p>
         </td>
      </tr>
   </tbody>
</table>

#### Example

A message using the identifier ANDREW.

<table cellspacing="0" width="90%">
   <col/>
      <tr>
         <td colspan="3" width="12%">
            <p>SEND</p>
            <p>IDM = ANDREW,</p>
            <p>MSG = ‘ANDREW: call PETER ’,</p>
         </td>
      </tr>
      <tr>
         <td width="12%">
            <p>PART = HQ,</p>
            <p>TYPE = MESSAGE,</p>
         </td>
      </tr>
</table>
