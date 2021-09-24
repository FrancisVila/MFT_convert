{
    "title": "Certificates ",
    "linkTitle": "Certificates ",
    "weight": "210"
}Using the default certificates that are supplied with Transfer CFT is strongly discouraged in a production environment. You should use your own certificates to enhance security.

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Type</th>
         <th>Location</th>
         <th>Certificate </th>
         <th>Expires</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><span>Secure Relay</span>
         </td>
         <td>&lt;Transfer_CFT&gt;/home/distrib/xsr         </td>
         <td>
            <p>SecureRelayCA.pem </p>
         </td>
         <td>November 2021         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>          </td>
         <td>SecureRelayMasterAgent.p12         </td>
         <td>November 2021         </td>
      </tr>
      <tr>
         <td><span>Central Governance</span>
         </td>
         <td>&lt;Transfer_CFT&gt;/runtime/conf/pki         </td>
         <td>passportCA.pem         </td>
         <td>November 2019         </td>
      </tr>
   </tbody>
</table>
