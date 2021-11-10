{
    "title": "OFTP identification code",
    "linkTitle": "OFTP identification code",
    "weight": "210"
}------------------------------------------------------------------------

RFC - Identification code description:

The Initiator (sender) and Responder (receiver) participating in an ODETTE-FTP session are uniquely identified by an Identification Code based on \[ISO-6523\]. This ISO describes the structure for the identification of organizations and organization parts (SIO).

The locations are considered to be adjacent for the duration of the transmission.

The SIO has the following format:



    o-------------------------------------------------------------------o
    | Pos | Field | Description | Format |
    |-----+-----------+---------------------------------------+---------|
    | 0 | SIOOID | ODETTE Identifier | F X(1) |
    | 1 | SIOICD | International Code Designator | V 9(4) |
    | 5 | SIOORG | Organisation Code | V X(14) |
    | 19 | SIOCSA | Computer Subaddress | V X(6) |
    o-------------------------------------------------------------------o

### Table of fields

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Field         </th>
<th class="HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>SIOOID ODETTE Identifier Character</p>         </td>
         <td><p>Value: 'O' Indicates ODETTE is assigned an Organisation Identifier.</p>
<p>Other values may be used for non-ODETTE codes.</p>         </td>
      </tr>
      <tr>
         <td><p>SIOICD International Code Designator String(4)</p>         </td>
         <td><p>A code forming part of the Organization Identifier.</p>         </td>
      </tr>
      <tr>
         <td><p>SIOORG Organisation Code String(14)</p>         </td>
         <td><p>A code forming part of the Organization Identifier. This field may contain the letters A to Z, the digits 0 to 9 and space and hyphen characters.</p>         </td>
      </tr>
      <tr>
         <td><p>SIOCSA Computer Subaddress String(6)</p>         </td>
         <td><p>A locally assigned address that uniquely identifies a system within an organization (defined by an Organization</p>
<p>Identifier).</p>         </td>
      </tr>
   </tbody>
</table>

Where:

X(n) - An alphanumeric field of length n octets.

9(n) - A numeric field of length n octets.

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
