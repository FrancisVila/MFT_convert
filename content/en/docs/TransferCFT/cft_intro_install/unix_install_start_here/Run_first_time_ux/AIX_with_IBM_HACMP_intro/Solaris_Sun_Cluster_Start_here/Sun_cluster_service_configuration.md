{
    "title": "Sun  cluster service configuration",
    "linkTitle": "Sun cluster service configuration",
    "weight": "260"
}This topic describes the Transfer CFT Sun cluster service configuration parameters and resource controls. To integrate Transfer CFT with Sun cluster, use the <span class="code">SCRGADM </span>command to
record and remove resources.

## About the scrgadm command

Enter the command:



    scrgadm -p[v[v]] [-t <Resource_Type_name>] 
     \
    [-g <Resource_Group_name>] \
    [-j <Resource_name>]
    scrgadm -a -t <Resource_Type_name> 
     [-f <RT_registration_file_path>] \
    [-h RT_installed_node_list]
    scrgadm -c -t <Resource_Type_name> 
     -h RT_installed_node_list
    scrgadm -r -t <Resource_Type_name>
    scrgadm -a | -c -g <Resource_Group_name> 
     [-h RT_installed_node_list]
    [-y <property>]
    scrgadm -r -g <RG_name>
    scrgadm -a -j <Resource_name> -t <Resource_Type_name> 
     \
    -g <RG_name> [-y <property> 
     [-y <property>]] \
    [-x <property> [-x <property>]]
    scrgadm -c -j <Resource_name> [-y 
     <property> [-y <property>]] \
    [-x <property> -x <property>]]
    scrgadm -r -j <Resource_name>
    scrgadm -a -L -g <LogicalHost_RG_Name> 
     [-j <Resource_name>] \
    -l hostname[,hostname,...] [-n nafo@node[,nafo@node,...]]
    [-y <property> [-y <property>]]
    scrgadm -a -S -g <SharedAddress_RG_Name> 
     [-j <Resource_name>] \
    -l hostname[,hostname,...] [-n nafo@node[,nafo@node,...]] 
     \
    [-X aux_node[,aux_node,...]] [-y <property> 
     [-y <property>]]

<span id="CFT_resources_group"></span>

### Transfer CFT resources group

All resources are included in the same group, named <span class="code">CFT-rg</span>:

scrgadm –a –g CFT-rg

This group is activated or switched over to one of the nodes to avoid
having two Transfer CFT instances activated simultaneously on the same
cluster.

View the command line description

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-a</p>         </td>
         <td><p>resource addition (add)</p>         </td>
      </tr>
      <tr>
         <td><p>-g CFT-rg</p>         </td>
         <td><p>resources group name</p>         </td>
      </tr>
   </tbody>
</table>

<span id="CFT_resources"></span>

### Transfer CFT resources

There are three resources for the CFT-rg group:

-   [Virtual
    IP](#Virtual_IP)
-   [Shared
    file system](#Shared_file_system)
-   [GDS](#Generic_data_service_CFT):
    the Transfer CFT start, stop, and test scripts

<span id="Virtual_IP"></span>

#### Virtual IP

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

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-a</p>         </td>
         <td><p>resource addition (add)</p>         </td>
      </tr>
      <tr>
         <td><p>–L</p>         </td>
         <td><p>logical name resource type</p>         </td>
      </tr>
      <tr>
         <td><p>-g CFT-rg</p>         </td>
         <td><p>resources group name</p>         </td>
      </tr>
      <tr>
         <td><p>-j cft-ip</p>         </td>
         <td><p>resource name</p>         </td>
      </tr>
      <tr>
         <td><p>–l cft-ip</p>         </td>
         <td><p>logical name (as defined in /etc/hosts
in our test)</p>         </td>
      </tr>
      <tr>
         <td><p>-n nafo0@1,nafo0@2</p>         </td>
         <td><p>use of nafo interfaces 1 and 2</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Shared_file_system"></span>

#### Shared file system

These tests were performed using a single shared file system. It is
declared as follows:

scrgadm –a –g CFT-rg –t SUNM.HAStoragePlus –j cft-disk \\  
–x FilesystemMountpoints=/global/cft

View the command line description

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-a</p>         </td>
         <td><p>resource addition (add)</p>         </td>
      </tr>
      <tr>
         <td><p>-g CFT-rg</p>         </td>
         <td><p>resources group name</p>         </td>
      </tr>
      <tr>
         <td><p>-t SUNW.HAStoragePlus</p>         </td>
         <td><p>GDS resource type</p>         </td>
      </tr>
      <tr>
         <td><p>-j cft-disk</p>         </td>
         <td><p>resource name</p>         </td>
      </tr>
      <tr>
         <td><p>-x FilesystemMountpoints=/global/cft</p>         </td>
         <td><p>mount point</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Generic_data_service_CFT"></span>

#### Generic data service CFT

The following is the declaration of the GDS for Transfer CFT:


    scrgadm –a –g CFT-rg –t SUNW.gds –j cft-gds \
    –x Start_command=/global/cft/cftstartFailover \
    –x Stop_command=/global/cft/cftstopFailover \
    –x Probe_command=/global/cft/cftprobeFailover \
    –y Port_list="1765/tcp,1766/tcp,1767/tcp" \
    –y Resource_dependencies=cft-ip,cft-disk

View the command line description

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command</p>         </th>
<th class="HeadD-Column1-Header1"><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>-a</p>         </td>
         <td><p>resource addition (add)</p>         </td>
      </tr>
      <tr>
         <td><p>-g CFT-rg</p>         </td>
         <td><p>resources group name</p>         </td>
      </tr>
      <tr>
         <td><p>-t SUNW.gds</p>         </td>
         <td><p>GDS resource type</p>         </td>
      </tr>
      <tr>
         <td><p>-j cft-gds</p>         </td>
         <td><p>resource name</p>         </td>
      </tr>
      <tr>
         <td><p>-x Start_command= /global/cft/cftstartFailover</p>         </td>
         <td><p>command definition for startup</p>         </td>
      </tr>
      <tr>
         <td><p>-x Stop_command= /global/cft/cftstopFailover</p>         </td>
         <td><p>command definition for stop</p>         </td>
      </tr>
      <tr>
         <td><p>-x Probe_command= /global/cft/cftprobeFailover</p>         </td>
         <td><p>command definition for probe</p>         </td>
      </tr>
      <tr>
         <td><p>–y Port_list=1765/tcp</p>         </td>
         <td><p>verification of the listening ports of Transfer CFT in
TCP (parameters of the Transfer CFT cftprot cards)</p>         </td>
      </tr>
      <tr>
         <td><p>–y Resource_dependencies= cft-ip,cft-disk</p>         </td>
         <td><p>You can activate GDX on a node only if the cft-ip and cft-disk
resources are online. In the event of problems with one of these two resources,
Sun Custer attempts to restart the faulty resource, or to switch over
to another node</p>         </td>
      </tr>
   </tbody>
</table>

The default parameters are adequate for the test
environment.
