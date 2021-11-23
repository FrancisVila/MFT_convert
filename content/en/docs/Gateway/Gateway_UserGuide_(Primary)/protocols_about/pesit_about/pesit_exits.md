{
    "title": "PeSIT specific user exits",
    "linkTitle": "PeSIT specific exits",
    "weight": "250"
}{{< Gateway/componentlongname  >}}: Protocols

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td><strong>Please note that care should be taken when</strong> <strong><span class="mc-variable gateway_variables.in_Snippet_UserExitsCaution_ variable">customizing user exits</span>, as there are some</strong> <span style="color: #8b0000;font-weight: bold;">security risks</span> <strong>involved if the custom code is not properly reviewed and security best practices are not followed. Please see the</strong> <em><strong>Security Guide &gt; Security best practices &gt; </strong><a href="/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/SecurityGuide/Security_best_practices.htm#identified_threats_and_possible_mitigations">Identified threats and possible mitigations</a></em> <strong>section for additional information.<br />
</strong>         </td>
      </tr>
   </tbody>
</table>

Gateway provides the following PeSIT user exits that you can customize according to your requirements:

-   [ExitPesitPreConnection](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitPesitPreConnection):  
    PeSIT pre-connection user exit routine. On reception of a PeSIT pre-connection message, this exit routine is called to validate the message content (user ID and password).

<!-- -->

-   [ExitPesitMsg](../../../customizing_gw_about/user_exits_about/user_exits_internal#ExitPesitMsg):  
    This exit routine is called on reception of an FPDU\_MSG. On return, FPDU\_ACKMSG is sent to the partner Site with diagnostic code (PI 2) equal to zero.

Related topics

[Internal user exits](../../../customizing_gw_about/user_exits_about/user_exits_internal)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
