{
    "title": "Running Transfer CFT for the first time UNIX",
    "linkTitle": "Unix operations",
    "weight": "160"
}The elements and tasks required to
start {{< TransferCFT/componentshortname  >}} for the first time include:

-   [Set the environment](#Set)
-   [Start and stopping Transfer
    CFT](#Configuring_CFT_)
    -   [Start using a command](#Start)
    -   [Shut
        down using a command](#Shut)
    -   [Start or stop via a user interface](#Start2)

<span id="Set"></span>

## Set the environment

After installing {{< TransferCFT/componentshortname  >}}
, but before starting {{< TransferCFT/componentshortname  >}} you should:

-   Execute the `profile` in the {{< TransferCFT/componentshortname >}} runtime directory to define environment
    variables. Run: `‘. ./profile’`

-   Create a new set of Transfer
    CFT working files, parameters, partners, catalog, communication file, logs,
    use the sample configuration files cft-tcp.conf and cft-tcp-part.conf in the `runtime/conf `directory. You can configure these during the product installation, or manually after installation.

-   Use `cftinit <configuration_file>` > and/or `cftupdate` to interpret the parameter and
    partner files.  



        cftinit  conf/cft-tcp.conf
        cftupdate conf/cft-tcp-part.conf

      
    or  


        cftinit conf/cft-tcp.conf conf/cft-tcp-part.conf

> **Note:**
>
> Caution  
> These commands generate an initial configuration by creating the configuration files. Any previous configurations, and any data in the communication file, catalog, or log files will be lost.

Sample file details

-   `cft-tcp.conf`: Contains PARM object definitions (PARM, CAT, COM, LOG, ACCNT, PROT, SEND, RECV,...etc.)
-   `cft-tcp-part.conf`: Contains partner definitions (CFTPART, CFTTCP, CFTSSL)

Delivered partners are:

-   PARIS - NEW YORK
-   LOOP
-   LOOPSSL0

## Start and stop commands

The following table lists the commands according to {{< TransferCFT/componentlongname  >}} version.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Version 2.7.1 and higher         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Version 2.7.0 and lower         </th>
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

> **Note:**
>
> The cftstart and cftstop commands, from version 2.7.0 and earlier, are redirected to the standardized commands for continued compatibility.

<span id="Configuring_CFT_"></span>

### Start up

You can start Transfer CFT with the `cft start `utility; see also Transfer CFT Management Utilities.

<span id="Shut"></span>

### Shut down

You can use one of the following methods to shut down Transfer CFT:

-   The `CFTUTIL `utility

<!-- -->



    CFTUTIL shut fast=no
    or
    CFTUTIL shut fast=yes

The `cft ` utility


    cft stop

For more information, see the administrative commands in [Manage the Transfer CFT server](https://docs.axway.com/bundle/TransferCFT_38_UsersGuide_allOS_en_HTML5/page/Content/administration/start_stop_cft.htm).

<span id="Start2"></span>

## Start or stop via a user interface

You can also use either [Central Governance](https://docs.axway.com/bundle/CentralGovernance_113_UsersGuide_allOS_en_HTML5/page/Content/CentralGov/operations/t_startCFT.htm) or the Transfer CFT to start or shut down {{< TransferCFT/hflongproductname  >}}.
