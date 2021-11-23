{
    "title": "Post Office Protocol (POP3)",
    "linkTitle": "POP3",
    "weight": "370"
}{{< Gateway/componentlongname  >}}: Messages and codes

This topic lists POP3 log messages.

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="POP001I"></span>001</p>         </td>
         <td><p><strong>POP I CONN_REQ %1(%2) [%3] connection request: user=%4</strong></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating that the user issued a connection request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The login user ID</p>         </td>
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
         <td><p><span id="POP002I"></span>002</p>         </td>
         <td><p><span style="font-weight: bold;">POP I CONN_ACK %1(%2) [%3] connection established. %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The POP3 server has accepted the connection request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the transfer request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The welcome message as sent by the POP3 server</p>         </td>
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
         <td><p><span id="POP003I"></span>003</p>         </td>
         <td><p><span style="font-weight: bold;">POP I USER_ACK %1(%2) [%3] login accepted. %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The POP3 server has accepted the login request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The reply message as sent by the POP3 server</p>         </td>
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
         <td><p><span id="POP004E"></span>004</p>         </td>
         <td><p><span style="font-weight: bold;">POP E USER_NAK %1(%2) [%3] login refused. %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The POP3 server has refused the login request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The reply message as sent by the POP3 server</p>         </td>
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
         <td><p><span id="POP010I"></span>010</p>         </td>
         <td><p><span style="font-weight: bold;">POP I RECV_CNT %1(%2) [%3] %4 mails available</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the number of emails available</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The mail count as sent by the POP3 server</p>         </td>
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
         <td><p><span id="POP011I"></span>011</p>         </td>
         <td><p><span style="font-weight: bold;">POP I RECV_IND %1(%2) [%3] beginning of reception From:%4 To:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the beginning of a mail reception cycle</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the email</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the email</p>         </td>
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
         <td><p><span id="POP012I"></span>012</p>         </td>
         <td><p><span style="font-weight: bold;">POP I RECV_IND %1(%2) [%3] beginning of reception, mailtype=%4, appli=%5, file=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the beginning of a mail reception cycle</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The type of mail (XFER, MAIL, DATA or REPORT)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The name of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> application used</p>         </td>
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
         <td><p><span id="POP013I"></span>013</p>         </td>
         <td><p><span style="font-weight: bold;">POP I RECV_END %1(%2) [%3] end of reception From:%4 To:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the end of a mail reception cycle</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the mail</p>         </td>
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
         <td><p><span id="POP014I"></span>014</p>         </td>
         <td><p><span style="font-weight: bold;">POP I RECV_END %1(%2) [%3] end of reception, mailtype=%4, appli=%5, file=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the end of a mail reception cycle.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The type of mail (XFER, MAIL, DATA or REPORT)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The name of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> application used</p>         </td>
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
         <td><p><span id="POP015E"></span>015</p>         </td>
         <td><p><span style="font-weight: bold;">POP E RECV_ERR %1(%2) [%3] error of reception From:%4 To:%5, reason=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that an error occurred during the mail reception phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Text describing the nature of the error</p>         </td>
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
         <td><p><span id="POP016E"></span>016</p>         </td>
         <td><p><span style="font-weight: bold;">POP E RECV_ERR %1(%2) [%3] error of reception, mailtype=%4, appli=%5, file=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that an error occurred during the mail reception phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The type of mail (XFER, MAIL, DATA or REPORT)</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The name of the <span class="mc-variable axway_variables.Company_Name variable">Axway</span> application used</p>         </td>
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
         <td><p><span id="POP017E"></span>017</p>         </td>
         <td><p><span style="font-weight: bold;">POP E XFER_ERR %1(%2) [%3] transfer refused. duplicate transfer. From:%4 To:%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A duplicated mail was detected during the mail reception phase.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the mail</p>         </td>
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
         <td><p><span id="POP018E"></span>018</p>         </td>
         <td><p><span style="font-weight: bold;">POP E XFER_ERR %1(%2) [%3] transfer refused. From:%4 To:%5 reason=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that mail reception was aborted due to a detected error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>Text describing the nature of the error</p>         </td>
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
         <td><p><span id="POP019I"></span>019</p>         </td>
         <td><p><span style="font-weight: bold;">POP I TERM_IND %1(%2) [%3] Session terminated by remote site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The POP3 server terminated the reception session. Message indicating that the reception session is terminated by the POP3 server.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP020I"></span>020</p>         </td>
         <td><p><span style="font-weight: bold;">POP I TERM_REQ %1(%2) [%3] Session terminated by local site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The POP3 client terminated the reception session. Message indicating that the reception session is terminated by the POP3 client</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP021I"></span>021</p>         </td>
         <td><p><span style="font-weight: bold;">POP I XFER_ACK %1(%2) ACK: xfer=%3 from=%4 to=%5</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating that a mail acknowledgment was received</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>The mail identification</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The sender of the mail</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The receiver of the mail</p>         </td>
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
         <td><p><span id="POP022I"></span>022</p>         </td>
         <td><p><span style="font-weight: bold;">POP I XFER_ACK %1(%2) ACK: %3 (%4)</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating that a mail acknowledgment was received</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>acknowledgment type</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>acknowledgment action</p>         </td>
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
         <td><p><span id="POP023W"></span>023</p>         </td>
         <td><p><span style="font-weight: bold;">POP W XFER_REC %1(%2) [%3] Start recovery. reason=%4, diag=%5, err=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating the start of the recovery process for a previous mail reception failure</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The supervisor refusal reason</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>The last POP3 diagnostic code</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>The last system error code</p>         </td>
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
         <td><p><span id="POP024W"></span>024</p>         </td>
         <td><p><span style="font-weight: bold;">POP W XFER_REC %1(%2) [%3] Error or duplicate. Mail left on server</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Message indicating that an error or duplicated mail was detected and left intact on the POP3 server</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP025W"></span>025</p>         </td>
         <td><p><span style="font-weight: bold;">POP W XFER_REC %1(%2) [%3] Error or duplicate. Mail deleted from server</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error or duplicated mail has been detected and then deleted from the POP3 server</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP030E"></span>030</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERORR %1(%2) [%3] memory allocation error. reason=%4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that a system memory allocation API error was detected</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Text describing the failure context</p>         </td>
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
         <td><p><span id="POP031E"></span>031</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] SFM error. reason=%4, diag=%5, errno=%6</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that a system file management API error was detected</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Text describing the failure context</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Diagnostic code</p>         </td>
      </tr>
      <tr>
         <td><p>6</p>         </td>
         <td><p>System error code</p>         </td>
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
         <td><p><span id="POP032E"></span>032</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] timeout</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error message indicating that an inactivity timeout occurred</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP033E"></span>033</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] Transfer aborted by local site</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The mail reception process was aborted due to an unrecoverable error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP034E"></span>034</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] Transfer aborted by SUP: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The mail reception process was aborted on Supervisor request</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Text describing the abort reason</p>         </td>
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
         <td><p><span id="POP035E"></span>035</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] internal protocol error</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The mail reception process was aborted due to an unrecoverable POP3 protocol error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP036E"></span>036</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The mail reception process was aborted due to an unrecoverable MIME parsing error</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Text detailing the MIME parser error context</p>         </td>
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
         <td><p><span id="POP037E"></span>037</p>         </td>
         <td><p><span style="font-weight: bold;">POP E ERROR %1(%2) [%3] recovery fails</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The attempted recovery process failed. The mail will either be deleted from or left intact on the POP3 server, depending on the Remote Site definition</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
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
         <td><p><span id="POP040I"></span>040</p>         </td>
         <td><p><span style="font-weight: bold;">POP I TRACE %1(%2) [%3] CMMD: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message for the POP3 protocol exchange</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The command text as sent by the client</p>         </td>
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
         <td><p><span id="POP041I"></span>041</p>         </td>
         <td><p><span style="font-weight: bold;">POP I TRACE %1(%2) [%3] RESP: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message for the POP3 protocol exchange</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The response text as sent by the server</p>         </td>
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
         <td><p><span id="POP042I"></span>042</p>         </td>
         <td><p><span style="font-weight: bold;">POP I TRACE %1(%2) [%3] DATA: %4</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Trace message for the POP3 protocol exchange</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Remote Site name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Internal context number associated with the transfer</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>Local identification of the Transfer Request</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>The data text as sent by the server</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
