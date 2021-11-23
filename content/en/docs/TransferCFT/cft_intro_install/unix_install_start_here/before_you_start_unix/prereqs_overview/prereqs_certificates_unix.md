{
    "title": "Certificates",
    "linkTitle": "Certificates",
    "weight": "190"
}Using the default certificates that are supplied with {{< TransferCFT/componentshortname  >}} is strongly discouraged in a production environment. You should use your own certificates to enhance security.

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
         <td>{{< TransferCFT/securerelayname  >}}         </td>
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
         <td>{{< TransferCFT/centralgovernancename  >}}         </td>
         <td>&lt;Transfer_CFT&gt;/runtime/conf/pki         </td>
         <td>passportCA.pem         </td>
         <td>November 2019         </td>
      </tr>
   </tbody>
</table>
