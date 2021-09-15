{
    "title": "Configure PeSIT server settings",
    "linkTitle": "Configure PeSIT server settings",
    "weight": "140"
}Use the *PeSIT Settings* page to configure the PeSIT protocol server.

1.  Select **Setup > PeSIT Settings**.  
    The *PeSIT Settings* page is displayed.

2.  Provide the information as described in the following table:  
    

    <table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Name</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="2">Settings         </td>
      </tr>
      <tr>
         <td>
            <p>Enable Segmentation</p>
         </td>
         <td>If a data article (record) is larger than the maximum size, it is sent in multiple FPDUs (messages).         </td>
      </tr>
      <tr>
         <td>
            <p>Enable multiple records</p>
         </td>
         <td>If more than one data article fits in a FPDU, they are sent in one FPDU.         </td>
      </tr>
      <tr>
         <td>
            <p>Enable Concatenation</p>
         </td>
         <td>Allow several FPDUs to be sent in one TCP message unit.         </td>
      </tr>
      <tr>
         <td>
            <p>Maximum Connections Number</p>
         </td>
         <td>The maximum number of concurrent TCP connections remote PeSIT servers can make.         </td>
      </tr>
      <tr>
         <td>
            <p>Maximum Sessions Number</p>
         </td>
         <td>The maximum number of concurrent sessions remote PeSIT servers can make.         </td>
      </tr>
      <tr>
         <td colspan="2">Timeouts         </td>
      </tr>
      <tr>
         <td>
            <p>Create and Select</p>
         </td>
         <td>For connections initiated by a remote PeSIT server, the time in seconds that <span>SecureTransport</span> waits for a PeSIT F.CREATE or a F.SELECT command before <span>SecureTransport</span> closes the connection.         </td>
      </tr>
      <tr>
         <td>
            <p>Inactivity</p>
         </td>
         <td>
            <p>For connections initiated by a remote PeSIT server, the time in seconds that a connection may be inactive before <span>SecureTransport</span> closes it.</p>
            <p> </p>
         </td>
      </tr>
      <tr>
         <td>
            <p>Connection Release</p>
         </td>
         <td>For connections initiated by a remote PeSIT server, the time in seconds that <span>SecureTransport</span> waits for a response to a PeSIT F.RELEASE command before <span>SecureTransport</span> closes it.         </td>
      </tr>
   </tbody>
</table>

3.  Click **Update**.

4.  On the *Server Control* page, restart the PeSIT server.
