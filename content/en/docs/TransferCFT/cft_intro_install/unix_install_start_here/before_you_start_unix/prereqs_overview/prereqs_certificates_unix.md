{
    "title": "Certificates",
    "linkTitle": "Certificates",
    "weight": "190"
}Using the default certificates that are supplied with <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is strongly discouraged in a production environment. You should use your own certificates to enhance security.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt">Type         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt">Location         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1" style="font-size: 9pt">Certificate         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1" style="font-size: 9pt">Expires         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span class="mc-variable suite_variables.SecureRelayName variable">Secure Relay</span>         </td>
         <td>&lt;Transfer_CFT&gt;/home/distrib/xsr         </td>
         <td><p>SecureRelayCA.pem</p>         </td>
         <td>November 2021         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>SecureRelayMasterAgent.p12         </td>
         <td>November 2021         </td>
      </tr>
      <tr>
         <td><span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>         </td>
         <td>&lt;Transfer_CFT&gt;/runtime/conf/pki         </td>
         <td>passportCA.pem         </td>
         <td>November 2019         </td>
      </tr>
   </tbody>
</table>
