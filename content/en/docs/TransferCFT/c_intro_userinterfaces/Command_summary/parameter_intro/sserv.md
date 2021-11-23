{
    "title": "sserv",
    "linkTitle": "sserv",
    "weight": "3310"
}### **<span id="sserv"></span>**sserv****

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

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">PeSIT profile         </th>
<th class="HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>PeSIT ANY  </p>         </td>
         <td><p>The SSERV = GSIT value is used in requester mode for exchanges via TCP/IP.<br />
Use of this parameter value does not affect the message, which contains
the "PeSIT" value. </p>         </td>
      </tr>
      <tr>
         <td><p>PeSIT SIT</p>         </td>
         <td><p>The default value is: SSERV = ‘ ’ as this parameter is ineffective.
In the SIT profile, there is no Log in message.</p>         </td>
      </tr>
   </tbody>
</table>

 

[Return to Command index](../../)

 
