{
    "title": "Rollback upgrade and restore catalog",
    "linkTitle": "Rollback upgrade and restore catalog",
    "weight": "230"
}This section describes the procedure to revert to the previous version if, for whatever reason, you need to roll back an upgrade. However, if you executed transfers in the upgraded version that used parameters or metadata that are not available in the earlier version, this metadata is lost when you roll back.

## Roll back to a previous version

You can rollback an upgrade if needed the same as if you [Uninstall a service pack](../update). However, rolling back an upgrade takes Transfer CFT back to the previous version before the upgrade, so all transfers and configuration modifications that were performed since the upgrade are lost.

## Roll back and restore catalog

Under the described conditions, you can restore your current catalog as explained below.

### Prerequisites

To perform a version downgrade, you must have already upgraded from Transfer CFT 3.4 or higher to Transfer CFT 3.6.

### Procedure

1.  Enter the following command to export the Transfer CFT catalog file, perfoming the command from the &lt;installation directory>:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI migr type=cat,direct=fromcat,ifname=$CFTCATA,ofname=cftcat_36</td>
    </tr>
    </tbody>
    </table>
2.  Uninstall the Transfer CFT 3.6. Please see [Uninstall](../uninstall) Transfer CFT for details.
3.  Create a Transfer CFT catalog file. See [Manually create internal data files](../../../admin_intro/admin_commands_intro/cftfile) for details. For example:  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTUTIL cftfile type=cat,mode=replace,fname=$CFTCATA,recnb=5000</td>
    </tr>
    </tbody>
    </table>
4.  Import the saved `cftcat_36 `to the catalog file &lt;logical\_filename> you created in the previous step.  
    <table data-cellspacing="0">
    <tbody>
    <tr class="odd">
    <td>CFTMI migr type=cat,direct=tocat,ifname=cftcat_36,ofname=$CFTCATA</td>
    </tr>
    </tbody>
    </table>
5.  Start Transfer CFT to verify the procedure.
