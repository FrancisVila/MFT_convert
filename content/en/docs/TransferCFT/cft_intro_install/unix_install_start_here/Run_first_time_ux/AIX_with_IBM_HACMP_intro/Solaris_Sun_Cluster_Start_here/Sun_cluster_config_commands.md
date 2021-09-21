{
    "title": "SCSWITCH and SCSTAT commands",
    "linkTitle": "SCSWITCH and SCSTAT commands",
    "weight": "300"
}# <span id="CFT_Sun_cluster_service_configuration_commands"></span> Sun cluster service configuration commands

Sun Cluster services are managed and monitored using the following
service configuration commands:

-   scswitch for startup,
    stop, and switch over
-   scstat for monitoring

### <span id="scswitch"></span>Sun cluster scswitch command

The commands are as follows:

scswitch -z -g resource\_grp\[,...\]
-h node\[,...\]

scswitch -z -D device\_group\_name\[,...\]
-h node

scswitch -S -h from\_node

scswitch -R -h node\[,...\]
-g resource\_grp\[,...\]

scswitch -m -D device\_service\_name\[,...\]

scswitch -e | -n \[-M\]
-j resource\[,...\]

scswitch -u | -o -g resource\_grp\[,...\]

scswitch -c -h node\[,...\]
-j resource\[,...\] -f flag\_name

scswitch -Z \[-g resource\_grp\[,...\]\]

scswitch -F -g resource\_grp\[,...\]
| -D device\_group\_name\[,...\]

scstat \[-DWgnpqi\] \[-v\[v\]\]
\[-h &lt;host>\]

The following sections describe the commands necessary
to monitor, start, stop and switchover services. Refer to the Sun documentation
and the "man" pages for additional details.

### Sun cluster scstat command

Example of scstat exit :

root@chou # scstat

-Resource Groups --

Group Name Node Name State

---------- --------- -----

Group: xos-rg chou Online

Group: xos-rg fleur Offline

Group: pel-rg chou Online

Group: pel-rg fleur Offline

Group: CFT-rg chou Offline

Group: CFT-rg fleur Online

 

-- Resources --

Resource Name Node Name State Status Message

------------- --------- ----- --------------

Resource: xos-disk chou Online Online

Resource: xos-disk fleur Offline Offline

Resource: ops-ip chou Online Online - LogicalHostname online.

Resource: ops-ip fleur Offline Offline

Resource: xos-sm chou Online Online

Resource: xos-sm fleur Offline Offline

Resource: xos-sp chou Online Online

Resource: xos-sp fleur Offline Offline

Resource: pel-ip chou Online Online - LogicalHostname online.

Resource: pel-ip fleur Offline Offline - LogicalHostname offline.

Resource: pel-disk chou Online Online

Resource: pel-disk fleur Offline Offline

Resource: pel-gds chou Online Online

Resource: pel-gds fleur Offline Offline

Resource: cft-ip chou Offline Offline - LogicalHostname offline.

Resource: cft-ip fleur Online Online - LogicalHostname online.

Resource: cft-disk chou Offline Offline

Resource: cft-disk fleur Online Online

Resource: cft-gds chou Offline Offline

Resource: cft-gds fleur Online Online

---------------------------------------------------------------

## Starting the service

The following command activates the Transfer CFT-rg service:

scswitch
–Z –g CFT-rg

View the log extract for starting Transfer CFT on a node

Oct
10 18:35:18 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hafoip\_prenet\_start> for resource &lt;cft-ip>, resource
group &lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18:35:18 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hafoip\_prenet\_start>
completed successfully for resource &lt;cft-ip>, resource group &lt;CFT-rg>

Oct
10 18:35:18 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_prenet\_start> for resource &lt;cft-disk>,
resource group &lt;CFT-rg>, timeout &lt;1800> seconds

Oct
10 18:35:20 fleur Cluster.Framework: \[ID 801593 daemon.notice\] stdout:
becoming primary for dsk/d16

Oct
10 18:35:20 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hastorageplus\_prenet\_start>
completed successfully for resource &lt;cft-disk>, resource group &lt;CFT-rg>

Oct
10 18:35:20 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hafoip\_start> for resource &lt;cft-ip>, resource group
&lt;CFT-rg>, timeout &lt;500> seconds

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hafoip\_start>
completed successfully for resource &lt;cft-ip>, resource group &lt;CFT-rg>

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hafoip\_monitor\_start> for resource &lt;cft-ip>, resource
group &lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_start> for resource &lt;cft-disk>, resource
group &lt;CFT-rg>, timeout &lt;90> seconds

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hafoip\_monitor\_start>
completed successfully for resource &lt;cft-ip>, resource group &lt;CFT-rg>

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hastorageplus\_start>
completed successfully for resource &lt;cft-disk>, resource group &lt;CFT-rg>

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_monitor\_start> for resource &lt;cft-disk>,
resource group &lt;CFT-rg>, timeout &lt;90> seconds

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;gds\_svc\_start> for resource &lt;cft-gds>, resource group
&lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18:35:21 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;hastorageplus\_monitor\_start>
completed successfully for resource &lt;cft-disk>, resource group &lt;CFT-rg>

Oct
10 18:35:31 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;gds\_svc\_start>
completed successfully for resource &lt;cft-gds>, resource group &lt;CFT-rg>

Oct
10 18:35:31 fleur Cluster.RGM.rgmd: \[ID 707948 daemon.notice\] launching
method &lt;gds\_monitor\_start> for resource &lt;cft-gds>, resource
group &lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18:35:31 fleur Cluster.RGM.rgmd: \[ID 148023 daemon.notice\] method &lt;gds\_monitor\_start>
completed successfully for resource &lt;cft-gds>, resource group &lt;CFT-rg>

### Stopping the service

The following command deactivates the Transfer CFT resources. To stop
Transfer CFT, deactivate the cft-gds resource. When you stop Transfer
CFT using cft stop, an automatic restart of Sun Cluster is triggered.

scswitch
–n –j cft-gds  
scswitch
–n –j cft-ip  
scswitch
–n –j cft-disk

View the log extract for stopping Transfer CFT on a node

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;hafoip\_monitor\_stop> for resource &lt;cft-ip>, resource
group &lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_monitor\_stop> for resource &lt;cft-disk>,
resource group &lt;CFT-rg>, timeout &lt;90> seconds

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;gds\_monitor\_stop> for resource &lt;cft-gds>, resource
group &lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;hastorageplus\_monitor\_stop> completed successfully for resource
&lt;cft-disk>, resource group &lt;CFT-rg>

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;hafoip\_monitor\_stop> completed successfully for resource &lt;cft-ip>,
resource group &lt;CFT-rg>

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;gds\_monitor\_stop> completed successfully for resource &lt;cft-gds>,
resource group &lt;CFT-rg>

Oct
10 18 :36 :34 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;gds\_svc\_stop> for resource &lt;cft-gds>, resource group
&lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;gds\_svc\_stop> completed successfully for resource &lt;cft-gds>,
resource group &lt;CFT-rg>

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_stop> for resource &lt;cft-disk>, resource
group &lt;CFT-rg>, timeout &lt;1800> seconds

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;hastorageplus\_stop> completed successfully for resource &lt;cft-disk>,
resource group &lt;CFT-rg>

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;hafoip\_stop> for resource &lt;cft-ip>, resource group
&lt;CFT-rg>, timeout &lt;300> seconds

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;hafoip\_stop> completed successfully for resource &lt;cft-ip>,
resource group &lt;CFT-rg>

Oct
10 18 :36 :44 fleur Cluster.RGM.rgmd : \[ID 707948 daemon.notice\] launching
method &lt;hastorageplus\_postnet\_stop> for resource &lt;cft-disk>,
resource group &lt;CFT-rg>, timeout &lt;1800> seconds

Oct
10 18 :36 :45 fleur Cluster.RGM.rgmd : \[ID 148023 daemon.notice\] method
&lt;hastorageplus\_postnet\_stop> completed successfully for resource
&lt;cft-disk>, resource group &lt;CFT-rg>

Oct
10 18 :36 :46 fleur Cluster.Framework : \[ID 801593 daemon.notice\] stdout
: no longer primary for dsk/d16

### Switch overs

Switch-over the service to the "fleur" node:   

scswitch
–z –g CFT-rg –h fleur
