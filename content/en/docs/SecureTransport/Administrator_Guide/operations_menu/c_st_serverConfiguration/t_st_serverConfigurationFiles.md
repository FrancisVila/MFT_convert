{
    "title": "Update configuration files",
    "linkTitle": "Update server configuration files",
    "weight": "180"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> stores the following server configuration files in the database:

-   `brules.xml`
-   `FileServicesInterfaceRegistry.xml`
-   `mime.types`
-   `sentinel-returncode-translation.xml`
-   `ssl.csr.conf`
-   SSO Configuration Files - The Single Sign-On (SSO) related configuration files. For more information, refer to <a href="../../../c_st_authentication/c_st_about_sso#SSO" class="MCXref xref">Single Sign-On (SSO) and Single Logout (SLO)</a>.

You can use the *Server Configuration Files* page to make changes on <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Server to the files listed, save the changes to the database, propagate the changes to all servers in a cluster (if applicable), and configure SSO for end-users and administrators. For information about how to configure the SSO functionality in <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, see <a href="../../../c_st_authentication/c_st_about_sso#SSO" class="MCXref xref">Single Sign-On (SSO) and Single Logout (SLO)</a>.

1.  On the *Server Configuration* page, select **Configuration Files**.  
    The *Server Configuration Files* page is displayed.
2.  Download the file to update. (For example, right-click the file name link in your browser and selected **Save Link As** or **Save Target As**.)
3.  Update the file using a editor on your local computer.
4.  Click **Browse** and select the file or type the path to the file in the **Selected File** column.
5.  Select the checkbox that corresponds to the updated file(s).
6.  Click **Upload**.
7.  Restart the `admind` service in order to apply the configuration changes.

In cluster deployment, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> will upload the selected files to the respective Server and copy the files to all the other Servers. However, the Server nodes will load the updated configuration after a restart of the `admind` service on each.
You can apply that same procedure to update configuration files across <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> Edges.

**Notes:**

-   SSO configuration files are replicated on Enterprise Clusters and Standard Clusters after they are uploaded in ZIP format.
-   Alternately, you can edit these configuration files on the server and then click **Synchronize** on the *Server Configuration Files* page for that server. The server saves the file in the database and copies the files to all the other servers in the cluster, and the servers load the updated configuration immediately.
-   For SSO configuration files, the **Synchronize** button will update the SSO-related configuration files in `<FILEDRIVEHOME/conf/sso>` directory with the database. This will only affect the current node.
-   Only ZIP format is accepted for SSO configuration files import.
-   Do not put the configuration files in a sub-directory inside the ZIP file.
-   You can list all SSO-related configuration files, by clicking on the **Plus** (![](/Images/SecureTransport/plus_icon.png)) icon. You can hide the same files, by clicking the **Minus** (![](/Images/SecureTransport/minus_icon.png)) icon.
-   You can download a single SSO-related configuration file, by clicking on the name of the file. You can also download all SSO files in ZIP format, by clicking on the **SSO Configuration Files** link.
-   When importing SSO Configuration Files on a SecureTransport Edge, make sure that the ZIP file contains the `sso-admin.xml`, otherwise the import will not be successful.
-   When importing the SSO Configuration Files in a Standard Cluster, make sure that the Transaction Manager service is running on the current node. For more information, see <a href="../../../c_st_standardclustering/c_st_managestandardcluster/c_st_standard_cluster_synchronization" class="MCXref xref">Standard Cluster synchronization</a>.

**Related topics:**

-   <a href="../c_st_editable_server_configuration_parameters" class="MCXref xref">Editable server configuration parameters</a>
-   <a href="../c_st_local_server_configuration_parameters" class="MCXref xref">Local server configuration parameters</a>
-   <a href="../t_st_serverconfigurationparameters" class="MCXref xref">View and change server configuration parameters</a>
-   <a href="../t_st_serverconfigurationexportimport" class="MCXref xref">Export and import server configuration</a>
