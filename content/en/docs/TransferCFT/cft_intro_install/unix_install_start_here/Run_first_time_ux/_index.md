{
    "title": "Running Transfer CFT for the first time UNIX",
    "linkTitle": "Unix operations",
    "weight": "160"
}The elements and tasks required to
start <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> for the first time include:

-   [Set the environment](#Set)
-   [Start and stopping Transfer
    CFT](#Configuring_CFT_)
    -   [Start using a command](#Start)
    -   [Shut
        down using a command](#Shut)
    -   [Start or stop via a user interface](#Start2)

<span id="Set"></span>

## Set the environment

After installing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>
, but before starting <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> you should:

-   Execute the <span class="code">profile</span> in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> runtime directory to define environment
    variables. Run: <span class="code">‘. ./profile’</span>

-   Create a new set of Transfer
    CFT working files, parameters, partners, catalog, communication file, logs,
    use the sample configuration files cft-tcp.conf and cft-tcp-part.conf in the <span class="code">runtime/conf </span>directory. You can configure these during the product installation, or manually after installation.

-   Use <span class="code">cftinit &lt;configuration\_file></span> > and/or <span class="code">cftupdate</span> to interpret the parameter and
    partner files.  



        cftinit  conf/cft-tcp.conf
        cftupdate conf/cft-tcp-part.conf

      
    or  


        cftinit conf/cft-tcp.conf conf/cft-tcp-part.conf

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Caution  </strong></span>         </td>
         <td>These commands generate an initial configuration by <span class="bold_in_para">creating </span>the configuration files. Any previous configurations, and any data in the communication file, catalog, or log files will be <strong>lost</strong>.         </td>
      </tr>
   </tbody>
</table>

Sample file details

-   <span class="code">cft-tcp.conf</span>: Contains PARM object definitions (PARM, CAT, COM, LOG, ACCNT, PROT, SEND, RECV,...etc.)
-   <span class="code">cft-tcp-part.conf</span>: Contains partner definitions (CFTPART, CFTTCP, CFTSSL)

Delivered partners are:

-   PARIS - NEW YORK
-   LOOP
-   LOOPSSL0

## Start and stop commands

The following table lists the commands according to <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> version.

<table>
   <th>
      <tr>
<th>Version 2.7.1 and higher         </th>
<th>Version 2.7.0 and lower         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>cft start         </td>
         <td>cftstart         </td>
      </tr>
      <tr>
         <td>cft stop         </td>
         <td>cftstop         </td>
      </tr>
      <tr>
         <td>cft status         </td>
         <td>cftstatus         </td>
      </tr>
      <tr>
         <td>cft force-stop         </td>
         <td>cftstop -kill         </td>
      </tr>
      <tr>
         <td>cft force-stop –kill         </td>
         <td>cftstop -forcedkill         </td>
      </tr>
   </tbody>
</table>

<table>
   <tbody>
      <tr>
         <td>         </td>
         <td><span><strong>Note</strong></span>         </td>
         <td>The <span class="code">cftstart </span>and <span class="code">cftstop </span>commands, from version 2.7.0 and earlier, are redirected to the standardized commands for continued compatibility.         </td>
      </tr>
   </tbody>
</table>

<span id="Configuring_CFT_"></span>

### Start up

You can start Transfer CFT with the <span class="code">cft start </span>utility; see also Transfer CFT Management Utilities.

<span id="Shut"></span>

### Shut down

You can use one of the following methods to shut down Transfer CFT:

-   The <span class="code">CFTUTIL </span>utility
-   The <span class="code">cft </span> utility

For more information, see the administrative commands in [Manage the Transfer CFT server](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/administration/start_stop_cft.htm).

<span id="Start2"></span>

## Start or stop via a user interface

You can also use either [Central Governance](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CentralGov/operations/t_startCFT.htm) or the Transfer CFT to start or shut down <span class="mc-variable header_footer_variables.hf_long_product_name variable">Transfer CFT</span>.
