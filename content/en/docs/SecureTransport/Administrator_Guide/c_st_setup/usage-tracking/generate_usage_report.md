{
    "title": "Usage and Deployment information",
    "linkTitle": "Usage and Deployment information",
    "weight": "220"
}You can manually generate a usage report that provides an overview of the daily usage of <span class="mc-variable axway_variables.Component_Short_Name variable" style="font-weight: normal;">SecureTransport</span>. This option is applicable to environments with SecureTransport only (without Transfer CFT or other MFT products).

The report provides daily usage metrics and totals for a selected period or date range:

-   number of active users
-   number of unique transfers based on [coreID](../../../operations_menu/c_st_filetransfertracking/t_st_viewfiletransferinfo#CoreID)
-   number of successful inbound and outbound file transfers

Along with these daily metrics, the report contains information regarding your current <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> setup.

The report is in JSON format and is available as a REST API resource.

The Administration Tool provides a simple interface to generate the report as a JSON file.

1.  Select **Setup > Server License**.  
    The *Server License* page is displayed.
2.  In the *Usage Report* pane, select a report time interval from the drop-down and click **Generate**.  
3.  A dialog box prompts you to open the report or save it to disk as a `.json` file.
4.  Select your preference, and click **OK**.

The generated JSON report contains the following parameters:

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Element</p>
<p><em>(type)</em></p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>
<p> </p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>envId</strong>
<p><em>(string)</em></p>         </td>
         <td><p>Unique custom identifier useful for specifying each cluster instance. Blank by default, this value can be changed using the <code>StatisticsSummaryReport.EnvironmentId</code> server configuration option.</p>         </td>
      </tr>
      <tr>
         <td><strong>schemaId</strong>
<p><em>(string)</em></p>         </td>
         <td><p>The JSON schema to validate the file against.</p>
<p>Blank by default this value can be changed using the <code>StatisticsSummaryReport.SchemaId</code> server configuration option.</p>         </td>
      </tr>
      <tr>
         <td><strong>timestamp</strong>
<p><em>(string)</em></p>         </td>
         <td><p>Timestamp when the report is generated.</p>
<p>This value is in ISO 8601 format: <code>{YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}.{SSS}{TZ}</code>.</p>         </td>
      </tr>
      <tr>
         <td><strong>granularity</strong>
<p><em>(number)</em></p>         </td>
         <td>Report interval granularity: <em>86400000</em> milliseconds (24 hours)         </td>
      </tr>
      <tr>
         <td><strong>report</strong>
<p><em>(object)</em></p>         </td>
         <td><p>Collection of <em>daily reports</em>, chronologically ordered by date in the specified reporting period.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><p><strong>date</strong></p>
<p><em>(object)</em></p></li>
</ul>         </td>
         <td><p>The date of the daily report.</p>
<p>This value is in ISO 8601 format: <code>{YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}.{SSS}{TZ}</code>.</p>
<p>The number of daily reports depends on your selection of the reporting period.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>product</strong><br />
<em>(string)</em></li>
</ul></li>
</ul>         </td>
         <td>Name of the MFT product, e.g., <span class="mc-variable suite_variables.SecureTransportName variable" style="font-style: italic;">SecureTransport</span>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><span id="usage"></span><strong>usage</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td><p>Collection of daily metrics related to the product. With <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> it contains the active users and information about the file transfers performed within the day.<br />
</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.ActiveUsers</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td><p>Number of <a href="../../../c_st_advancedaccountadministration/t_st_displayactiveusers" class="MCXref xref">Display active users</a> for the day</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersCore</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td>Total number of unique transfers (based on <code>coreID</code>) for the day         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersIn</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td><p>Number of successful inbound file transfers (with state RECEIVED) for the day. Internal routing (within <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersOut</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td><p>Number of successful outbound file transfers (with state SENT) for the day. Internal routing (within <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersMaxInOut</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td>The greater number between <code>ST.TransfersIn</code> and <code>ST.TransfersOut</code>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>meta</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td>Additional meta information for the daily report         </td>
      </tr>
      <tr>
         <td><p><strong>meta</strong></p>
<p><em>(object)</em></p>         </td>
         <td>Additional meta information for the summary report         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>companyName</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td>Company name as specified in the license         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>envName</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td><p>Custom display name of the environment.</p>
<p>Blank by default; this value can be changed using the <code>StatisticsSummaryReport.EnvironmentName</code> server configuration option.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>productLine</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td>Name of the product line, e.g., <em>MFT</em>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>productName</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td>Name of the MFT product, e.g, <span class="mc-variable suite_variables.SecureTransportName variable" style="font-style: italic;">SecureTransport</span>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>productVersion</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td>Base product version, e.g., <em>5.5</em> (the <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> version)         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>currentPatch</strong><br />
<em>(string)</em></li>
</ul>         </td>
         <td>The currently installed update version, e.g., <em>UPDATE-20200625</em>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>isECEnabled</strong><br />
<em>(boolean)</em></li>
</ul>         </td>
         <td>Specifies if <em>Enterprise Clustering</em> is enabled: can be <em>true</em> or <em>false</em>.         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>isFMEnabled</strong><br />
<em>(boolean)</em></li>
</ul>         </td>
         <td>Specifies if <em>Flow Management (Central Governance)</em> integration is enabled: can be <em>true</em> or <em>false</em>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>isADIEnabled</strong><br />
<em>(boolean)</em></li>
</ul>         </td>
         <td>Specifies if <em>AxwayDecisionInsight (Sentinel)</em> integration is enabled: can be <em>true</em> or <em>false</em>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>plugins</strong><br />
<em>(object)</em></li>
</ul>         </td>
         <td><p>List of installed plug-ins along with their versions</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>authorization</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td>List of installed <a href="../../../c_st_accesscontrol/c_st_pluggable_authorization#Pluggable_authorization" class="MCXref xref">Pluggable аuthorization</a>.         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>authentication</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td>List of installed <a href="../../../c_st_authentication/pluggable_authentication#Pluggable_authentication" class="MCXref xref">Pluggable authentication</a>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>site</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td>List of installed <a href="https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/transfer_sites/transfer_sites.htm" class="MCXref xref">transfer site plug-ins</a>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>customARStep</strong><br />
<em>(object)</em></li>
</ul></li>
</ul>         </td>
         <td>List of installed <a href="https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/ab_custom/Custom_Advanced_Routing_step.htm" class="MCXref xref">Advanced Routing step plug-ins</a>         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>reportTimeframe</strong><br />
<em>(object)</em></li>
</ul>         </td>
         <td>The report time frame         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>startDate</strong><br />
<em>(string)</em></li>
</ul></li>
</ul>         </td>
         <td>Timestamp of the start date of the reporting period         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><strong>endDate</strong><br />
<em>(string)</em></li>
</ul></li>
</ul>         </td>
         <td>Timestamp of the end date of the reporting period. Note that the end date is not included in the report.
For example, to generate a report for May, the start date should be 1 May, the end date should be 1 June.         </td>
      </tr>
      <tr>
         <td><ul>
<li><strong>reportSummary</strong><br />
<em>(object)</em></li>
</ul>         </td>
         <td><p>Usage aggregations for the selected period based on daily <a href="#usage" class="MCXref xref">usage</a> information</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.ActiveUsers</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td>Maximum number of <a href="../../../c_st_advancedaccountadministration/t_st_displayactiveusers" class="MCXref xref">Display active users</a> for the reporting period         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersCore</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td>Total number of unique transfers (based on <code>coreID</code>) for the reporting period         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersIn</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td><p>Number of successful inbound file transfers (with state RECEIVED) for the reporting period. Internal routing (within <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersOut</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td><p>Number of successful outbound file transfers (with state SENT) for the reporting period. Internal routing (within <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>         </td>
      </tr>
      <tr>
         <td><ul>
<li><ul>
<li><ul>
<li><strong>ST.TransfersMaxInOut</strong><br />
<em>(number)</em></li>
</ul></li>
</ul></li>
</ul>         </td>
         <td>Total of the <code>ST.TransfersMaxInOut</code> values for the reporting period         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   <a href="" class="MCXref xref">Disable automatic snapshot updates</a>
-   <a href="" class="MCXref xref">Server usage snapshot by user class</a>
-   <a href="" class="MCXref xref">Server usage details</a>
