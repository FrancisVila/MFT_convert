{
    "title": "Additional information",
    "linkTitle": "Additional information",
    "weight": "270"
}# <span id="Using_AIX_with_IBM__Start_here"></span>Additional information for AIX/HACMP

This topic provides reference information for using Transfer CFT AIX
with IBM HACMP. Refer to the HACMP documentation for help in creating virtual IP addresses
and shared system files during cluster installation.

## Transfer CFT resources group

All resources are include in the same group, named CFT-rg:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/usr/es/sbin/cluster/utilities/claddgrp -g 'CFT-rg' \<br />
-r 'cascading' -n 'hacmp1 hacmp2'</td>
</tr>
</tbody>
</table>

This group is activated or switched over to one of the nodes. This avoids
having two Transfer CFT instances activated simultaneously on the cluster.

Command line description:

-   -g CFT-rg: resources group name  
-   -r 'cascading': cascading type  
-   -n 'hacmp1 hacmp2': names of the nodes used

### Application server

Creating the cft-service:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/usr/es/sbin/cluster/utilities/claddserv
–s ‘cft-service’ \<br />
–b ‘usr/es/sbin/cluster/local/cftstartFailover’ \<br />
–e ‘usr/es/sbin/cluster/local/cftstopFailover’</td>
</tr>
</tbody>
</table>

Command line description:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>–s ‘cft-service’: service name<br />
–b ‘usr/es/sbin/cluster/local/cftstartFailover’: startup script<br />
–e ‘usr/es/sbin/cluster/local/cftstopFailover’: shutdown script</td>
</tr>
</tbody>
</table>

This service must be declared to the CFT-rg ressourcegroup:

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>/usr/es/sbin/cluster/utilities/claddres
-g'CFT-rg' \<br />
NODE_PRIORITY_POLICY= SERVICE_LABEL='cft-ip' FILESYSTEM='/cft-vg' FSCHECK_TOOL='fsck'
RECOVERY_METHOD='sequential' EXPORT_FILESYSTEM= MOUNT_FILESYSTEM= NFS_NETWORK=
VOLUME_GROUP='cftvg' CONCURRENT_VOLUME_GROUP= DISK= AIX_CONNECTIONS_SERVICES=
AIX_FAST_CONNECT_SERVICES= SHARED_TAPE_RESOURCES= APPLICATIONS='cft-service'
TCP_CONNECTIONS= MISC_DATA= VG_AUTO_IMPORT='false' INACTIVE_TAKEOVER='false'
CASCADE_WO_FALLBACK='false' DISK_FENCING='false' SSA_DISK_FENCING='false'
FS_BEFORE_IPADDR='false'</td>
</tr>
</tbody>
</table>

 
