{
    "title": "The performance cost of encryption",
    "linkTitle": "Performance cost of encryption",
    "weight": "150"
}Performance impact on various mailbox operation when data files are encrypted, N=1000 transfers:

<table>
   <tbody>
      <tr>
         <td>Operation         </td>
         <td>Average times         </td>
         <td>Performance decrease         </td>
      </tr>
      <tr>
         <td>Create one item         </td>
         <td>2.33ms/2.39ms         </td>
         <td>2.74%         </td>
      </tr>
      <tr>
         <td>Update one item         </td>
         <td>1.85ms/1.97ms         </td>
         <td>6.15%         </td>
      </tr>
      <tr>
         <td>Select one item with criteria         </td>
         <td>2.125ms/2.144ms         </td>
         <td>0.91%         </td>
      </tr>
      <tr>
         <td>Select one item         </td>
         <td>945ms/1.968ms         </td>
         <td>1.19%         </td>
      </tr>
   </tbody>
</table>

Links to documentation set for Axway Gateway {{< Gateway/releasenumber  >}}:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
