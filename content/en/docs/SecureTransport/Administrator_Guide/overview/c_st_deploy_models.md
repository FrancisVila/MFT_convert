{
    "title": "Deployment models",
    "linkTitle": "Deployment models",
    "weight": "80"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> cam be deployed as part of a Standard Cluster (SC), Enterprise Cluster (EC), or in standalone mode.

<span id="Clusteri"></span>

## Cluster models

To provide flexibility for both ease in managing clustering and scale to meet the most demanding of loads, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server offers two cluster models. These are the Standard Cluster and Enterprise Cluster.

Standard Clustering uses an embedded database, which minimizes external dependencies and overhead and reduces the cost of clustering. A Standard Cluster can have from two to three nodes (servers). For more information, see <a href="../../c_st_standardclustering#Standard_Clustering_3967700027_1013811" class="MCXref xref">Standard Cluster</a>.

For a situation that exceeds the capacity of a Standard Cluster or requires a shared database, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> <span class="mc-variable axway_variables.Component_Version variable">5.5</span> offers an Enterprise Cluster option. An Enterprise Cluster using an external database and a high-performance cache-management layer significantly improves efficiency, provides near-linear scaling, and enables very large scale configurations. With the Enterprise Cluster option, an active/active cluster can have up to 20 nodes. The Enterprise Cluster option requires your organization to provide and maintain an [external database](../r_st_axway_and_third-party_software_support#Database). You must also provide a high-performance shared file system for the user files. For more information, see <a href="../../c_st_largeenterpriseclustering#Large_Enterprise_Clustering_2746683174_1079954" class="MCXref xref">Enterprise Cluster</a>.

## Standalone deployment

When you do not need a cluster for additional capacity or improved availability, you can deploy <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server as a single server. A stand-alone <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server can use the embedded database or an external database. All stand-alone deployments can use a local file system for user files.

> **Note:**
>
> Multiple standalone SecureTransport instances sharing the file system where the user home directories are located is not a supported configuration.
