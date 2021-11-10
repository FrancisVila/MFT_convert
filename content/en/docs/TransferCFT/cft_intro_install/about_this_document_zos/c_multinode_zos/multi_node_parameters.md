{
    "title": "Configuration parameters",
    "linkTitle": "Multi-node configuration parameters",
    "weight": "240"
}This section presents the **multi-node** parameters and their default values. The column <span class="bold_in_para">Modify </span>indicates a strong recommendation that you should not modify this value if <span class="bold_in_para">No </span>is indicated.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameters</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Values</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Modify         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>cft.multi_node.enable</p>         </td>
         <td><p>Enables/disables the multi-node feature.</p>         </td>
         <td><p>No</p>         </td>
         <td><p>Yes, No</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.max</p>         </td>
         <td><p>Maximum number of nodes.</p>         </td>
         <td><p>8</p>         </td>
         <td><p>integer from 0 to 8</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
cftcomlock.fname</p>         </td>
         <td><p>Lock file for the main communication media file task in multi-node</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftcom.lck</p>         </td>
         <td><p>fname</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td>cft.multi_node.<br />
cftcom.dispatcher_policy         </td>
         <td><p>Specifies the dispatching policy.</p>
<p>- round_robin: Random dispatching across all nodes
occurs.</p>
<p>- node_affinity: Creates a one to one link between a partner and a node. Transfer requests for a given partner will always be performed by the same node.</p>         </td>
         <td>round_robin         </td>
         <td><p>round_robin,</p>
<p>node_affinity</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
sharedidt.fname</p>         </td>
         <td><p>Shared file for global IDT calculation in multi-node</p>         </td>
         <td><p>$(cft.runtime_dir)/data/cftsidt</p>         </td>
         <td><p>fname</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
sharedidt.enable</p>         </td>
         <td><p>Use global IDT calculation method</p>         </td>
         <td><p>No</p>         </td>
         <td><p>Yes, No</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
shared.filesystem.type</p>         </td>
         <td><p>Used to select appropriate consistency enforcement strategy.</p>
<p>If <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> is using NFSv4, you must enter the value <span class="code">nfs </span>in lower case.</p>         </td>
         <td><p>unknown</p>         </td>
         <td><p>unknown, posix, nfs, cifs</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
transfer_recovery_timeout</p>         </td>
         <td><p>Timeout in seconds for transfer recovery process (seconds)</p>         </td>
         <td><p>30</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
transfer_recovery_retry_delay</p>         </td>
         <td><p>Delay in seconds for transfer recovery retry (seconds)</p>         </td>
         <td><p>20</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
connection_retry_delay</p>         </td>
         <td><p>Delay in seconds for connection retry between nodes (seconds)</p>         </td>
         <td><p>10</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames</p>         </td>
         <td><p>List of hosts which handle the multi-node architecture</p>         </td>
         <td><p> </p>         </td>
         <td><p>list</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames.&lt;hostname&gt;.host</p>         </td>
         <td><p>Address (FQDN or IP address) of the host</p>         </td>
         <td><p> </p>         </td>
         <td><p>string</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.hostnames.<br />
&lt;hostname&gt;.pid</p>         </td>
         <td><p>Process ID of Copilot (copsmng) in multi-node</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames.&lt;hostname&gt;.state</p>         </td>
         <td><p>Copilot (copsmng) status in multi-node</p>         </td>
         <td><p>STOPPED</p>         </td>
         <td><p>INITIALIZING, STARTING, RUNNING, STOPPING, STOPPED, ERROR</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames.&lt;hostname&gt;.<br />
copui_pid</p>         </td>
         <td><p>Process ID of UI server (copui) in multi-node</p>         </td>
         <td><p> </p>         </td>
         <td><p> </p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames.&lt;hostname&gt;.<br />
copui_client_socket</p>         </td>
         <td><p>Windows socket passing for UI server (copui) in multi-node</p>         </td>
         <td><p> </p>         </td>
         <td><p>integer</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
hostnames.&lt;hostname&gt;.<br />
copui_notification_port</p>         </td>
         <td><p>Notification port for UI server (copui) in multi-node</p>         </td>
         <td><p> </p>         </td>
         <td><p>integer</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.nodes</p>         </td>
         <td><p>Number of nodes</p>         </td>
         <td><p>2</p>         </td>
         <td><p>integer from 2 to $(cft.multi_node.max)</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.nodestate</p>         </td>
         <td><p>Node status</p>         </td>
         <td><p>DISABLED</p>         </td>
         <td><p>DISABLED,</p>
<p>ENABLED_STOPPED,</p>
<p>ENABLED_STARTED</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.state</p>         </td>
         <td><p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> status</p>         </td>
         <td><p>STOPPED</p>         </td>
         <td><p>INITIALIZING,</p>
<p>STARTING, RUNNING, STOPPING, STOPPED,</p>
<p>ERROR</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.pid</p>         </td>
         <td><p>CFTMAIN process ID</p>         </td>
         <td><p> </p>         </td>
         <td><p>integer</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.hostname</p>         </td>
         <td><p>Hostname of the server where the node is running on</p>         </td>
         <td><p> </p>         </td>
         <td><p>string</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.host</p>         </td>
         <td><p>Host address of the server where the node is running on.</p>         </td>
         <td><p> </p>         </td>
         <td><p>string</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.prx_port</p>         </td>
         <td><p>Internal node listening port</p>         </td>
         <td><p> </p>         </td>
         <td><p>integer</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td><p>cft.multi_node.<br />
nodes.&lt;node_id&gt;.disabling</p>         </td>
         <td><p>Sets flag when disabling <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>.</p>         </td>
         <td><p>No</p>         </td>
         <td><p>Yes, No</p>         </td>
         <td>No         </td>
      </tr>
      <tr>
         <td>cft.multi_node.listen_port_range         </td>
         <td><p>Defines a port range to use for listening points dedicated to inter-node communication in multi-node, where the range is at least 4 x (number of nodes).</p>
<p>If you are using a firewall, you must use a port range that you can customize in your firewall to accept incoming connections.</p>         </td>
         <td><p>NA</p>
<p>(system value is used)</p>         </td>
         <td>          </td>
         <td>          </td>
      </tr>
   </tbody>
</table>

## Connection dispatcher parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameters</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Values</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Modify         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.enable</p>         </td>
         <td><p>Enable client registering connection dispatching</p>         </td>
         <td><p>Yes (multi-node), No otherwise</p>         </td>
         <td><p>Yes, No</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.control.port</p>         </td>
         <td><p>Connection dispatcher TCP control port</p>         </td>
         <td><p> </p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.retry_delay</p>         </td>
         <td><p>Client registering to connection dispatcher retry delay in seconds</p>         </td>
         <td><p>5</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.retry_timeout</p>         </td>
         <td><p>Client registering to connection dispatcher timeout in seconds</p>         </td>
         <td><p>300</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.unix.af_unix_fname</p>         </td>
         <td><p>Unix socket path name for connection dispatching</p>         </td>
         <td><p>$(cft.runtime_dir)/run/S_$<br />
(cft.short_hostname)DISPATCH</p>         </td>
         <td><p>fname</p>         </td>
         <td>Yes         </td>
      </tr>
      <tr>
         <td><p>copilot.<br />
connection_dispatcher.nt.local_port</p>         </td>
         <td><p>Local TCP port for connection dispatching</p>         </td>
         <td><p>1800</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
   </tbody>
</table>

### Node manager parameters

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Parameters</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Default</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1"><p>Values</p>         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Modify         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>copilot.<br />
node_manager.watchperiod</p>         </td>
         <td><p>Interval between checking the status of two Transfer CFT nodes. The Copilot watchdog uses the double of this value to ensure shared file system lease lock is not met. The value must therefore be less than the NFS lease time.</p>         </td>
         <td><p>10</p>         </td>
         <td><p>integer</p>         </td>
         <td>Yes         </td>
      </tr>
   </tbody>
</table>

Related topics

-   [Multi-node commands](../../../../about_multinode/multi_node_commands)
-   Managing multi-node
-   [UCONF: Protocols and networks](../../../../admin_intro/uconf/uconf_protocols_and_networks)
