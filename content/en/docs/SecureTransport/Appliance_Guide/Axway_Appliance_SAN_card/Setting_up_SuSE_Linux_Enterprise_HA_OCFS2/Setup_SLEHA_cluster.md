{
    "title": "Setup SLEHA cluster to use unicast",
    "linkTitle": "Setup SLEHA cluster to use unicast",
    "weight": "210"
}If your environment does not use multicast, change the configuration from multicast to unicast on each of the cluster nodes as follows:

1.  Run **/etc/init.d/openais stop** to stop the SLEHA cluster.  
    `#/etc/init.d/openais stop`

2.  Run **yast2 cluster** to display the SLEHA cluster configuration.  
    `#yast2 cluster`

3.  Navigate to **Cluster > Communication Channels > Transport** and change communications from `udp` to `udpu`.

4.  Navigate to **Cluster > Communication Channels > Member Address** and add all of the cluster nodes IP addresses.

5.  Select **Auto Generate Node ID**.

6.  Start SLEHA cluster on first node.  
    `#/etc/init.d/openais start`

7.  Start SLEHA cluster on each of the remaining nodes.  
    `#/etc/init.d/openais start`
      
    When all cluster resources are started correctly, **crm\_mon** does not show any errors.  
    

        Last updated: Tue Aug 5 22:15:32 2015
        Last change: Tue Aug 5 22:13:22 2015 by hacluster via crmd on <hostname>
        Stack: classic openais (within plugin)
        Current DC: <hostname> - partition with quorum
        Version: 1.1.9-2db99f1
        2 Node configured, 2 expected votes
        7 Resources configured


        Online: [ <hostname> <hostname> ]

        sonith-sbd    (sonith:external/sbd): Started <hostname>
          Clone Set: base-clone [base-group]
            Started: [ <hostname> <hostname> ]
