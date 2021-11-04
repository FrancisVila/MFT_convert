{
    "title": "Migrate  Windows Server 2012 R2 to a later OS version",
    "linkTitle": "Migrate Windows Server 2012 R2 to a later OS version",
    "weight": "120"
}This chapter provides detailed step-by step procedures on migrating <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> installed on Microsoft Windows Server 2012 R2 to a later Windows Server version: either 2016 or 2019. The following topics cover different <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Release_Number variable">5.5</span> deployments.

-   <a href="standalone-mysql" class="MCXref xref">Standalone installation with embedded database</a>
-   <a href="standalone-ext-db" class="MCXref xref">Standalone with External Database</a>
-   <a href="standard-cluster-mysql" class="MCXref xref">Standard Cluster environment with embedded database</a>
-   <a href="lec-ext-db" class="MCXref xref">Enterprise Cluster environment with external database</a>
-   <a href="edge-mysql" class="MCXref xref">Edge installation with Embedded Database</a>
-   <a href="edge-synced-mysql" class="MCXref xref">Edge installation with Embedded Database when part of a synchronized cluster</a>

 

> **Note:**
>
> The topics described will refer to your existing SecureTransport 5.5 on Windows Server 2012 R2 deployment as the original deployment. Your future SecureTransport 5.5 (on either Windows Server 2016 or Windows Server 2019) deployment is referred to as the new deployment.

Instructions in these topics pertain to <span class="mc-variable suite_variables.SecureTransportName variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> only. If you are using a previous version of <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, follow the upgrade procedures as provided in this guide.

In the listed topics, to avoid confusion, the following terminology is introduced:

-   The current <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> deployment on Windows Server 2012 R2 is also referred to as the *original* deployment.
-   Similarly, your future deployment (Windows Server 2016 or Windows Server 2019) is also referred to as the *new* deployment.

 
