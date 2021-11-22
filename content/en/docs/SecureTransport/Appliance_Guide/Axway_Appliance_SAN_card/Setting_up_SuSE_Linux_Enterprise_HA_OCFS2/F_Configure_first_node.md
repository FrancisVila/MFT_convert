{
    "title": "Setup SLEHA with OCFS2 using multicast on the first node",
    "linkTitle": "Setup SLEHA with OCFS2 using multicast on the first node",
    "weight": "190"
}To setup SLEHA with OCFS2 using multicast on the first node:

> **Note:**
>
> Caution  
> Make sure you fulfill the following prerequisites.

1.  [Create SBD partition](#Create)
2.  [Initialize SBD](#Initiali)
3.  [Initialize the cluster](#Initiali2)
4.  [Configure SBD STONITH resource](#Configur)
5.  [Configure Distributed Lock Manager (DLM)](#Configur2)
6.  [Configure OCFS2](#Configur3)

<span id="Create"></span>

## Create SBD partition

Use the `fdisk` utility to create SBD partition on your storage.

> **Note:**
>
> In an environment where all nodes have access to shared storage, a small partition of the device is formatted for use with SBD. The size of the partition depends on the block size of the used disk (for example, 1 MB for standard SCSI disks with 512 byte block size or 4 MB for DASD disks with 4 kB block size). The initialization process creates a message layout on the device with slots for up to 255 nodes.

-   Press `p` to see current partition table
-   Press `n` to create new partition
-   Press `p` for primary partition
-   Select the correct size of your SBD
-   Press `w` to write the partition table

<!-- -->



    node115:~ # fdisk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877

     

    Welcome to fdisk (util-linux 2.33.2).

    Changes will remain in memory only, until you decide to write them.

    Be careful before using the write command.

     

     

    Command (m for help): p

    Disk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877: 2 GiB, 2147483648 bytes, 4194304 sectors

    Units: sectors of 1 * 512 = 512 bytes

    Sector size (logical/physical): 512 bytes / 512 bytes

    I/O size (minimum/optimal): 512 bytes / 4194304 bytesDisklabel type: dos

    Disk identifier: 0x228d0281

     

    Command (m for help): n

    Partition type

       p   primary (0 primary, 0 extended, 4 free)

       e   extended (container for logical partitions)

    Select (default p): p

    Partition number (1-4, default 1): 1

    First sector (8192-4194303, default 8192): 

    Last sector, +/-sectors or +/-size{K,M,G,T,P} (8192-4194303, default 4194303): +1M

     

    Created a new partition 1 of type 'Linux' and of size 1 MiB.

     

    Command (m for help): w

    The partition table has been altered.

> **Note:**
>
> Caution  
> If you see a message saying "Failed to add partition 1 to system: Invalid argument", reboot the system and continue with the setup.

<span id="Initiali"></span>

## Initialize SBD

Run the following command:


    node115:~ # sbd -d /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 -4 180 -1 90 create
    Initializing device /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1

     
    Creating version 2.1 header on device 4 (uuid: 73e6e254-703c-43bd-acd5-538a7f3d42ad)

    Initializing 255 slots on device 4

    Device /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 is initialized.

-   Use `-4` option to specify the timeout. In the example above, it is set to 180 seconds.

-   Use `-1` option to specify the timeout. In the example above, it is set to 90 seconds. The minimum allowed value for the emulated watchdog is 15 seconds.

-   You may use the following formula for timeout configuration:  

    `Timeout (msgwait) >= (Timeout (watchdog) * 2)        stonith-timeout = Timeout (msgwait) + 20%`

> **Note:**
>
> Caution  
> The following should be executed on all cluster nodes, not only on the first one!

1.  After SBD is initialized, edit the file `/etc/sysconfig/sbd` and search for "SBD\_DEVICE=".

2.  Edit the line and replace it with your SBD device:  


        SBD_DEVICE="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"

3.  Enable sbd service on all nodes:  



        node115:~ # systemctl enable sbd

        Created symlink from /etc/systemd/system/corosync.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.

        Created symlink from /etc/systemd/system/pacemaker.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.

        Created symlink from /etc/systemd/system/dlm.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.

<span id="Initiali2"></span>

## Initialize the cluster

Run the following command:



    node115:~ # sleha-init 
      Generating SSH key

      Configuring csync2

      Generating csync2 shared key (this may take a while)...done

      csync2 checking files...done

      
    Configure Corosync:

      This will configure the cluster messaging layer.  You will need

      to specify a network address over which to communicate (default

      is eth0's network, but you can use the network address of any

      active interface).

     
      IP or network address to bind to [10.134.64.115]

      Multicast address [239.124.194.226]

      Multicast port [5405]

      
    Configure SBD:

      If you have shared storage, for example a SAN or iSCSI target,

      you can use it avoid split-brain scenarios by configuring SBD.

      This requires a 1 MB partition, accessible to all nodes in the

      cluster.  The device path must be persistent and consistent

      across all nodes in the cluster, so /dev/disk/by-id/* devices

      are a good choice.  Note that all data on the partition you

      specify here will be destroyed.

     
    Do you wish to use SBD (y/n)? y

    SBD is already configured to use /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 - overwrite (y/n)? n

      Initializing SBD......done

      Hawk cluster interface is now running. To see cluster status, open:

        https://10.134.64.115:7630/

      Log in with username 'hacluster', password 'linux'

    WARNING: You should change the hacluster password to something more secure!

      Waiting for cluster..............done

      Loading initial cluster configuration

      
    Configure Administration IP Address:

      Optionally configure an administration virtual IP

      address. The purpose of this IP address is to

      provide a single IP that can be used to interact

      with the cluster, rather than using the IP address

      of any specific cluster node.
     
    Do you wish to configure a virtual IP address (y/n)? n
      Done (log saved to /var/log/ha-cluster-bootstrap.log)
     

-   If you have more than one network interface, enter the address of the interface dedicated for the pacemaker. If you have only one interface configured press enter.
-   Press `y` on prompt Do you wish to use SBD
-   Press `n` when prompted to overwrite the configuration
-   Press `n` on prompt for virtual IP address

<span id="Configur"></span>

## Configure SBD STONITH resource

1.  Run the `crm configure` command.

2.  Type `property stonith-enabled="true"`. This is the default configuration as clusters without STONITH are not supported. In case STONITH has been deactivated for testing purposes, make sure this parameter is set to `true` again.

3.  Type `property stonith-watchdog-timeout=0`.

4.  Type `property stonith-timeout="240s"` A `stonith-timeout` value of 240 would be appropriate if the `msgwait` timeout value for SBD was set to 60 seconds.

5.  Type `verify` to check your configuration.

6.  Type `commit` to save the changes.

7.  Type `edit stonith-sbd` to add your STONITH device. This runs Vi mode.  



        primitive stonith-sbd stonith:external/sbd \

         params pcmk_delay_max=30s \

         params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"

8.  Type `verify` to check your configuration

9.  Type `commit` to save the changes

10. Type `show` to see the configuration  



        crm(live/node115)configure# show

        node 176570483: node115

        primitive stonith-sbd stonith:external/sbd \

                params pcmk_delay_max=30s \

                params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"property cib-bootstrap-options: \

                have-watchdog=true \

                dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \

                cluster-infrastructure=corosync \

                cluster-name=hacluster \

                stonith-enabled=true \

                stonith-watchdog-timeout=0 \

                stonith-timeout=240s

        rsc_defaults rsc-options: \

                resource-stickiness=1 \

                migration-threshold=3

        op_defaults op-options: \

                timeout=600 \

                record-pending=true

<span id="Configur2"></span>

## Configure Distributed Lock Manager (DLM)

1.  Run the `crm configure` command.

2.  Type `primitive dlm ocf:pacemaker:controld op monitor interval="60" timeout="60"`.

3.  Type `group g-storage dlm`.

4.  Type `clone cl-storage g-storage meta interleave=true target-role=Started`.

5.  Type `verify` to check your configuration.

6.  Type `commit` to save the changes.

7.  Type `show` to see the configuration. See <a href="../verifiy_cluster" class="MCXref xref">Verify cluster configuration</a>.  



        crm(live/node115)configure# show

        node 176570483: node115

        primitive dlm ocf:pacemaker:controld \

                op monitor interval=60 timeout=60

        primitive stonith-sbd stonith:external/sbd \

                params pcmk_delay_max=30s \
                params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"
        group g-storage dlmclone cl-storage g-storage \

                meta interleave=true target-role=Started

        property cib-bootstrap-options: \        have-watchdog=true \

                dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \

                cluster-infrastructure=corosync \

                cluster-name=hacluster \

                stonith-enabled=true \

                stonith-watchdog-timeout=0 \

                stonith-timeout=240srsc_defaults rsc-options: \

                resource-stickiness=1 \

                migration-threshold=3

        op_defaults op-options: \

                timeout=600 \

                record-pending=true

<span id="Configur3"></span>

## Configure OCFS2

1.  [Create partition for OCFS2](#Create2)
2.  [Create OCFS2 filesystem](#Create3)
3.  [Mount OCFS2 file system](#Mount)

<span id="Create2"></span>

### Create partition for OCFS2

You may skip this step if you already have partition on your SAN.

Use the `fdisk` utilty to create additional partition on your SAN:



    node115:~ # fdisk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877

     

    Welcome to fdisk (util-linux 2.33.2).

    Changes will remain in memory only, until you decide to write them.

    Be careful before using the write command.

     

     

    Command (m for help): nPartition type

       p   primary (1 primary, 0 extended, 3 free)

       e   extended (container for logical partitions)Select (default p): p

    Partition number (2-4, default 2): 

    First sector (10240-4194303, default 16384): 

    Last sector, +/-sectors or +/-size{K,M,G,T,P} (16384-4194303, default 4194303): 

     

    Created a new partition 2 of type 'Linux' and of size 2 GiB.

     

    Command (m for help): w

    The partition table has been altered.

1.  Press `n` for new partition.
2.  Press `p` for primary partition.
3.  Select the number of partition.
4.  Select the size of partition.
5.  Press `w` to save the partition table.

You may need to reboot your system.

<span id="Create3"></span>

### Create OCFS2 filesystem

Run the following command:



    node115:~ # mkfs.ocfs2 /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2

    mkfs.ocfs2 1.8.5

    Cluster stack: pcmk

    Cluster name: hacluster

    Stack Flags: 0x0

    NOTE: Feature extended slot map may be enabled

    Label: 
    Features: sparse extended-slotmap backup-super unwritten inline-data strict-journal-super xattr indexed-dirs refcount discontig-bg append-dio
    Block size: 4096 (12 bits)

    Cluster size: 4096 (12 bits)

    Volume size: 2139095040 (522240 clusters) (522240 blocks)

    Cluster groups: 17 (tail covers 6144 clusters, rest cover 32256 clusters)

    Extent allocator size: 4194304 (1 groups)

    Journal size: 67108864

    Node slots: 2

    Creating bitmaps: done

    Initializing superblock: done

    Writing system files: done

    Writing superblock: done

    Writing backup superblock: 1 block(s)

    Formatting Journals: done

    Growing extent allocator: done

    Formatting slot map: done

    Formatting quota files: done

    Writing lost+found: done

    mkfs.ocfs2 successful

For more information about options, refer to man page. Also see .

<span id="Mount"></span>

### Mount OCFS2 file system

1.  Run the `crm configure` command and type:  





         

         

         



         



         


      
    Where `/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2` is your OCFS2 partition and `/sanmount` is directory where it should be mounted

2.  Type `modgroup g-storage add ocfs2-1` to add ocfs2 primitive to g-storage group.

3.  Type `verify` to check your configuration.

4.  Type `commit` to save the changes.

5.  Type `show` to see the configuration.  



        node115:~ # crm configure
        crm(live/node115)configure# primitive ocfs2-1 ocf:heartbeat:Filesystem \   >   params device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2" directory="/sanmount" \
           >   fstype="ocfs2" options="acl" \

         

         

           >   op monitor interval="20" timeout="40" \

           >   op start timeout="60" op stop timeout="60" \

           >   meta target-role="Started"

        crm(live/node115)configure# modgroup g-storage add ocfs2-1

        crm(live/node115)configure# verify

        crm(live/node115)configure# commit

        crm(live/node115)configure# show

        node 176570483: node115

        primitive dlm ocf:pacemaker:controld \

                op monitor interval=60 timeout=60primitive ocfs2-1 Filesystem \

                params device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2" directory="/sanmount" fstype=ocfs2 options=acl \

                op monitor interval=20 timeout=40 \

                op start timeout=60 interval=0 \        op stop timeout=60 interval=0 \

                meta target-role=Startedprimitive stonith-sbd stonith:external/sbd \

                params pcmk_delay_max=30s \

                params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"group g-storage dlm ocfs2-1

        clone cl-storage g-storage \

                meta interleave=true target-role=Started

        property cib-bootstrap-options: \

                have-watchdog=true \

                dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \

                cluster-infrastructure=corosync \

                cluster-name=hacluster \

                stonith-enabled=true \

                stonith-watchdog-timeout=0 \

                stonith-timeout=240s

        rsc_defaults rsc-options: \

                resource-stickiness=1 \

                migration-threshold=3

        op_defaults op-options: \

                timeout=600 \

                record-pending=true

        crm(live/node115)configure#

6.  Type `quit` to exit the crm shell.

7.  Run `mount | grep ocfs2` to check whether the filesystem is mounted:
