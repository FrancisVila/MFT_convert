{
    "title": "Usage and Deployment information",
    "linkTitle": "Usage and Deployment information",
    "weight": "230"
}You can manually generate a usage report that provides an overview of the daily usage of SecureTransport. This option is applicable to environments with SecureTransport only (without Transfer CFT or other MFT products).

The report provides daily usage metrics and totals for a selected period or date range:

-   number of active users
-   number of unique transfers based on [coreID](../../../operations_menu/c_st_filetransfertracking/t_st_viewfiletransferinfo)
-   number of successful inbound and outbound file transfers

Along with these daily metrics, the report contains information regarding your current SecureTransport setup.

The report is in JSON format and is available as a REST API resource.

The Administration Tool provides a simple interface to generate the report as a JSON file.

1.  Select **Setup > Server License**.  
    The *Server License* page is displayed.
2.  In the *Usage Report* pane, select a report time interval from the drop-down and click **Generate**.  
3.  A dialog box prompts you to open the report or save it to disk as a `.json` file.
4.  Select your preference, and click **OK**.

The generated JSON report contains the following parameters:

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Element</p>
            <p><em>(type)</em>
</p>
</th>
         <th>
            <p>Description</p>
            <p> </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>envId</strong>
            <p><em>(string)</em>
</p>
         </td>
         <td>
            <p>Unique custom identifier useful for specifying each cluster instance. Blank by default, this value can be changed using the <code>StatisticsSummaryReport.EnvironmentId</code> server configuration option.</p>
         </td>
      </tr>
      <tr>
         <td><strong>schemaId</strong>
            <p><em>(string)</em>
</p>
         </td>
         <td>
            <p>The JSON schema to validate the file against.</p>
            <p>Blank by default this value can be changed using the <code>StatisticsSummaryReport.SchemaId</code> server configuration option.</p>
         </td>
      </tr>
      <tr>
         <td><strong>timestamp</strong>
            <p><em>(string)</em>
</p>
         </td>
         <td>
            <p>Timestamp when the report is generated.</p>
            <p>This value is in ISO 8601 format: <code>{YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}.{SSS}{TZ}</code>.</p>
         </td>
      </tr>
      <tr>
         <td><strong>granularity</strong>
            <p><em>(number)</em>
</p>
         </td>
         <td>Report interval granularity: <i>86400000</i> milliseconds (24 hours)         </td>
      </tr>
      <tr>
         <td><strong>report</strong>
            <p><em>(object)</em>
</p>
         </td>
         <td>
            <p>Collection of <i>daily reports</i>, chronologically ordered by date in the specified reporting period.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><strong>date</strong>
            <p><em>(object)</em>
</p>
               </li>
            </ul>
         </td>
         <td>
            <p>The date of the daily report. </p>
            <p>This value is in ISO 8601 format: <code>{YYYY}-{MM}-{DD}T{hh}:{mm}:{ss}.{SSS}{TZ}</code>.</p>
            <p>The number of daily reports depends on your selection of the reporting period.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><b>product</b>
                                        <br/><em>(string)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Name of the MFT product, e.g., <span>SecureTransport</span>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><a name="usage"></a><strong>usage</strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Collection of daily metrics  related to the product. With <span>SecureTransport</span> it contains the active users and information about the file transfers performed within the day.<br/></p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.ActiveUsers</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Number of  <a href="../../../c_st_advancedaccountadministration/t_st_displayactiveusers">Display active users</a>                        for the day</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersCore</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Total number of unique transfers  (based on <code>coreID</code>) for the day         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersIn</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Number of successful inbound file transfers (with state RECEIVED) for the day. Internal routing (within <span>SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersOut</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Number of successful outbound file transfers (with state SENT) for the day. Internal routing (within <span>SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersMaxInOut</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>The greater number between <code>ST.TransfersIn</code> and <code>ST.TransfersOut</code>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>meta</strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Additional  meta information for the daily report          </td>
      </tr>
      <tr>
         <td>
            <p><strong>meta</strong>
</p>
            <p><em>(object)</em>
</p>
         </td>
         <td>Additional meta information for the summary report         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>companyName</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>Company name as specified in the  license         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>envName</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>
            <p>Custom display name of the environment. </p>
            <p>Blank by default; this value can be changed using  the <code>StatisticsSummaryReport.EnvironmentName</code> server configuration option. </p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>productLine</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>Name of the product line, e.g., <i>MFT</i>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>productName</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>Name of the MFT product, e.g, <span>SecureTransport</span>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>productVersion</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>Base product version, e.g., <i>5.5</i> (the <span>SecureTransport</span> version)         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>currentPatch</b>
<br><em>(string)</em>
</br>               </li>
            </ul>
         </td>
         <td>The currently installed update version, e.g., <i>UPDATE-20200625</i>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>isECEnabled</b>
<br><em>(boolean)</em>
</br>               </li>
            </ul>
         </td>
         <td> Specifies if <i>Enterprise Clustering</i> is enabled: can be <i>true</i> or <i>false</i>.         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>isFMEnabled</b>
<br/><em>(boolean)</em>
               </li>
            </ul>
         </td>
         <td>Specifies if  <i>Flow Management (Central Governance)</i> integration is enabled: can be <i>true</i> or <i>false</i>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>isADIEnabled</b>
<br/><em>(boolean)</em>
               </li>
            </ul>
         </td>
         <td>Specifies if  <i>AxwayDecisionInsight (Sentinel)</i> integration is enabled: can be <i>true</i> or <i>false</i>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>plugins</b>
<br/><em>(object)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>List of installed plug-ins along with their versions</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>authorization</strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td> List of installed <a href="../../../c_st_accesscontrol/c_st_pluggable_authorization">Pluggable аuthorization</a>.         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>authentication</strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>List of installed <a href="../../../c_st_authentication/pluggable_authentication">Pluggable authentication</a>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>site </strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>List of installed <a href="https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/transfer_sites/transfer_sites.htm">transfer site plug-ins</a>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>customARStep</strong>
                                        <br/><em>(object)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>List of installed <a href="https://docs.axway.com/bundle/SecureTransport_55_DeveloperGuide_allOS_en_HTML5/page/Content/DevelopersGuide/ab_custom/Custom_Advanced_Routing_step.htm">Advanced Routing step plug-ins</a>         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>reportTimeframe</b>
                                <br/><em>(object)</em>
               </li>
            </ul>
         </td>
         <td>The report time frame                            </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>startDate</strong>
                                        <br/><em>(string)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Timestamp of the start date of the reporting period         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li><strong>endDate</strong>
                                        <br/><em>(string)</em>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Timestamp of the end date of the reporting period. Note that the end date is not included in the report. 
For example, to generate a report for May, the start date should be 1 May, the end date should be 1 June.         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>reportSummary</b>
                                <br/><em>(object)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>
                       Usage aggregations for the selected period based on daily <a href="#usage">usage</a> information</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.ActiveUsers</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Maximum number of  <a href="../../../c_st_advancedaccountadministration/t_st_displayactiveusers">Display active users</a> for the reporting period
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersCore</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Total number of unique transfers  (based on <code>coreID</code>) for the reporting period         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersIn</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Number of successful inbound file transfers (with state RECEIVED) for the reporting period. Internal routing (within <span>SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersOut</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>
            <p>Number of successful outbound file transfers (with state SENT) for the reporting period. Internal routing (within <span>SecureTransport</span>) via Advanced Router and Standard Router is excluded.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li>
            <ul>
               <li>
            <ul>
               <li><strong>ST.TransfersMaxInOut</strong>
                                                <br/><em>(number)</em>
               </li>
            </ul>
               </li>
            </ul>
               </li>
            </ul>
         </td>
         <td>Total of the <code>ST.TransfersMaxInOut</code> values for the reporting period
         </td>
      </tr>
   </tbody>
</table>

**Related topics:**

-   [Disable automatic snapshot updates](t_st_disable_automatic_snapshot_updates.htm)
-   [Server usage snapshot by user class](c_st_server_usage_snapshot.htm)
-   [Server usage details](c_st_connection_details.htm)
