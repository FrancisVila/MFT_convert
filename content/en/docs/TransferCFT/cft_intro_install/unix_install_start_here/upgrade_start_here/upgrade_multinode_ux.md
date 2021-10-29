{
    "title": "Upgrade a Transfer CFT multi-node installation",
    "linkTitle": "Upgrade a multi-node installation",
    "weight": "180"
}This section describes how to upgrade from a Transfer CFT 3.1.3, 3.2.x, 3.3.2, or 3.4 multi-node, multihost installation to Transfer CFT 3.9.

As of Transfer CFT 3.4 there is no separate upgrade package, you use the installation package to perform an upgrade procedure as described in the sections below.

## <span id="Before"></span>Before you start

Before beginning the upgrade procedure, download the Transfer CFT installation kit available at [support.axway.com](https://support.axway.com/).

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">Remember that <span>Transfer CFT</span> clusters must be fully stopped while performing an upgrade.         </td>
      </tr>
   </tbody>
</table>

## Limitation

During an upgrade, if the CFTCOM file path is greater than 64 characters the COM file is not migrated, and you must migrate it manually.

## Procedure

For details on shared disks, node commands, and other multi-node considerations, see *[Manage multi-node architecture](../../../about_multinode)*.

### Upgrade all hosts

1.  Stop Copilot. This command stops Copilot as well all cftnodes running on that machine.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>copstop -f</p>         </td>
          </tr>
       </tbody>
    </table>

2.  Connect to the first machine and execute the following command:

3.  <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>./Transfer_CFT_<span>3.9</span>_Install_&lt;OS&gt;_&lt;BN&gt;.run --architecture first_host --installdir &lt;installdir&gt;</p>         </td>
          </tr>
       </tbody>
    </table>

     

4.  For each additional host, connect to the machine and execute the following command:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>./Transfer_CFT_<span>3.9</span>_Install_&lt;OS&gt;_&lt;BN&gt;.run --architecture additional_host --runtimedir &lt;runtimedir&gt;</p>         </td>
          </tr>
       </tbody>
    </table>

-   Use the two following parameters, depending on if this is the first host or an additional host:
    -   architecture and installdir (first\_host), *or*
    -   architecture and runtimedir (additional\_host)
-   Where:
    -   --architecture &lt;architecture>: Installation architecture (first\_host or additional\_host).
    -   --installdir &lt;installdir>: For a legacy upgrade, this is the directory where the Axway Installer was installed. When this parameter is assigned, it overwrites any reference in the configuration file (first\_host).
    -   --runtimedir &lt;runtimedir>: For a legacy upgrade, this is the shared data directory where the Axway Installer was installed. When this parameter is assigned, it overwrites any reference in the configuration file (additional\_host).

### Restart the upgraded Transfer CFT multihost multi-node environment

1.  Launch the Transfer CFT profile from the Transfer CFT runtime directory on the shared disk of each machine.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>cd /&lt;shared_disk&gt;/&lt;CFTdir&gt;/Transfer_CFT/runtime<br />
    . ./profile         </td>
          </tr>
       </tbody>
    </table>
2.  Check the new version using the following command:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTUTIL ABOUT</p>         </td>
          </tr>
       </tbody>
    </table>
3.  Start Copilot (start each of the Copilots in the multi-node environment).  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>copstart</p>         </td>
          </tr>
       </tbody>
    </table>
4.  After restarting the Copilots, restart the Transfer CFT server:  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>cft restart</p>         </td>
          </tr>
       </tbody>
    </table>
5.  Check the upgraded Transfer CFT multi-node multihost system.  
    <table data-cellspacing="0">
       <tbody>
          <tr class="odd">
             <td>            <p>CFTUTIL listnode</p>         </td>
          </tr>
       </tbody>
    </table>

    -   All of the Copilots should be started

    <!-- -->

    -   All of the Transfer CFT nodes must be started

Your Transfer CFT 3.9 exec scripts are now operational. However, you must rebuild your APIs and Exits. Once Transfer CFT has been upgraded on a host you can start that instance, there is no need to wait until Transfer CFT is upgraded on every host.

## Managing multi-node

For details on shared disks, node commands, and other multi-node considerations, refer to the *Transfer CFT 3.9 User Guide &gt; *Manage multi-node architecture**.

## Post upgrade

After completing the upgrade procedure, your Transfer CFT 3.9, exec scripts are operational. However, you must rebuild your programs that use APIs and exits.

After performing an upgrade, all passwords are cyphered using a hard-coded key. We recommend that you generate an encryption key as described in [Generate an encryption](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/Security/cipher_key.htm).

## Check the new version

To check the Transfer CFT version, as well as the license key and system information, enter the command:

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p><span>CFTUTIL ABOUT</span></p>         </td>
      </tr>
   </tbody>
</table>

## Uninstall an upgrade pack

The procedure is the same as when you uninstall a Service Pack. See [Uninstall Transfer CFT](../uninstall_transfercft_ux).
