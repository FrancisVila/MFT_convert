{
    "title": "Using a shared file system",
    "linkTitle": "Using a shared file system",
    "weight": "220"
}## Active/passive mode shared file systems

Active/passive mode requires a shared file system. Two typical shared file system implementations are NAS (network attached storage) and SAN (storage area network). This section describes GPFS, NFSv4, AWS EFS, and SMB/CIFS.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">In <span>Transfer CFT</span>, you can use any Portable Operating System Interface (POSIX) compliant shared file system for transferable application files.         </td>
      </tr>
</table>

## Using GPFS

GPFS, General Parallel File System, is the shared file system of choice for Transfer CFT. It provides high-speed file access for Transfer CFT.

## <span id="Using"></span>Using NFS

The recommendations in this section apply to a Transfer CFT an active/passive architecture based on an NFS shared file system. As NFSv3 cannot detect host failures, we recommend that you use NFSv4.

-   [Required NFS mount options](#required)
-   [Mount options summary](#mount) 
-   [Synchronous / asynchronous option impact](#impact)
-   [Tuning NFSv4 locking for node failover](#tuning)
-   [Troubleshoot an NFS lock daemon issue](#troubles)

### <span id="Required"></span>Required NFS mount options

#### Define the NFS version

If version 4 is not your NFS subsystem's default, you should specify version 4 when defining the mount options. Depending on your OS, use either the vers or nfsvers option.

#### Set the hard and nointr options

Mount NFS using the hard and nointr options. The intr mount option should not be available for NFSv4, but if you are in doubt, you should explicitly specify the nointr option.

#### Define file locking

Because Transfer CFT uses POSIX file locking services to synchronize shared files, make sure that the NFS clients report these locks to the NFS server. Depending on the NFS client, the corresponding option to tune may be called  local\_lock, llock, or nolock.

-   If local\_lock = all, the NFS client assumes locks are local, and allows Transfer CFT to simultaneously start on both the active and passive hosts. As a result, Transfer CFT does not function properly.
-   If `local_lock = none`, or if this option is not specified, the NFS client assumes that the locks are not local. This prevents Transfer CFT from starting on the second host when it is running on the first host.

Do not enable the local locking option.

#### Set the cto option

NFS implements a weak data consistency called "Close To Open consistency" or cto. This means that when a file is closed on a client, all modified data associated with the file is flushed from the server. If your NFS clients allow this behavior, be certain that the cto option is set.

#### <span id="Mount"></span>Mount options summary

The following table summarizes the recommended NFS mount options. Note that depending on the OS platform, only one of the three locking options should be available.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Recommended option</th>
         <th>Not recommended </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>vers=4 (or nfsvers=4)         </td>
         <td>not specified or value &lt;= 4         </td>
      </tr>
      <tr>
         <td>hard   (default)         </td>
         <td>"soft" specified         </td>
      </tr>
      <tr>
         <td>nointr (not the default)          </td>
         <td>
"intr" specified
         </td>
      </tr>
      <tr>
         <td>llock not specified          </td>
         <td>"llock" specified         </td>
      </tr>
      <tr>
         <td>lock   (default)          </td>
         <td>"nolock" specified         </td>
      </tr>
      <tr>
         <td>local_lock=none (default)         </td>
         <td>any other value specified         </td>
      </tr>
      <tr>
         <td>cto    (default)          </td>
         <td>"nocto" specified         </td>
      </tr>
   </tbody>
</table>

### Synchronous versus asynchronous option

To improve performance, NFS clients and NFS servers can delay file write operations in order to combine small file IOs into larger file IOs. You can enable this behavior on the NFS clients, NFS servers, or on both, using the async option. The sync option disables this behavior.

#### **Client**

On the client side, use the mount command to specify the async/sync option.

##### Async

The NFS client treats the sync mount option differently than some other file systems. If neither sync nor async is specified (or if async is specified), the NFS client delays sending application writes to the server until any of the following events occur:

-   Memory limitations force reclaiming of system memory resources.
-   Transfer CFT explicitly flushes file data (PeSIT synchronization points, for example).
-   Transfer CFT closes a file.

This means that under normal circumstances, data written by Transfer CFT may not immediately appear on the server that hosts the file.

##### Sync

If the sync option is specified on a mount point, any system call that writes data to files on that mount point causes that data to be flushed to the server before the system call returns control to Transfer CFT. This provides greater data cache coherence among clients, but at a significant cost to performance.

#### Server

On the server side, use the exports command to specify the async/sync option (NFS server export table).

##### Async

The async option allows the NFS server to violate the NFS protocol and reply to requests before any changes made by that request have been committed to stable storage (the disk drive, for example), even if the client is set to sync. This option usually improves performance, however data may be lost or corrupted in the case of an unclean server restart, such as an NFS server crash.

This possible data corruption is not detectable at the time of occurrence, because the async option instructs the server to lie to the client, telling the client that all data was written to stable storage (regardless of the protocol used).

##### Sync

Enables replies to requests only after the changes have been committed to stable storage.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">For more information on these options, refer to <i>NFS mount and export options </i>in the UNIX man pages (for example, <a href="http://man7.org/linux/man-pages/man5/nfs.5.html">here</a>).         </td>
      </tr>
</table>

#### <span id="Impact"></span>Synchronous / asynchronous option impact

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Client</th>
         <th> 	Server</th>
         <th>	Internal data</th>
         <th> 	Transferable data</th>
         <th>	Performance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Sync         </td>
         <td>	Sync         </td>
         <td>	1         </td>
         <td>	1         </td>
         <td>	Low         </td>
      </tr>
      <tr>
         <td>Sync         </td>
         <td>	Async         </td>
         <td>	2   (secure the NFS server)         </td>
         <td>	2  (secure the NFS server)         </td>
         <td>	Medium          </td>
      </tr>
      <tr>
         <td>Async         </td>
         <td>	Sync         </td>
         <td>	1   (if cft.server.catalog.<br/>sync.enable=Yes)         </td>
         <td>	1   (when using sync points)         </td>
         <td>	Medium - high         </td>
      </tr>
      <tr>
         <td>Async         </td>
         <td>	Async         </td>
         <td>	3         </td>
         <td>3         </td>
         <td>	High         </td>
      </tr>
   </tbody>
</table>

Legend:

-   1 = Secure
-   2 = Fairly secure
-   3 = Not secure
-   Internal data = Transfer CFT runtime files, such as the catalog
-   Transferable data = Files exchanged using Transfer CFT

### <span id="Tuning"></span>

### <span id="Troubles"></span>Troubleshoot an NFS lock daemon issue with no error message

When transferring files that are located in a **N**etwork **F**ile **S**ystem, an NFS locking issue (lockd) may occur if the correct port is not open on the firewall.

Symptom

-   Flow transfers hang in the phase T and phasestep C, with a timeout but no error message.

Remedy

-   Check that the correct port for the lockd service is open on the firewall (default=4045).

### Troubleshoot the UID and GID

NFS uses UIDs and GIDs for all file permissions. Therefore during installation of a multihost multi-node architecture, the Transfer CFT user must have read and write access to any folder and files created on the other host or hosts. Additionally, all hosts in the implementation should use the same UID number.

For more information, please refer to the [NFS](http://nfs.sourceforge.net/nfs-howto/ar01s07.html#pemission_issues) documentation.

## Using AWS EFS

The recommendations in this section apply to a Transfer CFT multi-node, multi-host architecture based on an Amazon Web Services (AWS) Elastic File System (EFS) shared file system.

When using AWS EFS, you cannot set the server options; only the client is configurable.

This system is based on NFSv4. For more information on NFSv4, please see [Using NFS](#using) .

This shared file system has features that impact performance, as compared to a traditional NFS:

-   Distributed systems replicating data  
-   Processing does not continue until all data is replicated

## Using SMB/CIFS

*Windows only*

SMB, Server Message Block, is a protocol used to share files across corporate intranets and the Internet, and is available as a shared file system when running Transfer CFT in a Windows environment.

It is recommended that you use SMB version 2 or higher with Transfer CFT.

CIFS, Common Internet File System, is an out-dated SMB protocol variant.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Samba suite usage is not recommended with Transfer CFT.         </td>
      </tr>
</table>