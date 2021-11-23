{
    "title": "Workload distribution",
    "linkTitle": "Workload distribution",
    "weight": "130"
}Event distribution in a {{< SecureTransport/componentshortname  >}} Enterprise Cluster (EC) is handled by a distributed event processor and a distributed scheduler. As long as one {{< SecureTransport/componentshortname  >}} Server is running, incoming and scheduled tasks are assigned.

You can configure the event processor to distribute events based on their attributes, however the event processor assigns all events related to one remote PeSIT server to the same {{< SecureTransport/componentshortname  >}} server. Event assignment options are:

-   Events can be assigned to a server with required functionality.
-   Events associated with an particular account can be assigned to the same server. This can improve the performance of the distributed object cache by caching the object that represents the account and related object where they are used.

**Related topics:**

-   [Enterprise Cluster deployment](../c_st_large_enterprise_cluster_deployment)
-   [Passive disaster recovery](../c_st_passive_disaster_recovery)
