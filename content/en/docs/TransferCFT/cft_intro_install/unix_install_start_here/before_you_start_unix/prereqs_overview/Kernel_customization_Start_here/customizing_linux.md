{
    "title": "Linux: Customize the kernel",
    "linkTitle": "Linux: Customize the kernel",
    "weight": "210"
}This section describes suggested kernel customizations to perform prior to an installation to better enable Transfer CFT operations.

## Kernel customization parameters

The following table lists IPC tuning parameters to consider customizing and recommended values.

> **Note:**
>
> To aid in correctly calculating semaphores, remember that each Transfer CFT has two semaphores per instance.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Recommended</p>
<p>value</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>msgmax         </td>
         <td>8192         </td>
         <td>Maximum size of a message in bytes.         </td>
      </tr>
      <tr>
         <td>msgmnb         </td>
         <td>32768         </td>
         <td>Maximum size in bytes on a single IPC message queue.         </td>
      </tr>
      <tr>
         <td>msgmni         </td>
         <td><p>48 per <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> instance</p>
<p>See <a href="#note_linux">NOTE</a>**</p>         </td>
         <td><p>Maximum number of IPC message queue resources allowed.</p>
<p>You require as many message queues as processes per Transfer CFT instance (when using multiple instances, multiply the number of instances by the number of Transfer CFT processes).</p>         </td>
      </tr>
      <tr>
         <td><p>shmall</p>
<p>(shmall*PAGE_SIZE)</p>         </td>
         <td><p>2097152</p>
<p>(8 GB when page_size = 4096)</p>         </td>
         <td><p>The total amount of shared memory available on the system is 2097152*4096 bytes (shmall*PAGE_SIZE) which is 8 GB.</p>
<p>This number may be affected by the use of a very large number of Transfer CFT instances.</p>         </td>
      </tr>
      <tr>
         <td>shmmax         </td>
         <td><p>3554432: for fewer than 512 transfers in parallel</p>
<p>67108864: for more than 512 transfers in parallel</p>         </td>
         <td>Maximum size in bytes for a shared memory segment.         </td>
      </tr>
      <tr>
         <td>shmmni         </td>
         <td>4096         </td>
         <td><p>Number of shared memory segment identifiers in the system.</p>
<p>For each Transfer CFT instance you need 2 shared memory segments, so when using multiple instances or multi-node, multiply the number of instances by 2.</p>         </td>
      </tr>
      <tr>
         <td>shmseg         </td>
         <td>10         </td>
         <td>Maximum number of shared memory segments per process.         </td>
      </tr>
      <tr>
         <td>semmsl         </td>
         <td>250         </td>
         <td>Maximum number of IPC semaphores per set.         </td>
      </tr>
      <tr>
         <td>semmns         </td>
         <td>32000         </td>
         <td>Number of IPC system-wide semaphores.         </td>
      </tr>
      <tr>
         <td>semopm         </td>
         <td>100         </td>
         <td>Maximum number of semaphore operations that can be performed per semop(2).         </td>
      </tr>
      <tr>
         <td>semmni         </td>
         <td>128         </td>
         <td><p>Maximum number of IPC system-wide semaphore sets.</p>
<p>For each Transfer CFT instance you need 2 semaphore sets, so when using multiple instances or multi-node, multiply the number of instances by 2.</p>         </td>
      </tr>
   </tbody>
</table>

> **Note:**
>
> \*\*This value is based on the number of processes started by the Transfer CFT. This minimum is typically 7, but can be in excess of 40 depending on the values for maxtask, sslmtask, Sentinel if enabled, one task for each exit, etc.
