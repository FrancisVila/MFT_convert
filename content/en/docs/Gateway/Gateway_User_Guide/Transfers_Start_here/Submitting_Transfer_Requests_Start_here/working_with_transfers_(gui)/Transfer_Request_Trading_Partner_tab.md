{
    "title": "New Transfer Request: Trading Partner tab",
    "linkTitle": "Trading Partner tab",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

Only use this tab for: S/MIME, EDIINT, RosettaNet or OFTP R2.0.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Destination partner</p>         </td>
         <td><p>Enter the Trading Partner name that is the file destination.</p>         </td>
      </tr>
      <tr>
         <td><p>Originator partner</p>         </td>
         <td><p>Enter the Trading Partner name that is the file originator.</p>         </td>
      </tr>
      <tr>
         <td><p>Format</p>         </td>
         <td><p>Select the trading format:</p>
<ul>
<li>SMIME</li>
<li>AS1</li>
<li>AS2</li>
<li>AS3</li>
<li>RosettaNet</li>
<li><span style="font-weight: bold;">CMS</span> (for OFTP R2.0)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Is signing</p>         </td>
         <td><p>Select the signing option:</p>
<ul>
<li>Yes</li>
<li>No</li>
<li>(empty)<span style="font-weight: normal;"> = use the value set in the destination Trading Partner</span></li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Is compressing</p>         </td>
         <td><p>Select the compressing option:</p>
<ul>
<li>Yes</li>
<li>No</li>
<li><span style="font-weight: bold;">(empty)</span> = use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Is encrypting</p>         </td>
         <td><p>Select the encryption (ciphering) method:</p>
<ul>
<li>Yes</li>
<li>No</li>
<li><span style="font-weight: bold;">(empty)</span> = use the value set in the destination Trading Partner</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Receipt request</p>         </td>
         <td><p>Select the receipt request option:</p>
<ul>
<li>Signed</li>
<li>Unsigned</li>
<li>None</li>
<li><span style="font-weight: bold;">Undefined</span> = use the value set in the destination Trading Partner</li>
</ul>
<p><span style="font-weight: bold;">Note:</span> Only the S/MIME protocol allows the sending of a signed receipt.</p>         </td>
      </tr>
      <tr>
         <td><p>Synchronize receipt</p>         </td>
         <td><p>Only available for AS2 transfers if acknowledgment request is set to <span style="font-weight: bold;">Signed</span> or <span style="font-weight: bold;">Unsigned</span>.</p>
<p>Select this option if a synchronized receipt must be requested.</p>         </td>
      </tr>
      <tr>
         <td><p>Receipt url/email</p>         </td>
         <td><p>Not Available for S/MIME protocol</p>
<p>Enter the receipt response target address. If you do not complete this field, the default value is the originator name.</p>         </td>
      </tr>
      <tr>
         <td><p>Content-type</p>         </td>
         <td><p>Enter the content type to use when sending an EDI or S/MIME file.</p>
<p>For example:</p>
<ul>
<li>application/EDIFACT</li>
<li>application/XML</li>
<li>text/plain</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Working with File Transfer Requests](../)

[Transfers: Parameters List](../../working_with_transfers_cli/transfer_req_parameter_list)

[About EDIINT](../../../../protocols_about/ediint_about)

[About RosettaNet](../../../../protocols_about/rosettanet_about)

[About OFTP](../../../../protocols_about/oftp_about)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
