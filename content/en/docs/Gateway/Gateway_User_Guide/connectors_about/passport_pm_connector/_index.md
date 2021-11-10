{
    "title": "Axway PassPort PM connector",
    "linkTitle": "Axway PassPort",
    "weight": "220"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Connectors

## About PassPort PM

PassPort PM (Partner Management) enables you to manage partners on the <span class="mc-variable axway_variables.Platform_or_Suite_Short_Name variable">Axway Platform</span>.

### Activating the PassPort PM connector

To configure Gateway for use with PassPort PM, set up the PassPort PM connector in the Gateway [configuration menu](../../configuration_start_here/config_procedure#Configuring_Gateway):

-   In the left pane of the Gateway GUI, right-click the Gateway server that you want to configure and select <span style="font-weight: bold;">Configure</span>.
-   Select <span style="font-weight: bold;">Connectivity > Axway Connectivity > PassPort</span>.
-   Complete the [PassPort parameters](../../configuration_start_here/config_connectors#olh_connectivity_passport).
-   Click <span style="font-weight: bold;">OK</span>.

Enter the following information to configure the PassPort PM connection:

-   <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> Version
-   Select the **Use partner management** option
-   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> server host name or IP address
-   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> HTTP port
-   The Component Id
-   The login user name  
    Note: you need to set the component password by running the `pelencpass `command locally on the <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> server.
-    Also you can select the **Use TLS** option to secure the connection between <span class="mc-variable axway_variables.Component_Short_Name variable">Gateway</span> and PassPort PM. If you do that, you need to enter the following parameters:
    -   The PKI SSL port
    -   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> CA location is pre-defined, but you can modify it.

<span id="PassPort_PM_cache"></span>

### PassPort PM cache

After modifying a partner from PassPort PM, it may take some time until Gateway can use the updated values (based on the velue of the <span class="code">vsite\_age\_max </span>parameter). There are two <span class="code">pelctl </span>commands you can use to invalidate the PassPort PM cache, and view the changes earlier:

-   <span class="code"></span>To invalidate all PassPort's PM cache:<span class="code">  
    pelctl invalidate\_tpm\_cache </span>  
-   To invalidate only the &lt;comprofile> entry in the cache<span class="code">:  
    pelctl invalidate\_tpm\_cache -tpmdea &lt;comprofile> </span>

## Optimizing performance between Gateway and PassPort PM

When using PassPort PM, Gateway saves the results of queries in specific Site objects called <span style="font-style: italic;">Virtual Sites</span>. These Virtual Sites save PassPort from being queried all the time by Gateway.

Virtual Sites have a tunable lifetime set by the <span class="code">vsite\_age\_max</span> parameter. Setting a long lifetime reduces the number of queries to PassPort resulting in shorter processing times. However, during that time any change made in the related PassPort entry is not refreshed. On the other hand, having a short <span class="code">vsite\_age\_max</span> value allows quicker updates of PassPort modifications within Gateway, but with poorer performance.

Modify the <span class="code">vsite\_age\_max</span> parameter in the [Gateway advanced options](../../configuration_start_here/config_gateway_paras#Advanced_parameters).

Related topics

[Using PassPort PM with OFTP](../../protocols_about/oftp_about/oftp_and_passport_pm)

[Managing X.400 partners](../x400_about/x400_managing_partners)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
