{
    "title": "Working with PassPort AM",
    "linkTitle": "Working with PassPort AM",
    "weight": "170"
}{{< Gateway/componentlongname  >}}: Managing Security

[Selecting PassPort AM Access Control Management](#selecting)

[Before using PassPort AM with Gateway](#before_using)

[Configuring Gateway for PassPort AM](#config)

[Calling the PassPort AM server](#calling_pp_am_server)

<span id="selecting"></span>

## Selecting PassPort AM Access Control Management

You can select PassPort AM as the method to use for Access Control Management when installing or when configuring Gateway.

When PassPort AM is selected, you cannot use Gateway's own user management (via the User and Profile objects). The two methods are exclusive.

### Modifying the Access Control Management method

If the Access Control Management method is currently *None*, you can modify it via the Gateway configuration menu.

After setting the Access Control Management method to a secure user access (using Passport AM or Gateway), you can no longer change the option unless you have administrator rights in Gateway or the privilege to update the configuration resource in Passport AM.

<span id="before_using"></span>

## Before using PassPort AM with Gateway

Before using PassPort AM Access Control Management in Gateway:

1.  Install PassPort AM.
2.  Start PassPort AM.
3.  Import the CSD file into the PassPort AM repository.
4.  Install Gateway.
5.  Update the PassPort AM repository with the installed Gateway instance name.

For information about PassPort AM, refer to the Axway PassPort AM documentation.

For information about installing {{< Gateway/componentshortname  >}}, refer to the *{{< Gateway/componentshortname  >}} [Installation Guide](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm)*.

<span id="config"></span>

## Configuring Gateway for PassPort AM

In the Gateway configuration menu:

1.  Select **[Gateway > Connection control](../../../../../gateway_userguide_(primary)/configuration_start_here/config_gateway_paras#olh_gateway_connection_control)**.
2.  In <span style="font-weight: bold;">User access control</span>, select <span style="font-style: italic;">By PassPort AM</span>.
3.  Select <span style="font-weight: bold;">[Connectivity > Axway Connectivity > PassPort](../../../../../gateway_userguide_(primary)/configuration_start_here/config_connectors#olh_connectivity_passport)</span>.
4.  Enter the following information to configure the PassPort AM connection:
    -   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> version (v4)
    -   Select the **Use access management** option
    -   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> server host name or IP address
    -   The <span class="mc-variable suite_variables.PassPortName variable">PassPort</span> HTTP port
    -   The Component Id
    -   The login user name  
        Note: you need to set the component password by running the `pelencpass `command locally on the Gateway machine.
    -   You can also choose to use **TLS**

**Note:** If you log in with the username <span class="code">admin </span>and password <span class="code">admin</span> into Passport AM, you can leave the password field blank.

The lifetime of the cache is available for user configuration through the general configuration parameter <span class="code">\[am\] cache\_duration</span>. It accepts integer values, expressed in minutes, range from *0* to *120*, and it defaults to *1*.

<span id="calling_pp_am_server"></span>

## Calling the PassPort AM server

Gateway calls the PassPort AM server for:

-   Authentication
-   Access management

A system cache is used to optimize the data flow between Gateway and PassPort AM.

Related topics

[About PassPort AM](../)

[About Access Control Management](../../)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
