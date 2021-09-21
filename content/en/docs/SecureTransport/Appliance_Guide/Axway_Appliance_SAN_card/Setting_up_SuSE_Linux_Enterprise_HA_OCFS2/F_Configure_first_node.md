{
    "title": "Setup SLEHA with OCFS2 using multicast on the first node",
    "linkTitle": "Setup SLEHA with OCFS2 using multicast on the first node",
    "weight": "190"
}To setup SLEHA with OCFS2 using multicast on the first node:

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">Make sure you fulfill the following <a href="..//securetransport/appliance_guide/axway_appliance_san_card/setting_up_suse_linux_enterprise_ha_ocfs2">prerequisites</a>.         </td>
      </tr>
</table>

1.  [Create SBD partition](#create)
2.  [Initialize SBD](#initiali)
3.  [Initialize the cluster](#initiali2)
4.  [Configure SBD STONITH resource](#configur)
5.  [Configure Distributed Lock Manager (DLM)](#configur2)
6.  [Configure OCFS2](#configur3)

## <span id="Create"></span>Create SBD partition

Use the `fdisk` utility to create SBD partition on your storage.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In an environment where all nodes have access to shared storage, a small partition of the device is formatted for use with SBD. The size of the partition depends on the block size of the used disk (for example, 1 MB for standard SCSI disks with 512 byte block size or 4 MB for DASD disks with 4 kB block size). The initialization process creates a message layout on the device with slots for up to 255 nodes.         </td>
      </tr>
</table>

-   Press `p` to see current partition table
-   Press `n` to create new partition
-   Press `p` for primary partition
-   Select the correct size of your SBD
-   Press `w` to write the partition table

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # fdisk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877</code>
</p>
            <p><code> </code>
</p>
            <p><code>Welcome to fdisk (util-linux 2.33.2).</code>
</p>
            <p><code>Changes will remain in memory only, until you decide to write them.</code>
</p>
            <p><code>Be careful before using the write command.</code>
</p>
            <p><code> </code>
</p>
            <p><code> </code>
</p>
            <p><code>Command (m for help): p</code>
</p>
            <p><code>Disk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877: 2 GiB, 2147483648 bytes, 4194304 sectors</code>
</p>
            <p><code>Units: sectors of 1 * 512 = 512 bytes</code>
</p>
            <p><code>Sector size (logical/physical): 512 bytes / 512 bytes</code>
</p>
            <p><code>I/O size (minimum/optimal): 512 bytes / 4194304 bytes</code><code>Disklabel type: dos</code>
</p>
            <p><code>Disk identifier: 0x228d0281</code>
</p>
            <p><code> </code>
</p>
            <p><code>Command (m for help): n</code>
</p>
            <p><code>Partition type</code>
</p>
            <p><code>   p   primary (0 primary, 0 extended, 4 free)</code>
</p>
            <p><code>   e   extended (container for logical partitions)</code>
</p>
            <p><code>Select (default p): p</code>
</p>
            <p><code>Partition number (1-4, default 1): 1</code>
</p>
            <p><code>First sector (8192-4194303, default 8192): </code>
</p>
            <p><code>Last sector, +/-sectors or +/-size{K,M,G,T,P} (8192-4194303, default 4194303): +1M</code>
</p>
            <p><code> </code>
</p>
            <p><code>Created a new partition 1 of type 'Linux' and of size 1 MiB.</code>
</p>
            <p><code> </code>
</p>
            <p><code>Command (m for help): w</code>
</p>
            <p><code>The partition table has been altered.</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">If you see a message saying "Failed to add partition 1 to system: Invalid argument", reboot the system and continue with the setup.         </td>
      </tr>
</table>

## <span id="Initiali"></span>Initialize SBD

Run the following command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre><code>node115:~ # sbd -d /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 -4 180 -1 90 create</code></pre>
            <p><code>Initializing device /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1</code>
</p>
            <p> </p>
            <p><code>Creating version 2.1 header on device 4 (uuid: 73e6e254-703c-43bd-acd5-538a7f3d42ad)</code>
</p>
            <p><code>Initializing 255 slots on device 4</code>
</p>
            <p><code>Device /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 is initialized.</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

-   Use `-4` option to specify the msgwait timeout. In the example above, it is set to 180 seconds.

-   Use `-1` option to specify the watchdog timeout. In the example above, it is set to 90 seconds. The minimum allowed value for the emulated watchdog is 15 seconds.

-   You may use the following formula for timeout configuration:
      
    

    `Timeout (msgwait) >= (Timeout (watchdog) * 2)        stonith-timeout = Timeout (msgwait) + 20%`

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Caution  </b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Caution  &lt;/b&gt;" valign="top">The following should be executed on all cluster nodes, not only on the first one!         </td>
      </tr>
</table>

1.  After SBD is initialized, edit the file `/etc/sysconfig/sbd` and search for "SBD\_DEVICE=".

2.  Edit the line and replace it with your SBD device:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><code>SBD_DEVICE="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"</code>
         </td>
      </tr>
   </tbody>
</table>

3.  Enable sbd service on all nodes:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # systemctl enable sbd</code>
</p>
            <p><code>Created symlink from /etc/systemd/system/corosync.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.</code>
</p>
            <p><code>Created symlink from /etc/systemd/system/pacemaker.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.</code>
</p>
            <p><code>Created symlink from /etc/systemd/system/dlm.service.requires/sbd.service to /usr/lib/systemd/system/sbd.service.</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Initiali2"></span>Initialize the cluster

Run the following command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # sleha-init</code> </p>
            <p><code>  Generating SSH key</code>
</p>
            <p><code>  Configuring csync2</code>
</p>
            <p><code>  Generating csync2 shared key (this may take a while)...done</code>
</p>
            <p><code>  csync2 checking files...done</code>
</p>
            <p>  </p>
            <p><code>Configure Corosync:</code>
</p>
            <p><code>  This will configure the cluster messaging layer.  You will need</code>
</p>
            <p><code>  to specify a network address over which to communicate (default</code>
</p>
            <p><code>  is eth0's network, but you can use the network address of any</code>
</p>
            <p><code>  active interface).</code>
</p>
            <p> </p>
            <p><code>  IP or network address to bind to [10.134.64.115]</code>
</p>
            <p><code>  Multicast address [239.124.194.226]</code>
</p>
            <p><code>  Multicast port [5405]</code>
</p>
            <p>  </p>
            <p><code>Configure SBD:</code>
</p>
            <p><code>  If you have shared storage, for example a SAN or iSCSI target,</code>
</p>
            <p><code>  you can use it avoid split-brain scenarios by configuring SBD.</code>
</p>
            <p><code>  This requires a 1 MB partition, accessible to all nodes in the</code>
</p>
            <p><code>  cluster.  The device path must be persistent and consistent</code>
</p>
            <p><code>  across all nodes in the cluster, so /dev/disk/by-id/* devices</code>
</p>
            <p><code>  are a good choice.  Note that all data on the partition you</code>
</p>
            <p><code>  specify here will be destroyed.</code>
</p>
            <p> </p>
            <p><code>Do you wish to use SBD (y/n)? y</code>
</p>
            <p><code>SBD is already configured to use /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1 - overwrite (y/n)? n</code>
</p>
            <p><code>  Initializing SBD......done</code>
</p>
            <p><code>  Hawk cluster interface is now running. To see cluster status, open:</code>
</p>
            <p><code>    https://10.134.64.115:7630/</code>
</p>
            <p><code>  Log in with username 'hacluster', password 'linux'</code>
</p>
            <p><code>WARNING: You should change the hacluster password to something more secure!</code>
</p>
            <p><code>  Waiting for cluster..............done</code>
</p>
            <p><code>  Loading initial cluster configuration</code>
</p>
            <p>  </p>
            <p><code>Configure Administration IP Address:</code>
</p>
            <p><code>  Optionally configure an administration virtual IP</code>
</p>
            <p><code>  address. The purpose of this IP address is to</code>
</p>
            <p><code>  provide a single IP that can be used to interact</code>
</p>
            <p><code>  with the cluster, rather than using the IP address</code>
</p>
            <p>  of any specific cluster node.</p>
            <p> </p>
            <p>Do you wish to configure a virtual IP address (y/n)? n</p>
            <p>  Done (log saved to /var/log/ha-cluster-bootstrap.log)</p>
            <p><code> </code>
</p>
         </td>
      </tr>
   </tbody>
</table>

-   If you have more than one network interface, enter the address of the interface dedicated for the pacemaker. If you have only one interface configured press enter.
-   Press `y` on prompt Do you wish to use SBD
-   Press `n` when prompted to overwrite the configuration
-   Press `n` on prompt for virtual IP address

## <span id="Configur"></span>Configure SBD STONITH resource

1.  Run the `crm configure` command.

2.  Type `property stonith-enabled="true"`. This is the default configuration as clusters without STONITH are not supported. In case STONITH has been deactivated for testing purposes, make sure this parameter is set to `true` again.

3.  Type `property stonith-watchdog-timeout=0`.

4.  Type `property stonith-timeout="240s"` A `stonith-timeout` value of 240 would be appropriate if the `msgwait` timeout value for SBD was set to 60 seconds.

5.  Type `verify` to check your configuration.

6.  Type `commit` to save the changes.

7.  Type `edit stonith-sbd` to add your STONITH device. This runs Vi mode.  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>primitive stonith-sbd stonith:external/sbd \</code>
</p>
            <p><code> params pcmk_delay_max=30s \</code>
</p>
            <p><code> params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

8.  Type `verify` to check your configuration

9.  Type `commit` to save the changes

10. Type `show` to see the configuration  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>crm(live/node115)configure# show</code>
</p>
            <p><code>node 176570483: node115</code>
</p>
            <p><code>primitive stonith-sbd stonith:external/sbd \</code>
</p>
            <p><code>        params pcmk_delay_max=30s \</code>
</p>
            <p><code>        params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"</code><code>property cib-bootstrap-options: \</code>
</p>
            <p><code>        have-watchdog=true \</code>
</p>
            <p><code>        dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \</code>
</p>
            <p><code>        cluster-infrastructure=corosync \</code>
</p>
            <p><code>        cluster-name=hacluster \</code>
</p>
            <p><code>        stonith-enabled=true \</code>
</p>
            <p><code>        stonith-watchdog-timeout=0 \</code>
</p>
            <p><code>        stonith-timeout=240s</code>
</p>
            <p><code>rsc_defaults rsc-options: \</code>
</p>
            <p><code>        resource-stickiness=1 \</code>
</p>
            <p><code>        migration-threshold=3</code>
</p>
            <p><code>op_defaults op-options: \</code>
</p>
            <p><code>        timeout=600 \</code>
</p>
            <p><code>        record-pending=true</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Configur2"></span>Configure Distributed Lock Manager (DLM)

1.  Run the `crm configure` command.

2.  Type `primitive dlm ocf:pacemaker:controld op monitor interval="60" timeout="60"`.

3.  Type `group g-storage dlm`.

4.  Type `clone cl-storage g-storage meta interleave=true target-role=Started`.

5.  Type `verify` to check your configuration.

6.  Type `commit` to save the changes.

7.  Type `show` to see the configuration. See [Verify cluster configuration](../verifiy_cluster).  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>crm(live/node115)configure# show</code>
</p>
            <p><code>node 176570483: node115</code>
</p>
            <p><code>primitive dlm ocf:pacemaker:controld \</code>
</p>
            <p><code>        op monitor interval=60 timeout=60</code>
</p>
            <p><code>primitive stonith-sbd stonith:external/sbd \</code>
</p>
            <p><code>        params pcmk_delay_max=30s \</code>
</p><pre><code>        params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"</code></pre>
            <p><code>group g-storage dlm</code><code>clone cl-storage g-storage \</code>
</p>
            <p><code>        meta interleave=true target-role=Started</code>
</p>
            <p><code>property cib-bootstrap-options: \</code><code>        have-watchdog=true \</code>
</p>
            <p><code>        dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \</code>
</p>
            <p><code>        cluster-infrastructure=corosync \</code>
</p>
            <p><code>        cluster-name=hacluster \</code>
</p>
            <p><code>        stonith-enabled=true \</code>
</p>
            <p><code>        stonith-watchdog-timeout=0 \</code>
</p>
            <p><code>        stonith-timeout=240s</code><code>rsc_defaults rsc-options: \</code>
</p>
            <p><code>        resource-stickiness=1 \</code>
</p>
            <p><code>        migration-threshold=3</code>
</p>
            <p><code>op_defaults op-options: \</code>
</p>
            <p><code>        timeout=600 \</code>
</p>
            <p><code>        record-pending=true</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="Configur3"></span>Configure OCFS2

1.  [Create partition for OCFS2](#create2)
2.  [Create OCFS2 filesystem](#create3)
3.  [Mount OCFS2 file system](#mount)

### <span id="Create2"></span>Create partition for OCFS2

You may skip this step if you already have partition on your SAN.

Use the `fdisk` utilty to create additional partition on your SAN:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # fdisk /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877</code>
</p>
            <p><code> </code>
</p>
            <p><code>Welcome to fdisk (util-linux 2.33.2).</code>
</p>
            <p><code>Changes will remain in memory only, until you decide to write them.</code>
</p>
            <p><code>Be careful before using the write command.</code>
</p>
            <p><code> </code>
</p>
            <p><code> </code>
</p>
            <p><code>Command (m for help): n</code><code>Partition type</code>
</p>
            <p><code>   p   primary (1 primary, 0 extended, 3 free)</code>
</p>
            <p><code>   e   extended (container for logical partitions)</code><code>Select (default p): p</code>
</p>
            <p><code>Partition number (2-4, default 2): </code>
</p>
            <p><code>First sector (10240-4194303, default 16384): </code>
</p>
            <p><code>Last sector, +/-sectors or +/-size{K,M,G,T,P} (16384-4194303, default 4194303): </code>
</p>
            <p><code> </code>
</p>
            <p><code>Created a new partition 2 of type 'Linux' and of size 2 GiB.</code>
</p>
            <p><code> </code>
</p>
            <p><code>Command (m for help): w</code>
</p>
            <p><code>The partition table has been altered.</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

1.  Press `n` for new partition.
2.  Press `p` for primary partition.
3.  Select the number of partition.
4.  Select the size of partition.
5.  Press `w` to save the partition table.

You may need to reboot your system.

### <span id="Create3"></span>Create OCFS2 filesystem

Run the following command:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # mkfs.ocfs2 /dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2</code>
</p>
            <p><code>mkfs.ocfs2 1.8.5</code>
</p>
            <p><code>Cluster stack: pcmk</code>
</p>
            <p><code>Cluster name: hacluster</code>
</p>
            <p><code>Stack Flags: 0x0</code>
</p>
            <p><code>NOTE: Feature extended slot map may be enabled</code>
</p>
            <p><code>Label: </code>
</p><pre><code>Features: sparse extended-slotmap backup-super unwritten inline-data strict-journal-super xattr indexed-dirs refcount discontig-bg append-dio</code></pre>
            <p><code>Block size: 4096 (12 bits)</code>
</p>
            <p><code>Cluster size: 4096 (12 bits)</code>
</p>
            <p><code>Volume size: 2139095040 (522240 clusters) (522240 blocks)</code>
</p>
            <p><code>Cluster groups: 17 (tail covers 6144 clusters, rest cover 32256 clusters)</code>
</p>
            <p><code>Extent allocator size: 4194304 (1 groups)</code>
</p>
            <p><code>Journal size: 67108864</code>
</p>
            <p><code>Node slots: 2</code>
</p>
            <p><code>Creating bitmaps: done</code>
</p>
            <p><code>Initializing superblock: done</code>
</p>
            <p><code>Writing system files: done</code>
</p>
            <p><code>Writing superblock: done</code>
</p>
            <p><code>Writing backup superblock: 1 block(s)</code>
</p>
            <p><code>Formatting Journals: done</code>
</p>
            <p><code>Growing extent allocator: done</code>
</p>
            <p><code>Formatting slot map: done</code>
</p>
            <p><code>Formatting quota files: done</code>
</p>
            <p><code>Writing lost+found: done</code>
</p>
            <p><code>mkfs.ocfs2 successful</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

For more information about mkfs.ocfs2 options, refer to man page. Also see man tunefs.ocfs2.

### <span id="Mount"></span>Mount OCFS2 file system

1.  Run the `crm configure` command and type:  
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code><span>primitive ocfs2-1 ocf:heartbeat:Filesystem \</span></code>
</p>
            <p><code> </code>
</p>
            <p><code><span>params device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2" directory="/sanmount" \</span></code><code> </code><code><span>fstype="ocfs2" options="acl" \</span></code>
</p>
            <p><code> </code>
</p>
            <p><code><span>op monitor interval="20" timeout="40" \</span></code>
</p>
            <p><code> </code>
</p>
            <p><code><span>op start timeout="60" op stop timeout="60" \</span></code>
</p>
            <p><code> </code>
</p>
            <p><code><span>meta target-role="Started"</span></code>
</p>
         </td>
      </tr>
   </tbody>
</table>

      
    Where `/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2` is your OCFS2 partition and `/sanmount` is directory where it should be mounted

2.  Type `modgroup g-storage add ocfs2-1` to add ocfs2 primitive to g-storage group.

3.  Type `verify` to check your configuration.

4.  Type `commit` to save the changes.

5.  Type `show` to see the configuration.   
    

    <table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p><code>node115:~ # crm configure</code>
</p><code>crm(live/node115)configure# primitive ocfs2-1 ocf:heartbeat:Filesystem \</code><code>   &gt;   params device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2" directory="/sanmount" \</code>
            <p><code>   &gt;   fstype="ocfs2" options="acl" \</code>
</p>
            <p><code> </code>
</p>
            <p><code> </code>
</p>
            <p><code>   &gt;   op monitor interval="20" timeout="40" \</code>
</p>
            <p><code>   &gt;   op start timeout="60" op stop timeout="60" \</code>
</p>
            <p><code>   &gt;   meta target-role="Started"</code>
</p>
            <p><code>crm(live/node115)configure# modgroup g-storage add ocfs2-1</code>
</p>
            <p><code>crm(live/node115)configure# verify</code>
</p>
            <p><code>crm(live/node115)configure# commit</code>
</p>
            <p><code>crm(live/node115)configure# show</code>
</p>
            <p><code>node 176570483: node115</code>
</p>
            <p><code>primitive dlm ocf:pacemaker:controld \</code>
</p>
            <p><code>        op monitor interval=60 timeout=60</code><code>primitive ocfs2-1 Filesystem \</code>
</p>
            <p><code>        params device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part2" directory="/sanmount" fstype=ocfs2 options=acl \</code>
</p>
            <p><code>        op monitor interval=20 timeout=40 \</code>
</p>
            <p><code>        op start timeout=60 interval=0 \</code><code>        op stop timeout=60 interval=0 \</code>
</p>
            <p><code>        meta target-role=Started</code><code>primitive stonith-sbd stonith:external/sbd \</code>
</p>
            <p><code>        params pcmk_delay_max=30s \</code>
</p>
            <p><code>        params sbd_device="/dev/disk/by-id/dm-name-360014056e1d398a52894c8e99d7de877-part1"</code><code>group g-storage dlm ocfs2-1</code>
</p>
            <p><code>clone cl-storage g-storage \</code>
</p>
            <p><code>        meta interleave=true target-role=Started</code>
</p>
            <p><code>property cib-bootstrap-options: \</code>
</p>
            <p><code>        have-watchdog=true \</code>
</p>
            <p><code>        dc-version="1.1.23+20200622.28dd98fad-3.6.1-1.1.23+20200622.28dd98fad" \</code>
</p>
            <p><code>        cluster-infrastructure=corosync \</code>
</p>
            <p><code>        cluster-name=hacluster \</code>
</p>
            <p><code>        stonith-enabled=true \</code>
</p>
            <p><code>        stonith-watchdog-timeout=0 \</code>
</p>
            <p><code>        stonith-timeout=240s</code>
</p>
            <p><code>rsc_defaults rsc-options: \</code>
</p>
            <p><code>        resource-stickiness=1 \</code>
</p>
            <p><code>        migration-threshold=3</code>
</p>
            <p><code>op_defaults op-options: \</code>
</p>
            <p><code>        timeout=600 \</code>
</p>
            <p><code>        record-pending=true</code>
</p>
            <p><code>crm(live/node115)configure#</code>
</p>
         </td>
      </tr>
   </tbody>
</table>

6.  Type `quit` to exit the crm shell.

7.  Run `mount | grep ocfs2` to check whether the filesystem is mounted:
