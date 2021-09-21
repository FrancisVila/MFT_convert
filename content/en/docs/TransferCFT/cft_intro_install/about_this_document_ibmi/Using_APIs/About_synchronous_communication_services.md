{
    "title": "Synchronous communication services",
    "linkTitle": "Synchronous communication services",
    "weight": "260"
}# <span id="Synchronous_communication_services"></span>Synchronous communication services

This topic describes Transfer CFT synchronous communication services.

## Description of functions

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Function</p>
</th>
         <th>
            <p>Use</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td colspan="1" rowspan="1">
            <p>COM</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Set the communication medium</p>
         </td>
      </tr>
      <tr>
         <td>
            <p>GETXINFO</p>
         </td>
         <td>
            <p>Retrieve information concerning the last transfer made 
 from a synchronous request after a request of the following types: SEND, 
 RECV, HALT, KEEP, START, RESUME, DELETE, END, SUBMIT, SWITCH, PURGE.</p>
            <p>The information is stored in a cftApiInf-type structure:</p>
            <ul>
               <li>Transfer 
 state                </li>
               <li>Diagnostic 
                </li>
               <li>Diagnostic 
 protocol                </li>
               <li>Value 
 of the PART field of CFTPARM                </li>
               <li>Transfer 
 identifier (IDT)                </li>
               <li>Local 
 transfer identifier (IDTU)                </li>
               <li>Transfer 
 type (single, cyclical, diffusion list, collection, file group)                </li>
               <li>Public 
 reference of the transfer (only for a single transfer in Send)               </li>
            </ul>
            <p>The GETXINFO action returns an error if the communication 
 medium is not synchronous.</p>
            <p>&amp;&amp;&amp; ïïï ùùù</p>
         </td>
      </tr>
   </tbody>
</table>
