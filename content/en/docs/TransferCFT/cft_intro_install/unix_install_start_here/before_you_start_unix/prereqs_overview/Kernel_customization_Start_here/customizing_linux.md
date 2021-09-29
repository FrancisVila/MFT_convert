{
    "title": "Linux:\u00a0Customize the kernel",
    "linkTitle": "Linux:\u00a0Customize the kernel",
    "weight": "220"
}This section describes suggested kernel customizations to perform prior to an installation to better enable Transfer CFT operations.

## Kernel customization parameters

The following table lists IPC tuning parameters to consider customizing and recommended values.

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">To aid in correctly calculating semaphores, remember that each <span>Transfer CFT</span> has two semaphores per instance.</td>
</tr>
</tbody>
</table>

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th><p>Recommended</p>
<p>value</p></th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>msgmax</td>
<td>8192</td>
<td>Maximum size of a message in bytes.</td>
</tr>
<tr class="even">
<td>msgmnb</td>
<td>32768</td>
<td>Maximum size in bytes on a single IPC message queue.</td>
</tr>
<tr class="odd">
<td>msgmni</td>
<td><p>48 per <span>Transfer CFT</span> instance</p>
<p>See <a href="#note_linux">NOTE</a>**</p></td>
<td><p>Maximum number of IPC message queue resources allowed.</p>
<p>You require as many message queues as processes per Transfer CFT instance (when using multiple instances, multiply the number of instances by the number of Transfer CFT processes).</p></td>
</tr>
<tr class="even">
<td><p>shmall</p>
<p>(shmall*PAGE_SIZE)</p></td>
<td><p>2097152</p>
<p>(8 GB when page_size = 4096)</p></td>
<td><p>The total amount of shared memory available on the system is 2097152*4096 bytes (shmall*PAGE_SIZE) which is 8 GB.</p>
<p>This number may be affected by the use of a very large number of Transfer CFT instances.</p></td>
</tr>
<tr class="odd">
<td>shmmax</td>
<td><p>3554432: for fewer than 512 transfers in parallel</p>
<p>67108864: for more than 512 transfers in parallel</p></td>
<td>Maximum size in bytes for a shared memory segment.</td>
</tr>
<tr class="even">
<td>shmmni</td>
<td>4096</td>
<td><p>Number of shared memory segment identifiers in the system.</p>
<p>For each Transfer CFT instance you need 2 shared memory segments, so when using multiple instances or multi-node, multiply the number of instances by 2.</p></td>
</tr>
<tr class="odd">
<td>shmseg</td>
<td>10</td>
<td>Maximum number of shared memory segments per process.</td>
</tr>
<tr class="even">
<td>semmsl</td>
<td>250</td>
<td>Maximum number of IPC semaphores per set.</td>
</tr>
<tr class="odd">
<td>semmns</td>
<td>32000</td>
<td>Number of IPC system-wide semaphores.</td>
</tr>
<tr class="even">
<td>semopm</td>
<td>100</td>
<td>Maximum number of semaphore operations that can be performed per semop(2).</td>
</tr>
<tr class="odd">
<td>semmni</td>
<td>128</td>
<td><p>Maximum number of IPC system-wide semaphore sets.</p>
<p>For each Transfer CFT instance you need 2 semaphore sets, so when using multiple instances or multi-node, multiply the number of instances by 2.</p></td>
</tr>
</tbody>
</table>

<table data-cellpadding="0" data-cellspacing="0">
<tbody>
<tr class="odd">
<td data-valign="top"></td>
<td data-valign="top"><span><strong>Note</strong></span></td>
<td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top"><span id="note_linux"></span>**This value is based on the number of processes started by the Transfer CFT. This minimum is typically 7, but can be in excess of 40 depending on the values for maxtask, sslmtask, Sentinel if enabled, one task for each exit, etc.</td>
</tr>
</tbody>
</table>
