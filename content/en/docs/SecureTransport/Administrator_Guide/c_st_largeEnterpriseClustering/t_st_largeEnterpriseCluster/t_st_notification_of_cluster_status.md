{
    "title": "Notification of cluster status",
    "linkTitle": "Notification of cluster status",
    "weight": "190"
}<span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> can send an email notification when the number of online servers in the cluster falls below a limit that you set. If enabled, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> sends an email each time it detects a server failure. You can use this notification for the following purposes, among others:

-   Set the limit to one less than the number of nodes in the cluster and use the notification to inform you to restore the node that is offline.
-   Set the limit to one less than the number of nodes required for acceptable performance and use the notification to inform you to evaluate whether to fail over to your standby disaster recovery site.

You configure the email notification in the **Node Threshold** topic of the *Cluster Management* page.

1.  Select **Operations > Cluster Management**.  
    The *Cluster Management* page is displayed.
2.  To change the value of the **Minimum Number of Nodes** field:
    1.  Click the Edit icon (![Edit](/Images/SecureTransport/EditIcon_12x13.png)).
    2.  Type the new value in the field.
    3.  Click the Save icon (![Save](/Images/SecureTransport/SaveIcon_13x13.png)).
3.  To configure the notification email, click **Edit Email Notification**.  
    The *Email Notification* page is displayed.
    1.  To send the emails, select **Send Notification**.
    2.  Type the email subject in the **Subject** field and the email body in the **Notification** field.
    3.  Click **Save** to save your changes or **Cancel** to reset the values to the last saved values.
    4.  Select **Operations > Cluster Management to** return to the *Cluster Management* page.
4.  To set the address the email is sent to, select **Setup > Miscellaneous**.
5.  Make sure all the fields in the *FTP/HTTP Startup Password Timeout Configuration* pane have valid values.

> **Note:**
>
> You must change the default value, root@localhost, of the Notify e-mail field to a complete and valid email address. This address is used for both the sender address and recipient address.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
-   <a href="../t_st_direct_cluster_workload" class="MCXref xref">Direct cluster workload</a>
