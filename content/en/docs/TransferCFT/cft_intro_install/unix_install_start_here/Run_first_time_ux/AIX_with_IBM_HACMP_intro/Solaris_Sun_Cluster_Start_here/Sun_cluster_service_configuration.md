{
    "title": "Sun  cluster service configuration",
    "linkTitle": "Sun cluster service configuration",
    "weight": "260"
}This topic describes the Transfer CFT Sun cluster service configuration parameters and resource controls. To integrate Transfer CFT with Sun cluster, use the `SCRGADM `command to
record and remove resources.

## About the scrgadm command

Enter the command:

<span id="CFT_resources_group"></span>

### Transfer CFT resources group

All resources are included in the same group, named `CFT-rg`:

scrgadm –a –g CFT-rg

This group is activated or switched over to one of the nodes to avoid
having two Transfer CFT instances activated simultaneously on the same
cluster.

View the command line description


|  Command  |  Description  |
| --- | --- |
|  -a  |  resource addition (add)  |
|  -g CFT-rg  |  resources group name  |


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

<span id="Shared_file_system"></span>

#### Shared file system

These tests were performed using a single shared file system. It is
declared as follows:

scrgadm –a –g CFT-rg –t SUNM.HAStoragePlus –j cft-disk \\  
–x FilesystemMountpoints=/global/cft

View the command line description

<span id="Generic_data_service_CFT"></span>

#### Generic data service CFT

The following is the declaration of the GDS for Transfer CFT:

View the command line description

The default parameters are adequate for the test
environment.
