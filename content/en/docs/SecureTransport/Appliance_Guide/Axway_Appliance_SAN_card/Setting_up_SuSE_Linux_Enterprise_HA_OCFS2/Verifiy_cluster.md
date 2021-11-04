{
    "title": "Verify cluster configuration",
    "linkTitle": "Verify cluster configuration",
    "weight": "220"
}Run **crm configure show** to view the cluster resource configuration.

`#crm configure show`



    primitive dlm ocf:pacemaker:controld \
        op monitor interval="60" timeout="60"
    primitive o2cb ocf:ocfs2:o2cb \
        op monitor interval="60" timeout="60"
    primitive ocfs2-1 ocf:heartbeat:Filesystem \
        params device="/dev/disk/by-id/dm-name-<per environment>_part2" directory="/mnt/ocfs2" fstype="ocfs2" options="acl" \
        op monitor interval="20" timeout="40"
    primitive stonith-sbd stonith:external/sbd \
        params sbd_device="/dev/disk/by-id/dm-name-<per environment>_part1" \
        meta target-role="Started" \
        op monitor interval="20" timeout="20" start-delay="20"
    group base-group dlm o2cb ocfs2-1
    clone base-clone base-group \
        meta interleave="true"
    property $id="cib-bootstrap-options" \
        stonith-enabled="true" \
        no-quorum-policy="ignore" \
        placement-strategy="balanced" \
        dc-version="1.1.9-2db99f1" \
        cluster-infrastructure="classic openais (with plugin)" \
        expected-quorum-votes="2"
    rsc_defaults $id="rsc-options" \
        resource-stickiness="1" \
        migration-threshold="3"
    op_defaults $id="op-options" \
        timeout="600" \
        record-pending="true"

For each node, there should be a `stonith external/sbd` resource created.

Also there is a HA Web Console for viewing the cluster status and configuration, running on port 7630 on each of the cluster nodes. Username: **hacluster** password: **linux**
