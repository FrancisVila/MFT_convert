{
    "title": "Configuring X.400 O/R address",
    "linkTitle": "X.400 O/R Address",
    "weight": "220"
}{{< Gateway/componentlongname  >}}: Configuration

The *O/R Address* window is displayed if you click **Edit...** in:

-   The configuration menu
-   Remote Site
-   Transfer Request

Message originators and recipients within X.400 are identified by their O/R address. The O/R address consists of a number of mandatory and optional address attributes. These attributes are organized hierarchically.

Specify the O/R address by modifying the address attributes in the <span style="font-style: italic;">X.400 O/R Address</span> window. Only use [valid characters](#valid_characters) in the O/R address, as listed in this topic.

<span style="font-weight: bold;">Note:</span> Not all fields are used for all objects. In this case they are grayed out.

<span id="olh_general"></span>

## General tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Country (C)</p>         </td>
         <td><p>Identifies the Country.</p>         </td>
      </tr>
      <tr>
         <td><p>ADMD (A)</p>         </td>
         <td><p>Administration Domain Name. Identifies an ADMD relative to the country specified by the Country Name. An ADMD provides a public messaging service within a single country. Several ADMDs may exist within a Country.</p>         </td>
      </tr>
      <tr>
         <td><p>PRMD (P)</p>         </td>
         <td><p>Private Domain Name. Identifies a PRMD relative to the ADMD or the Country. A PRMD is a messaging service within an organization. The ADMD operator must uniquely assign the Name of the Private Domain if the PRMD is connected to an ADMD service.</p>         </td>
      </tr>
      <tr>
         <td><p>Organization (O)</p>         </td>
         <td><p>Identifies an organization relative to the PRMD.</p>         </td>
      </tr>
      <tr>
         <td><p>Org. Unit 1 (OU1)</p>         </td>
         <td><p>Organization Unit Name 1-4.</p>
<p>Can be used up to four times to identify divisions/departments within the organization.</p>
<p>The names appear in order of importance. Always start with Org. Unit 1. You cannot enter an Org. Unit 2 unless you enter an Org. Unit 1 first, and so on.</p>         </td>
      </tr>
      <tr>
         <td><p>Org. Unit 2 (OU2)</p>         </td>
      </tr>
      <tr>
         <td><p>Org. Unit 3 (OU3)</p>         </td>
      </tr>
      <tr>
         <td><p>Org. Unit 4 (OU4)</p>         </td>
      </tr>
      <tr>
         <td><p>Common name (CN)</p>         </td>
         <td><p>Identifies a user, an application, or a distribution list.</p>
<p><span style="font-weight: bold;">Caution:</span> Common name is not supported in MTA version 84. You may encounter problems if your MTA is routed via a version 84 MTA.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_personal"></span>

## Personal tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Surname (S)</p>         </td>
         <td><p>The Surname is a mandatory part of the Personal Name.</p>         </td>
      </tr>
      <tr>
         <td><p>Given name (G)</p>         </td>
         <td><p>The Given Name is an optional part of the Personal Name.</p>         </td>
      </tr>
      <tr>
         <td><p>Initials (I)</p>         </td>
         <td><p>The Initials are an optional part of the Personal Name.</p>         </td>
      </tr>
      <tr>
         <td><p>Generation Qual (Q)</p>         </td>
         <td><p>The Generation qualifier is an optional part of the Personal Name.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_domain_defined"></span>

## Domain defined tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Type (DDA)</p>         </td>
         <td><p>The Domain-defined attributes are specific to a messaging domain and are used to pass non-standard information. These attributes are used in addition to those that specify the user/application.</p>         </td>
      </tr>
      <tr>
         <td><p>Value</p>         </td>
      </tr>
   </tbody>
</table>

<span id="olh_additional"></span>

## Additional tab

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Free form name (FFN)</p>         </td>
         <td><p>Free text.</p>         </td>
      </tr>
      <tr>
         <td><p>Telephone number (TPH)</p>         </td>
         <td><p>Telephone number of Originator/Recipient.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="valid_characters"></span>

### Valid characters in O/R addresses

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Character description         </th>
<th class="HeadD-Column1-Header1">Character         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Uppercase alphabetic characters</p>         </td>
         <td><p>A, B, C, … Z</p>         </td>
      </tr>
      <tr>
         <td><p>Lowercase alphabetic characters</p>         </td>
         <td><p>a, b, c, … z</p>         </td>
      </tr>
      <tr>
         <td><p>Digits</p>         </td>
         <td><p>0, 1, 2, … 9</p>         </td>
      </tr>
      <tr>
         <td><p>Space</p>         </td>
         <td><p>‘  ’</p>         </td>
      </tr>
      <tr>
         <td><p>Apostrophe</p>         </td>
         <td><p>'</p>         </td>
      </tr>
      <tr>
         <td><p>Left and right parentheses</p>         </td>
         <td><p>( )</p>         </td>
      </tr>
      <tr>
         <td><p>Plus sign</p>         </td>
         <td><p>+</p>         </td>
      </tr>
      <tr>
         <td><p>Comma and period</p>         </td>
         <td><p>, .</p>         </td>
      </tr>
      <tr>
         <td><p>Slash</p>         </td>
         <td><p>/</p>         </td>
      </tr>
      <tr>
         <td><p>Dash</p>         </td>
         <td><p>-</p>         </td>
      </tr>
      <tr>
         <td><p>Colon</p>         </td>
         <td><p>:</p>         </td>
      </tr>
      <tr>
         <td><p>Equal sign</p>         </td>
         <td><p>=</p>         </td>
      </tr>
      <tr>
         <td><p>Question mark</p>         </td>
         <td><p>?</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[About X.400](../../../connectors_about/x400_about)

[X.400 connector](../../../connectors_about/x400_about/x400_connector)

[Configuration: Connectors](../../config_connectors#olh_connectivity_x400)

[New Remote Site: X.400 tab](../../../managing_partners_start_here/sites_start_here/managing_remote_sites/remote_site_x400_tab)

[New Transfer Request: X.420 tab](../../../transfers_start_here/submitting_transfer_requests_start_here/working_with_transfers_(gui)/transfer_request_x420_tab)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
