{
    "title": "Customize the VIPA and execute commands",
    "linkTitle": "Customize the VIPA and execute commands",
    "weight": "190"
}This sections describes how to customize the LPAR (hosts) for your multi-node setup. It is based on an example implementation of an Active/Active High Availability multi-host configuration use case. For a mono host, multi-node installation, you only customize one LPAR (host).

After you complete the customization and configuration checks, execute the program commands.

## Procedure overview

To customize the hosts in your setup and submit the customization, perform the tasks listed in the table.

"How to" instructions for configuring LPAR options and submitting the VARY OBEYFILE commands are provided in the sections following this table.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Step</th>
         <th>Task</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1         </td>
         <td>If you have not done so, customize <a href="../t__mninit_multinode_zos">MNINIT</a>.          </td>
      </tr>
      <tr>
         <td>2         </td>
         <td>
            <p>Customize the UPARM(TC*) members. </p>
            <p>The example (below) demonstrates how to customize LPAR1 and LPAR2. If you have additional machines in your configuration, repeat this step for each host machine. For a single host installation, you only customize UPARM(TCPSHAP1).</p>
         </td>
      </tr>
      <tr>
         <td>3         </td>
         <td>
            <p>Perform a Transfer CFT configuration check:</p>
            <ul>
               <li>Verify that the CFTNET object host parameter corresponds with what you defined for the VIPA.                </li>
               <li>Verify that  the CFTNET command SRCPORT parameter is set to 1.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>4         </td>
         <td>Submit the MNINIT. The Transfer CFT is now configured for multi-node.         </td>
      </tr>
      <tr>
         <td>          </td>
         <td>Steps 5 and 6, which use the VARY OBEYFILE commands, require administrator rights.         </td>
      </tr>
      <tr>
         <td>5         </td>
         <td>Execute the VARY OBEYFILE command  for each UPARM(TC*) member.         </td>
      </tr>
      <tr>
         <td>6         </td>
         <td>For a z/OS restart, the administrator must do all of the VIPA OBEYFILE commands performed in Step 5  on the z/OS machine.          </td>
      </tr>
   </tbody>
</table>

## Customize the UPARM(TC\*) members

The UPARM(TC\*) members customization example is based on a setup two hosts, LPAR1 and LPAR2. For a mono host, multi-node installation, you only need to customize the UPARM(TCPSHAP1).

For each host in your multi-node configuration, perform the following customization and execute. You can execute after each option, or after customizing all options.

### Customize the LPAR1

Define the shareport method.

..UPARM(TCPSHAP1) SHAREPORT / SHAREPORTWLM

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=... UPARM(TCPSHAP1)</p>
         </td>
      </tr>
   </tbody>
</table>

Customize the dynamic XCF address (automatic function to declare LPAR).

..UPARM(TCPDYMX1) DYNAMICXCF

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCPDYMX1)</p>
         </td>
      </tr>
   </tbody>
</table>

### Customize the LPAR2

Define the shareport method.

..UPARM(TCPSHAP1) SHAREPORT / SHAREPORTWLM

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...V30X.UPARM(TCPSHAP1)         </td>
      </tr>
   </tbody>
</table>

Customize the dynamic XCF address (automatic function to declare LPAR).

..UPARM(TCPDYMX2) DYNAMICXCF (one for each host)

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...V30X.UPARM(TCPDYMX2)         </td>
      </tr>
   </tbody>
</table>

## Customize the cluster

Define the cluster address after configuring the DYNAMICXCF on all hosts (that is, the customization of LPAR1 and LPAR2 in the previous section). This host address is the unique host address as seen externally, and should correspond with the one declared in the local CFTNET.

Remember that the VIPA commands must be executed by someone with administrator rights.

Customize the cluster as follows:

..UPARM(TCVIPDEF) VIPADEFINE (global for all hosts VIPADEFINE mask @DVIPA)

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPDEF)</p>
         </td>
      </tr>
   </tbody>
</table>

This means that in the example configuration, the cluster will work with the machines (LPAR1, LPAR2,...) using this one single dynamic address.

### About Copilot

For each listening port configuration (for the SYSPLEX distributor incoming calls), you can have one dvipa address for Copilot, where there is one Copilot for each host.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">There is no PORT statement for Copilot. An external Copilot passes via the SYSPLEX distributor directly to the host Copilot. There is one Copilot per host, regardless of the number of Transfer CFT nodes on the host.         </td>
      </tr>
</table>

Two command samples contain the VIPAdistribute Statement, which concerns the SYSPLEX distributor. There is also a command also for Copilot.

### About REST API

When using REST API (copilot.restapi.enable=yes) in a multi-node environment, you must also define the copilot.restapi.serverport value in the VIPA configuration. See, for example, the delivered UPARM(TCVIPRN5) and UPARM(TCVIPWG5) files.

## Define a distribution method

The following examples, WeightedActive and RounRobin, represent two of the possible load distribution methods that you can use in VIPA. Select a load distribution method, and execute the corresponding VARY OBEYFILE  command once you have finished customizing this option.

**Weighted active example**

\- DISTMethod WEIGHTEDActive

..UPARM(TCVIPWG0) Port pesit

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPWG0)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG1) Port pesit ssl

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPWG1)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG2) Port Copilot

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPWG2)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG3) Port Synchronous Communication

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPWG3)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG4) Port Copilot SSL

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPWG4)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG5) Port Copilot REST API server port

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPWG5)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPWG6) Port SFTP

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPWG6)         </td>
      </tr>
   </tbody>
</table>

**Round robin example**

\- DISTMethod ROUNDROBIN

..UPARM(TCVIPRN0) Port pesit

Example VIPA command to execute:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPRN0)         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN1) Port pesit ssl

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPRN1)         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN2) Port Copilot

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPRN2)         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN3) Port Synchronous Communication

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPRN3)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN4) Port Copilot SSL

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPRN4)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN5) Port Copilot REST API server port

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>v tcpip,tcpip,obeyfile,dsn=….UPARM(TCVIPRN5)</p>
         </td>
      </tr>
   </tbody>
</table>

..UPARM(TCVIPRN6) Port SFTP

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>v tcpip,tcpip,obeyfile,dsn=...UPARM(TCVIPRN6)         </td>
      </tr>
   </tbody>
</table>

You have now customized the VIPA and submitted the programs.

 
