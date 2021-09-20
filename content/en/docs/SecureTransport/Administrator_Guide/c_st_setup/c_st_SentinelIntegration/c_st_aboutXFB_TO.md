{
    "title": "About XFB Transfer tracked object",
    "linkTitle": "About XFB Transfer tracked object",
    "weight": "210"
}A XFB Transfer Tracked Object (TO) is the Sentinel structure used to store transfer related events coming from the following Axway products: Transfer CFT, Gateway, Gateway Interchange, SecureTransport, and InterPel.

For each step of each SecureTransport file transfer process, SecureTransport generates a Tracked Object instance and sends this to Sentinel. In each TO instance, the State attribute identifies the relevant step of the transfer process.

Each file transfer has a unique identifier that consists of a set of parameters that are exchanged at the beginning of the transfer, or parameters that make the transfer unique in the product. A computation of these parameters creates a unique Sentinel identifier called a CycleID. Linking these CycleIDs together can provide end-to-end monitoring when using a store and forward, or when the Sentinel Universal Agent (UA) is used in an implementation to integrate application processing.

Each transfer passes through different States during its execution, so Sentinel receives an event each time the State changes. A UserState is also available to track pre or post transfer processing. These UserState values vary depending on the operation performed.

The attributes contained in a tracked object fall into one of two categories:

-   System attributes that are common to most tracked objects. System attributes identify application and platform events and errors.
-   User attributes that are not common to all tracked objects. User attributes describe the application- or platform-specific properties of monitored events.

**Related topics:**

-   [Event states](../r_st_sentineleventstates)
-   [Axway Sentinel tracked objects](../r_st_sentineltrackedobjects)
-   [PeSIT protocol](../r_st_pesit_protocol)
-   [List of PeSIT states](../r_st_listofpesitstates)
-   [XFB Tracked Object attributes](../r_st_xfb_toattributes)
-   [CycleId calculation](../r_st_cycleid)
-   [Axway Sentinel dashboards](r_st_sentineldashboards.htm)
-   [Axway Sentinel requests](../r_st_sentinelrequests)
-   [Configure SecureTransport to send events to Axway Sentinel](../t_st_sentinel)