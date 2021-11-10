{
    "title": "About XFB Transfer tracked objects",
    "linkTitle": "About XFB Transfer tracked object",
    "weight": "200"
}A XFB Transfer Tracked Object (TO) is the Sentinel structure used to store transfer related events coming from the following Axway products: Transfer CFT, Gateway, Gateway Interchange, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span>, and InterPel.

For each step of each <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> file transfer process, <span class="mc-variable axway_variables.Component_Short_Name variable">SecureTransport</span> generates a Tracked Object instance and sends this to Sentinel. In each TO instance, the State attribute identifies the relevant step of the transfer process.

Each file transfer has a unique identifier that consists of a set of parameters that are exchanged at the beginning of the transfer, or parameters that make the transfer unique in the product. A computation of these parameters creates a unique Sentinel identifier called a CycleID. Linking these CycleIDs together can provide end-to-end monitoring when using a store and forward, or when the Sentinel Universal Agent (UA) is used in an implementation to integrate application processing.

Each transfer passes through different States during its execution, so Sentinel receives an event each time the State changes. A UserState is also available to track pre or post transfer processing. These UserState values vary depending on the operation performed.

The attributes contained in a tracked object fall into one of two categories:

-   System attributes that are common to most tracked objects. System attributes identify application and platform events and errors.
-   User attributes that are not common to all tracked objects. User attributes describe the application- or platform-specific properties of monitored events.

**Related topics:**

-   <a href="../r_st_sentineleventstates" class="MCXref xref">Event states</a>
-   <a href="../r_st_sentineltrackedobjects" class="MCXref xref">Axway Sentinel tracked objects</a>
-   <a href="../r_st_pesit_protocol" class="MCXref xref">PeSIT protocol</a>
-   <a href="../r_st_listofpesitstates" class="MCXref xref">List of PeSIT states</a>
-   <a href="../r_st_xfb_toattributes" class="MCXref xref">XFB Tracked Object attributes</a>
-   <a href="../r_st_cycleid" class="MCXref xref">CycleId calculation</a>
-   <a href="" class="MCXref xref">Axway Sentinel dashboards</a>
-   <a href="../r_st_sentinelrequests" class="MCXref xref">Axway Sentinel requests</a>
-   <a href="../t_st_sentinel" class="MCXref xref">Configure SecureTransport to send events to Axway Sentinel</a>
