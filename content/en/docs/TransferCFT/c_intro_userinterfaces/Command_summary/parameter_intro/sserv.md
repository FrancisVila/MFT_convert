{
    "title": "sserv",
    "linkTitle": "sserv",
    "weight": "3340"
}### **<span id="sserv"></span>sserv**

#### **CFTPROT**

**\[SSERV = {see table below | *identifier*}\]**

Identifies the service, or protocol
variant, required of the incoming partner.

Its value is conveyed in the LOGON message of the PeSIT protocol. This
parameter should only be specified for the CFT profile, or Extern profile
as applicable, in certain specific cases.

Some products, as shown below, use this parameter as a protocol selector
for incoming calls.

<span id="sserv_parameter_details"></span>Sserv parameter details

<table data-border="1" data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>PeSIT profile</th>
         <th>Details</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td data-valign="top" width="29%">            <p>PeSIT ANY  </p>         </td>
         <td data-valign="top" width="71%">            <p>The SSERV = GSIT value is used in requester mode for exchanges via TCP/IP.<br />
Use of this parameter value does not affect the message, which contains
the "PeSIT" value. </p>         </td>
      </tr>
      <tr class="even">
         <td data-valign="top" width="29%">            <p>PeSIT SIT</p>         </td>
         <td data-valign="top" width="71%">            <p>The default value is: SSERV = ‘ ’ as this parameter is ineffective.
In the SIT profile, there is no Log in message.</p>         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../)

 
