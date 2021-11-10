{
    "title": "Governance services",
    "linkTitle": "Governance services",
    "weight": "130"
}<span class="mc-variable axway_variables.Company_Name variable">Axway</span> <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> and Flow Manager are two <span class="mc-variable axway_variables.Platform_or_Suite_Long_Name variable">AMPLIFY</span> management applications that provide a set of services for administering Transfer CFTs. From the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> UI, for example, you can configure, access logs, and perform operational tasks for your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. Central Governance also simplifies the task of creating file transfers definitions, and supports mass deployment of configuration changes to groups of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s.

<span class="mc-variable Primary.CG or_UM variable">Central Governance</span> offers the following key features:

-   Automatic recognition and registration of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s on connection
-   Centralized management of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> configurations, with processing capabilities for highly distributed environments
-   Centralized start, stop, and log viewing for your <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>s
-   Global management of user and partner identities and rights
-   Data flow repository, allowing you to create and supervise end-to-end data flow definitions
-   Alert management for tracking <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> and its data flow processing, including an alert notification option
-   Out-of-the-box dashboards

The following diagram illustrates a simplified view of the <span class="mc-variable Primary.CG or_UM variable">Central Governance</span> architecture.

<img src="/Images/TransferCFT/2013_g_CG_architecture_draft1.png" class="mediumWidth" alt="High level view of Central Governance layer over a group of Transfer CFTs" />

You can deploy a single Central Governance instance with one computer per network. The system supports active/passive resiliency, and can bring another instance of Central Governance online if the primary fails.

> **Note:**
>
> Flow Manager offers services that are similar to Central Governance, but with the addition of predefined templates and API functionality in a container setting.
