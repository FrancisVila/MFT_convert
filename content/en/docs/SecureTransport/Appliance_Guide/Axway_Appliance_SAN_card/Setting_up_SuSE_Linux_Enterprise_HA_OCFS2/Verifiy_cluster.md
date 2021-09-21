{
    "title": "Verify cluster configuration",
    "linkTitle": "Verify cluster configuration",
    "weight": "220"
}Run **crm configure show** to view the cluster resource configuration.

`#crm configure show`

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>primitive dlm ocf:pacemaker:controld \<br/>    op monitor interval="60" timeout="60"<br/>primitive o2cb ocf:ocfs2:o2cb \<br/>    op monitor interval="60" timeout="60"<br/>primitive ocfs2-1 ocf:heartbeat:Filesystem \<br/>    params device="/dev/disk/by-id/dm-name-&lt;per environment&gt;_part2" directory="/mnt/ocfs2" fstype="ocfs2" options="acl" \<br/>    op monitor interval="20" timeout="40"<br/>primitive stonith-sbd stonith:external/sbd \<br/>    params sbd_device="/dev/disk/by-id/dm-name-&lt;per environment&gt;_part1" \<br/>    meta target-role="Started" \<br/>    op monitor interval="20" timeout="20" start-delay="20"<br/>group base-group dlm o2cb ocfs2-1<br/>clone base-clone base-group \<br/>    meta interleave="true"<br/>property $id="cib-bootstrap-options" \<br/>    stonith-enabled="true" \<br/>    no-quorum-policy="ignore" \<br/>    placement-strategy="balanced" \<br/>    dc-version="1.1.9-2db99f1" \<br/>    cluster-infrastructure="classic openais (with plugin)" \<br/>    expected-quorum-votes="2"<br/>rsc_defaults $id="rsc-options" \<br/>    resource-stickiness="1" \<br/>    migration-threshold="3"<br/>op_defaults $id="op-options" \<br/>    timeout="600" \<br/>    record-pending="true"<br/></p>
         </td>
      </tr>
   </tbody>
</table>

For each node, there should be a `stonith external/sbd` resource created.

Also there is a HA Web Console for viewing the cluster status and configuration, running on port 7630 on each of the cluster nodes. Username: **hacluster** password: **linux**
