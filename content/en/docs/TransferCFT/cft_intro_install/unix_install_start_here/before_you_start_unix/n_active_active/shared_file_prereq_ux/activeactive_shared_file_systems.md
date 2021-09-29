{
    "title": "Using a shared file system",
    "linkTitle": "Using a shared file system",
    "weight": "210"
}## <span id="Active_active_mode_shared_file_systems_..4"></span><span id="Active_active_mode_shared_file_systems"></span>Active/active mode shared file systems

In a multi-node context, a shared file system allows multiple applications to access the same files at the same time. Two typical shared file system implementations are NAS (network attached storage) and SAN (storage area network). This section describes GPFS, NFSv4, AWS EFS, and SMB/CIFS as they pertain to Transfer CFT multi-node installations.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">In <span>Transfer CFT</span>, you can use any Portable Operating System Interface (POSIX) compliant shared file system for transferable application files.</td>
</tr>
</tbody>
</table>

## <span id="Using_GPFS_..5"></span><span id="Using_GPFS"></span>Using GPFS

GPFS, General Parallel File System, is the shared file system of choice for Transfer CFT. It provides high-speed file access for Transfer CFT when executing in a multi-node architecture.

### <span id="Use_the_default_setting_for_GPFS_usage_..6"></span><span id="Use_the_default_setting_for_GPFS_usage"></span>Use the default setting for GPFS usage

By default, the shared file system is set to unknown, the value to use for GPFS. If you are uncertain as to the file system setting for the Transfer CFT internal data files, execute the following command to return to the default setting:  
`CFTUTIL uconfunset id=cft.multi_node.shared.filesystem.type`

## <span id="Using_NFSv4_..7"></span><span id="Using_NFSv4"></span><span id="Using"></span>Using NFSv4

The recommendations in this section apply to a Transfer CFT multi-node, multi-host architecture based on an NFSv4 shared file system. To implement a Transfer CFT active/active architecture using NFS, version 4 is mandatory. This is because NFSv4 can detect host failures (unlike NFSv3). With host failure detections possible, Transfer CFT can restart another host's nodes when necessary.

To implement active/active Transfer CFT you must use NFSv4 for the Transfer CFT runtime directory, which contains internal data such as the catalog, log, communication file, etc. Other versions of NFS are not supported for the runtime directory. For file exchanges, you can use either NFSv4 or v3. NFSv3 is not described in this document.

-   [Required NFSv4 mount options](#required)
-   [Mount options summary](#mount) 
-   [Synchronous / asynchronous option impact](#impact)
-   [Tuning NFSv4 locking for node failover](#tuning)
-   [Perform a NAS failover](#perform)
-   [Troubleshoot an NFS lock daemon issue](#troubles)

### <span id="Define_NFS_as_the_shared_file_system_..8"></span><span id="Define_NFS_as_the_shared_file_system"></span>Define NFS as the shared file system

Execute the following command to enable the Transfer CFT internal data files to reside on a NFSv4 file system.  
Enter the nfs value in lower case:  

`CFTUTIL uconfset id=cft.multi_node.shared.filesystem.type, value=nfs`

### <span id="Required_NFSv4_mount_options_..9"></span><span id="Required_NFSv4_mount_options"></span><span id="Required"></span>Required NFSv4 mount options

#### <span id="Define_the_NFS_version_..10"></span><span id="Define_the_NFS_version"></span>Define the NFS version

If version 4 is not your NFS subsystem's default, you must specify version 4 when defining the mount options. Depending on your OS, use either the vers or nfsvers option.

#### <span id="Set_the_hard_and_nointr_options_..11"></span><span id="Set_the_hard_and_nointr_options"></span>Set the hard and nointr options

Mount NFSv4 using the hard and nointr options. The intr mount option should not be available for NFSv4, but if you are in doubt, you should explicitly specify the nointr option.

#### <span id="Define_file_locking_..12"></span><span id="Define_file_locking"></span>Define file locking

Because Transfer CFT uses POSIX file locking services to synchronize shared files, make sure that the NFS clients report these locks to the NFS server. Depending on the NFS client, the corresponding option to tune may be called  local\_lock, llock, or nolock. Do not enable the local locking option.

#### <span id="Set_the_cto_option_..13"></span><span id="Set_the_cto_option"></span>Set the cto option

NFS implements a weak data consistency called "Close To Open consistency" or cto. This means that when a file is closed on a client, all modified data associated with the file is flushed from the server. If your NFS clients allow this behavior, be certain that the cto option is set.

#### <span id="Mount_options_summary_..14"></span><span id="Mount_options_summary"></span><span id="Mount"></span>Mount options summary

The following table summarizes the recommended NFSv4 mount options. Note that depending on the OS platform, only one of the three locking options should be available.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Correct option</th>
<th>Incorrect option</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>vers=4 (or nfsvers=4)</td>
<td>not specified or value &lt;= 4</td>
</tr>
<tr class="even">
<td>hard (default)</td>
<td>"soft" specified</td>
</tr>
<tr class="odd">
<td>nointr (not the default)</td>
<td>"intr" specified</td>
</tr>
<tr class="even">
<td>llock not specified</td>
<td>"llock" specified</td>
</tr>
<tr class="odd">
<td>lock (default)</td>
<td>"nolock" specified</td>
</tr>
<tr class="even">
<td>local_lock=none (default)</td>
<td>any other value specified</td>
</tr>
<tr class="odd">
<td>cto (default)</td>
<td>"nocto" specified</td>
</tr>
</tbody>
</table>

### <span id="Synchronous_versus_asynchronous_option_..15"></span><span id="Synchronous_versus_asynchronous_option"></span>Synchronous versus asynchronous option

To improve performance, NFS clients and NFS servers can delay file write operations in order to combine small file IOs into larger file IOs. You can enable this behavior on the NFS clients, NFS servers, or on both, using the async option. The sync option disables this behavior.

#### <span id="Client_..16"></span><span id="Client"></span>**Client**

On the client side, use the mount command to specify the async/sync option.

##### <span id="Async_..17"></span><span id="Async"></span>Async

The NFS client treats the sync mount option differently than some other file systems. If neither sync nor async is specified (or if async is specified), the NFS client delays sending application writes to the server until any of the following events occur:

-   Memory limitations force reclaiming of system memory resources.
-   Transfer CFT explicitly flushes file data (PeSIT synchronization points, for example).
-   Transfer CFT closes a file.

This means that under normal circumstances, data written by Transfer CFT may not immediately appear on the server that hosts the file.

##### <span id="Sync_..18"></span><span id="Sync"></span>Sync

If the sync option is specified on a mount point, any system call that writes data to files on that mount point causes that data to be flushed to the server before the system call returns control to Transfer CFT. This provides greater data cache coherence among clients, but at a significant cost to performance.

#### <span id="Server_..19"></span><span id="Server"></span>Server

On the server side, use the exports command to specify the async/sync option (NFS server export table).

##### <span id="Async_..20"></span><span id="Async_..1"></span>Async

The async option allows the NFS server to violate the NFS protocol and reply to requests before any changes made by that request have been committed to stable storage (the disk drive, for example), even if the client is set to sync. This option usually improves performance, however data may be lost or corrupted in the case of an unclean server restart, such as an NFS server crash.

This possible data corruption is not detectable at the time of occurrence, because the async option instructs the server to lie to the client, telling the client that all data was written to stable storage (regardless of the protocol used).

##### <span id="Sync_..21"></span><span id="Sync_..2"></span>Sync

Enables replies to requests only after the changes have been committed to stable storage.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">For more information on these options, refer to <em>NFS mount and export options</em> in the UNIX man pages (for example, <a href="http://man7.org/linux/man-pages/man5/nfs.5.html">here</a>).</td>
</tr>
</tbody>
</table>

#### <span id="Synchronous___asynchronous_option_impact_..22"></span><span id="Synchronous___asynchronous_option_impact"></span><span id="Impact"></span>Synchronous / asynchronous option impact

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Client</th>
<th>Server</th>
<th>Internal data</th>
<th>Transferable data</th>
<th>Performance</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sync</td>
<td>Sync</td>
<td>1</td>
<td>1</td>
<td>Low</td>
</tr>
<tr class="even">
<td>Sync</td>
<td>Async</td>
<td>2 (secure the NFS server)</td>
<td>2 (secure the NFS server)</td>
<td>Medium</td>
</tr>
<tr class="odd">
<td>Async</td>
<td>Sync</td>
<td>1 (if cft.server.catalog.<br />
sync.enable=Yes)</td>
<td>1 (when using sync points)</td>
<td>Medium - high</td>
</tr>
<tr class="even">
<td>Async</td>
<td>Async</td>
<td>3</td>
<td>3</td>
<td>High</td>
</tr>
</tbody>
</table>

Legend:

-   1 = Secure
-   2 = Fairly secure
-   3 = Not secure
-   Internal data = Transfer CFT runtime files, such as the catalog
-   Transferable data = Files exchanged using Transfer CFT

### <span id="Tuning_NFSv4_locking_for_node_failover_..23"></span><span id="Tuning_NFSv4_locking_for_node_failover"></span><span id="Tuning"></span>Tuning NFSv4 locking for node failover

The NFSv4 locking lease period affects the Transfer CFT delay required to detect node failovers. The default value for this parameter is typically 90 seconds. On systems where this parameter is tunable, configuring a shorter value can significantly reduce Transfer CFT node failovers.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">You should configure the lease time together with the UCONF <span>copilot.node_manager.watchperiod</span> parameter, noting the restriction that NFS lease time &gt; 2 * <span>copilot.node_manager.watchperiod</span>.</td>
</tr>
</tbody>
</table>

### <span id="Perform_a_NAS failover_..24"></span><span id="Perform_a_NAS failover"></span><span id="Perform"></span>Perform a NAS failover

When using NAS failover in a multihost-multinode architecture, you must stop the cluster prior to performing the failover. For information on starting and stopping a cluster, see [Multi-node commands and management](../../../../../../about_multinode/multi_node_commands)

1.  Stop the Transfer CFT cluster.
2.  Perform the failover.
3.  Start the Transfer CFT cluster.

### <span id="Troubleshoot_an_NFS_lock_daemon_issue_with_no_error_message_..25"></span><span id="Troubleshoot_an_NFS_lock_daemon_issue_with_no_error_message"></span><span id="Troubles"></span>Troubleshoot an NFS lock daemon issue with no error message

When transferring files that are located in a **N**etwork **F**ile **S**ystem, an NFS locking issue (lockd) may occur if the correct port is not open on the firewall.

Symptom

-   Flow transfers hang in the phase T and phasestep C, with a timeout but no error message.

Remedy

-   Check that the correct port for the lockd service is open on the firewall (default=4045).

### <span id="Troubleshoot_the_UID_and_GID_..26"></span><span id="Troubleshoot_the_UID_and_GID"></span>Troubleshoot the UID and GID

NFS uses UIDs and GIDs for all file permissions. Therefore during installation of a multihost multi-node architecture, the Transfer CFT user must have read and write access to any folder and files created on the other host or hosts. Additionally, all hosts in the implementation should use the same UID number.

For more information, please refer to the [NFS](http://nfs.sourceforge.net/nfs-howto/ar01s07.html#pemission_issues) documentation.

## <span id="Using_AWS EFS_..27"></span><span id="Using_AWS EFS"></span>Using AWS EFS

The recommendations in this section apply to a Transfer CFT multi-node, multi-host architecture based on an Amazon Web Services (AWS) Elastic File System (EFS) shared file system.

When using AWS EFS, you cannot set the server options; only the client is configurable.

This system is based on NFSv4. For more information on NFSv4, please see [Using NFSv4](#using) .

This shared file system has features that impact performance, as compared to a traditional NFS:

-   Distributed systems replicating data  
-   Processing does not continue until all data is replicated

## <span id="Using_SMB_CIFS_..28"></span><span id="Using_SMB_CIFS"></span>Using SMB/CIFS

*Windows only*

SMB, Server Message Block, is a protocol used to share files across corporate intranets and the Internet, and is available as a shared file system when running Transfer CFT in a Windows environment.

It is recommended that you use SMB version 2 or higher with Transfer CFT.

CIFS, Common Internet File System, is an out-dated SMB protocol variant.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Samba suite usage is not recommended with Transfer CFT.</td>
</tr>
</tbody>
</table>
