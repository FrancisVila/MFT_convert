{
    "title": "Incompatibilities",
    "linkTitle": "Incompatibilities",
    "weight": "60"
}This section describes the upgrade paths and incompatibilities and between SecureTransport5.5 and:

-   Other products that you may be using with previous versions.
-   Earlier versions of SecureTransport.

<span id="UpgradePaths"></span>The supported upgrade paths are:

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
<th rowspan="2">SecureTransport version<br/>(Appliance Platform version)</th>
<th colspan="2">Upgrade path</th>
      </tr>
      <tr>
         <th>Prerequisites</th>
         <th>Upgrade Steps</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>
            <p>ST 5.2.1 SP9 </p>
            <p>(AP 6.7.0)</p>
         </td>
         <td>none         </td>
         <td>
<ol>
               <li value="1">Remove ST 5.2.1 SP9               </li>
               <li value="2">ST 5.3.0 GA (AP 6.7.1)               </li>
               <li value="3">ST 5.3.0 Patch 14 (AP 6.7.1)               </li>
               <li value="4">ST 5.3.1 GA (AP 7.0.1)               </li>
               <li value="5">ST 5.3.3 GA (AP 7.0.1)               </li>
               <li value="6">ST 5.3.6 GA (AP 7.1.1)               </li>
               <li value="7">ST 5.4 GA (AP 7.1.1)               </li>
               <li value="8">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="9">ST 5.5 GA (ST 5.5 Virtual Appliance)
							               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.2.1 any SP up to SP8 </p>
            <p>(AP 6.7.0)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.2.1 SP 8 </p>
            <p>(AP 6.7.0)</p>
         </td>
         <td>
<ol>
               <li value="1">ST 5.3.0 GA (AP 6.7.1)               </li>
               <li value="2">ST 5.3.0 Patch 14 (AP 6.7.1)               </li>
               <li value="3">ST 5.3.1 GA (AP 7.0.1)               </li>
               <li value="4">ST 5.3.3 GA (AP 7.0.1)               </li>
               <li value="5">ST 5.3.6 GA (AP 7.1.1)               </li>
               <li value="6">ST 5.4 GA (AP 7.1.1)               </li>
               <li value="7">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="8">ST 5.5 GA (ST 5.5 Virtual Appliance)               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.3.0 any patch level </p>
            <p>(AP 6.7.1)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.3.0 latest patch </p>
            <p>(AP 6.7.1)</p>
         </td>
         <td>
<ol>
               <li value="1">ST 5.3.1 GA (AP 7.0.1)               </li>
               <li value="2">ST 5.3.3 GA (AP 7.0.1)               </li>
               <li value="3">ST 5.3.6 GA (AP 7.1.1)               </li>
               <li value="4">ST 5.4 GA (AP 7.1.1)               </li>
               <li value="5">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="6">ST 5.5 GA (ST 5.5 Virtual Appliance)               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.3.1 any patch level </p>
            <p>(AP 7.0.0)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.3.1 latest patch </p>
            <p>(AP 7.0.0)</p>
         </td>
         <td>
<ol>
               <li value="1">ST 5.3.3 GA (AP 7.0.1)               </li>
               <li value="2">ST 5.3.6 GA (AP 7.1.1)               </li>
               <li value="3">ST 5.4 GA (AP 7.1.1)               </li>
               <li value="4">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="5">
								ST 5.5 GA (ST 5.5 Virtual Appliance)
							               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.3.3 any patch level </p>
            <p>(AP 7.0.1)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.3.3 latest patch </p>
            <p>(AP 7.0.1)</p>
         </td>
         <td>
<ol>
               <li value="1">ST 5.3.6 GA (AP 7.1.1)
               </li>
               <li value="2">ST 5.4 GA (AP 7.1.1)
							               </li>
               <li value="3">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="4">
								ST 5.5 GA (ST 5.5 Virtual Appliance)
							               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.3.5 any patch level </p>
            <p>(AP 7.0.3)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.3.5 RA latest patch </p>
            <p>(AP 7.0.3)</p>
         </td>
         <td>
<ol>
               <li value="1">ST 5.3.6 GA (AP 7.1.1)
               </li>
               <li value="2">ST 5.4 GA (AP 7.1.1)
               </li>
               <li value="3">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="4">
								ST 5.5 GA (ST 5.5 Virtual Appliance)
							               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.3.6 any patch level </p>
            <p>(AP 7.1.1)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.3.6 latest patch </p>
            <p>(AP 7.1.1)</p>
         </td>
         <td>
<ol>
               <li value="1"> ST 5.4 GA (AP 7.1.1)               </li>
               <li value="2">ST 5.4 Latest Patch (AP 7.2.0)               </li>
               <li value="3">
								ST 5.5 GA (ST 5.5 Virtual Appliance)
							               </li>
</ol>
         </td>
      </tr>
      <tr>
         <td>
            <p>ST 5.4 any patch level</p>
            <p>(AP 7.1.1)</p>
         </td>
         <td>
            <p>Upgrade to ST 5.4 latest patch </p>
            <p>(AP 7.2.0)</p>
         </td>
         <td>ST 5.5 GA (ST 5.5 Virtual Appliance)         </td>
      </tr>
   </tbody>
</table>

Review the upgrade information for older SecureTransport versions in Axway Support at [SecureTransport documentation](https://support.axway.com/en/search/index/type/Documentation/sort/created%7Cdesc/ipp/50/product/COMPAX012416/category/Installation+and+Prerequisites). Upgrade from ST 5.2.1 SP 9 to 5.4 (and any version) is not possible, as it would result in data loss. In case of questions, contact Axway Global Support at [support.axway.com](http://support.axway.com/).

**Notes:**

-   For a complete list of supported software, refer to **Axway and third-party software support** in the in the *SecureTransport Administrator's Guide*.
-   On upgrade to SecureTransport 5.5, ciphers are added to and removed from the existing cipher sets. For the SecureTransport 5.5 list of ciphers, refer to **SecureTransport cipher suites** in the *SecureTransport Security Guide*.
-   After upgrade to SecureTransport 5.5, when a proxy is configured, direct connections from the SecureTransport Backend are not permitted even when the proxy is unreachable. To change the default behavior, set the `Direct.Connection.When.Proxy.Down` server configuration parameter to **true**. For information on changing server configuration parameters, refer to **View and change server configuration parameters** in the *SecureTransport Administrator's Guide*.
-   In SecureTransport 5.3.3 there is a structural change of database tables related to File Tracking. The data related to file transfers made before upgrade, should be migrated to the new tables created after upgrade to SecureTransport 5.3.3 for them to be visible in File Tracking for SecureTransport 5.3.3 and above. If the migration is skipped, all the details related to the file transfers made before the upgrade will NOT be visible on the Administration Tool *File Tracking* page. For more information, refer to **Migration of File Tracking entries after upgrade** in the *SecureTransport 5.4 Installation Guide*.
