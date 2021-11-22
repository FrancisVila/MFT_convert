{
    "title": "Direct cluster workload",
    "linkTitle": "Direct cluster workload",
    "weight": "230"
}As described in <a href="../../c_st_largeenterpriseclustermodel/c_st_workload_distribution" class="MCXref xref">Workload distribution</a>, an event processor directs events that represent workload tasks to the {{< SecureTransport/componentshortname  >}} Servers in the cluster. Using its default policies, the event processor directs all events associated with an account to the same set of servers. This policy improves the performance of the distributed object cache that {{< SecureTransport/componentshortname  >}} uses to avoid database fetches for object references. If all tasks associated with an account are performed by the same set of servers, the object that represents that account and related objects are cached at that server. This improves performance because the cache manager does not need to fetch them from another server.

In addition to the default account-based event management, event processor policies can direct events to particular servers based on attributes of each event. By default, the event processor uses a round-robin policy to direct events to servers in the set that is processing events for the account, directing each event to the next server in sequence.

If a server in your cluster has performance characteristics or other resources required for certain tasks, you can direct events that represent those tasks that to those particular servers. By default the following task-type attributes are defined:

-   **FM\_TRIGGERED** – Caused by an action of a transfer site that uses the Folder Monitor protocol
-   **MAINTENANCE** – Log applications: LogEntry Maintenance, Sentinel Link Data Maintenance, and Transfer Log Maintenance
-   **PGP** – PGP encryption or decryption
-   **PULL** – Server-initiated incoming transfer
-   **PUSH** – Server-initiated outgoing transfer

For example, to improve performance of PGP encryption and decryption, you can include in your cluster a server with better computational performance, and direct all PGP task to that server.

The `EventQueue.DispatchPolicy.name` system configuration parameter controls the behavior of the event queue. Valid values are:

-   `cacheBasedPolicy` (default) – Directs all events associated with an account to the same server to improve performance
-   `attributeMatchPolicy` – Directs events based on specified attributes
-   `roundRobinPolicy` – Causes the event queue to direct each event to the next server in sequence without regard to account or attributes

The `attributeMatchPolicy` is not used when a node in the cluster is overloaded. For more information, refer to the description of the `EventQueue.taskProcessor.threshold` parameter on the *Server Configuration* page.

In each case, either the policy identifies a set of servers or, if no servers match, the criteria, a set that includes the whole cluster. The event manager uses the round-robin method and select the next server from the set in sequence. Of course, round-robin distribution does not occur when only one server is selected by the policy.

You can configure a {{< SecureTransport/componentshortname  >}} Server to process tasks of one or more types by editing a local configuration parameter.

1.  Log on to the {{< SecureTransport/componentshortname >}} Server.
2.  Select **Operations > Server Configuration**.  
    The *Server Configuration* page is displayed.
3.  Search for the local parameter `EventQueue.taskProcessor.attributes`.  
    The value is a comma-separated list of task types to direct to this server. The default value is `PGP=false, PUSH=false, PULL=false, FM_TRIGGERED=false, MAINTENANCE=false`.
4.  Edit the value and change `false` to `true` for each event type to direct to this server.
5.  Save the new value.
6.  Search for the parameter `EventQueue.DispatchPolicy.name`, edit it, and change its value to `attributeMatchPolicy`.
7.  Select **Operations > Server Control** and restart the TM Server.

The distributed Event Manager now prefers the Server for events of the selected types.

If you configure a {{< SecureTransport/componentshortname  >}} Server to process PGP tasks, you must make other changes on every node of your cluster.

1.  If your deployment uses NFS to provide the shared file system, you must export the file system with the `sync` and `no_wdelay` options.

2.  Log on the {{< SecureTransport/componentshortname >}} Server computer.

3.  If your deployment uses NFS to provide the shared file system, change the NFS mount to use the `-o noac,sync` options.

4.  Make a backup copy and open the `<FILEDRIVEHOME>/brules/local/wptdocuments/Streaming.xml` file in a text editor.

5.  Find the following text:  



        <!-- Uncomment the following if you want to enable the 
             PGP Event type distribution -->
        <!--
        <operator name="or" />
           <expression>
              <item>
                 <attribute>EventType</attribute>
                 <comparator name="equal" />
                 <value>Transformation</value>
              </item>
              <operator name="and" />
              <item>
                 <attribute>DXAGENT_TRANSFORMATION_TYPE</attribute>
                 <comparator name="equal" />
                 <value>PGP</value>
              </item>
           </expression>
        -->

6.  Delete the following comment lines from that text:  
    `<!--`  
    and  
    `-->`

7.  Save the file.

8.  Select **Operations > Server Control** and restart the TM Server.

> **Note:**
>
> When a SecureTransport Server is configured to process PGP tasks, Sentinel reporting for those transfers is not accurate because Sentinel cannot combine the processes of the transfer.

You can add task types (attributes) to `EventQueue.taskProcessor.attributes` by editing the `EventQueue.submissionConfigurator.additionalAttributes` server configuration parameter on any server in the cluster.

The items in this comma-separated list of attributes are the names of environment variables that you need to use to identify events. For example:

-   `DXAGENT_APPLICATION_NAME` is used to identify events for all users who are subscribed to the named application.
-   `DXAGENT_SITE_NAME` is used to identify events for all users who are subscribed to a transfer site with the given name.

Once you add task types to `EventQueue.submissionConfigurator.additionalAttributes`, you edit `EventQueue.taskProcessor.attributes` in the same way you do for the standard task types. The items you add have the form:

`<environment variable>=<value>`

where the environment variable is listed in `EventQueue.submissionConfigurator.additionalAttributes` and the value selects the events to direct to the server. For example:

-   To define a task type for events for all users who are subscribed to an Site Mailbox application named `smbBU1`, the attribute is `DXAGENT_APPLICATION_NAME=smbBU1`.
-   To define a task type for events for all users who have a transfer site named `FtpNode3Unit1`, the attribute is `DXAGENT_SITE_NAME=FtpNode3Unit1`.

**Related topics:**

-   <a href="../c_st_cluster_prerequisites" class="MCXref xref">Enterprise Cluster prerequisites</a>
-   <a href="../t_st_setup_cluster" class="MCXref xref">Set up a cluster</a>
-   <a href="../t_st_add_server_to_cluster" class="MCXref xref">Add a server to a cluster</a>
-   <a href="../t_st_remove_server_from_cluster" class="MCXref xref">Remove a server from a cluster</a>
-   <a href="../t_st_view_cluster_status" class="MCXref xref">View cluster status</a>
-   <a href="../t_st_notification_of_cluster_status" class="MCXref xref">Notification of cluster status</a>
-   <a href="../t_st_setup_disaster_recovery_cluster" class="MCXref xref">Set up a disaster recovery cluster</a>
-   <a href="../t_st_maintain_disaster_recovery_cluster" class="MCXref xref">Maintain a disaster recovery cluster</a>
-   <a href="../t_st_dr_failover_fallback" class="MCXref xref">Disaster recovery failover and fallback</a>
