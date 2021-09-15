{
    "title": "Sun cluster service configuration",
    "linkTitle": "Sun cluster service configuration",
    "weight": "290"
}# <span id="Sun_cluster_service_configuration"></span>Sun cluster service configuration

This topic describes the Transfer CFT Sun cluster service configuration parameters and resource controls. To integrate Transfer CFT with Sun cluster, use the SCRGADM command to
record and remove resources.

## About the scrgadm command

Enter the command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>scrgadm -p[v[v]] [-t &lt;Resource_Type_name&gt;] 
 \<br/>[-g &lt;Resource_Group_name&gt;] \<br/>[-j &lt;Resource_name&gt;]<br/>scrgadm -a -t &lt;Resource_Type_name&gt; 
 [-f &lt;RT_registration_file_path&gt;] \<br/>[-h RT_installed_node_list]<br/>scrgadm -c -t &lt;Resource_Type_name&gt; 
 -h RT_installed_node_list<br/>scrgadm -r -t &lt;Resource_Type_name&gt;<br/>scrgadm -a | -c -g &lt;Resource_Group_name&gt; 
 [-h RT_installed_node_list]<br/>[-y &lt;property&gt;]<br/>scrgadm -r -g &lt;RG_name&gt;<br/>scrgadm -a -j &lt;Resource_name&gt; -t &lt;Resource_Type_name&gt; 
 \<br/>-g &lt;RG_name&gt; [-y &lt;property&gt; 
 [-y &lt;property&gt;]] \<br/>[-x &lt;property&gt; [-x &lt;property&gt;]]<br/>scrgadm -c -j &lt;Resource_name&gt; [-y 
 &lt;property&gt; [-y &lt;property&gt;]] \<br/>[-x &lt;property&gt; -x &lt;property&gt;]]<br/>scrgadm -r -j &lt;Resource_name&gt;<br/>scrgadm -a -L -g &lt;LogicalHost_RG_Name&gt; 
 [-j &lt;Resource_name&gt;] \<br/>-l hostname[,hostname,...] [-n nafo@node[,nafo@node,...]]<br/>[-y &lt;property&gt; [-y &lt;property&gt;]]<br/>scrgadm -a -S -g &lt;SharedAddress_RG_Name&gt; 
 [-j &lt;Resource_name&gt;] \<br/>-l hostname[,hostname,...] [-n nafo@node[,nafo@node,...]] 
 \<br/>[-X aux_node[,aux_node,...]] [-y &lt;property&gt; 
 [-y &lt;property&gt;]]</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="CFT_resources_group"></span>Transfer CFT resources group

All resources are included in the same group, named CFT-rg:

scrgadm –a –g CFT-rg

This group is activated or switched over to one of the nodes to avoid
having two Transfer CFT instances activated simultaneously on the same
cluster.

View the command line description

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Command</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="30.781%">
            <p>-a</p>
         </td>
         <td width="69.219%">
            <p>resource addition (add)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-g CFT-rg</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>resources group name</p>
         </td>
      </tr>
   </tbody>
</table>

### <span id="CFT_resources"></span>Transfer CFT resources

There are three resources for the CFT-rg group:

-   [Virtual
    IP](#virtual_ip)
-   [Shared
    file system](#shared_file_system)
-   [GDS](#generic_data_service_cft):
    the Transfer CFT start, stop, and test scripts

#### <span id="Virtual_IP"></span>Virtual IP

The public interface support has changed between the versions 3.0 and
3.1 of Sun Cluster. Consequently, the declaration of the virtual IP is
different between the two versions. The following interface types are
used:

-   NAFO, Network Adapter
    Fail Over, for SC 3.0
-   IPMP, IP MultiPathing,
    for SC 3.1

The virtual IP is added as follows on Sun Cluster version 3.0:

scrgadm
–a –L –g CFT-rg –j cft\_ip –l cft-ip –n nafo0@1,nafo0@2

For Sun Cluster 3.1 the command is:

scrgadm
–a –L –g CFT-rg –j cft\_ip –l cft-ip –n ipmp0@1,ipmp0@2

View the command line description

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Command</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td>
            <p>-a</p>
         </td>
         <td>
            <p>resource addition (add)</p>
         </td>
      </tr>
      <tr valign="top">
         <td>
            <p>–L</p>
         </td>
         <td>
            <p>logical name resource type</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>-g CFT-rg</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>resources group name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>-j cft-ip</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>resource name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>–l cft-ip</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>logical name (as defined in /etc/hosts 
 in our test)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1">
            <p>-n nafo0@1,nafo0@2</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>use of nafo interfaces 1 and 2</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Shared_file_system"></span>Shared file system

These tests were performed using a single shared file system. It is
declared as follows:

scrgadm –a –g CFT-rg –t SUNM.HAStoragePlus –j cft-disk \\  
–x FilesystemMountpoints=/global/cft

View the command line description

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Command</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="30.781%">
            <p>-a</p>
         </td>
         <td width="69.219%">
            <p>resource addition (add)</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="30.781%">
            <p>-g CFT-rg</p>
         </td>
         <td width="69.219%">
            <p>resources group name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-t SUNW.HAStoragePlus</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>GDS resource type</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-j cft-disk</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>resource name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-x FilesystemMountpoints=/global/cft</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>mount point</p>
         </td>
      </tr>
   </tbody>
</table>

#### <span id="Generic_data_service_CFT"></span>Generic data service CFT

The following is the declaration of the GDS for Transfer CFT:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>scrgadm –a –g CFT-rg –t SUNW.gds –j cft-gds \<br/>–x Start_command=/global/cft/cftstartFailover \<br/>–x Stop_command=/global/cft/cftstopFailover \<br/>–x Probe_command=/global/cft/cftprobeFailover \<br/>–y Port_list="1765/tcp,1766/tcp,1767/tcp" \<br/>–y Resource_dependencies=cft-ip,cft-disk         </td>
      </tr>
   </tbody>
</table>

View the command line description

<table cellspacing="0" width="90%">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Command</p>
</th>
         <th>
            <p>Description</p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr valign="top">
         <td width="30.781%">
            <p>-a</p>
         </td>
         <td width="69.219%">
            <p>resource addition (add)</p>
         </td>
      </tr>
      <tr valign="top">
         <td width="30.781%">
            <p>-g CFT-rg</p>
         </td>
         <td width="69.219%">
            <p>resources group name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-t SUNW.gds</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>GDS resource type</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-j cft-gds</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>resource name</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-x Start_command= /global/cft/cftstartFailover</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>command definition for startup</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-x Stop_command= /global/cft/cftstopFailover</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>command definition for stop</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>-x Probe_command= /global/cft/cftprobeFailover</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>command definition for probe</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>–y Port_list=1765/tcp</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>verification of the listening ports of Transfer CFT in 
 TCP (parameters of the Transfer CFT cftprot cards)</p>
         </td>
      </tr>
      <tr valign="top">
         <td colspan="1" rowspan="1" width="30.781%">
            <p>–y Resource_dependencies= cft-ip,cft-disk</p>
         </td>
         <td colspan="1" rowspan="1" width="69.219%">
            <p>You can activate GDX on a node only if the cft-ip and cft-disk 
 resources are online. In the event of problems with one of these two resources, 
 Sun Custer attempts to restart the faulty resource, or to switch over 
 to another node</p>
         </td>
      </tr>
   </tbody>
</table>

The default parameters are adequate for the test
environment.
