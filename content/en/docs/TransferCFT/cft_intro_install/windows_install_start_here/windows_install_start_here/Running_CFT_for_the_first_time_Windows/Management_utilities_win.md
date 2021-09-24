{
    "title": "Management utilities",
    "linkTitle": "Management utilities",
    "weight": "280"
}# <span id="Management_utilities"></span>Management utilities

This topic describes the following management utilities:

-   [cftinit](#cftinit)
-   [cft start](#cftstart)
-   [cft stop](#cftstop)
-   [cftupdate](#cftupdate)

## Management utilities descriptions

## <span id="cftinit"></span>cftinit

*cftinit* is a general Transfer CFT
initialization utility. Prior to running cftinit, you must stop both the Copilot and Transfer CFT server.

**Syntax**

cftinit \[&lt;filename> \[&lt;filename>...\]\]

**Standard use**

*cftinit* is normally used with a single
parameter, which is the name of the Transfer CFT configuration file.

cftinit my\_config.cft

**Advanced use**

Several file names can be included in the command line. Normally, all
Transfer CFT parameters are declared in a single file. However, for organizational
reasons, you may wish to separate the configuration into several files
(for example, a file describing the CFTPART cards and another file containing
the CFTPARM, CFTLOG cards, and so on).

cftinit partners.cft the\_rest.cft

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">          </td>
      </tr>
</table>

-   If no file name
    is passed as a parameter, the program requests one or more file names
-   If no name is supplied,
    the program stops
-   When you run cftinit, it creates the catalog and communication files. You can modify the default sizes of these files to suit your requirements by updating the uconf values for cft.cftcat.default\_size and cft.cftcom.default\_size (these values are expressed as a number of records).

## <span id="cftstart"></span>cft start

The *cft start* utility performs a controlled start of Transfer
CFT and its additional elements.

**Syntax**

cft start

**Standard use**

*cft start* is normally used without
parameters. It checks the Transfer CFT environment to ensure that Transfer
CFT starts up correctly. It then runs Transfer CFT, waits for the processes
to start up and displays an information message with the process identifier
(PID) of the CFTMAIN process.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>% cft start<br/>Starting CFT with IDPARM "IDPARM0"<br/>Starting CFTMAIN ... started<br/>Starting CFTTCOM .... started<br/>Starting CFTTPRO ... started<br/>Starting CFTLOG ... started<br/>CFT started correctly.<br/>CFTMAIN process ID is 23564.<br/>%         </td>
      </tr>
   </tbody>
</table>

## <span id="cftstop"></span>cft stop

The *cft stop* utility performs a controlled shutdown of Transfer
CFT.

**Syntax**

cft stop \[-kill\]

**Standard use**

The *cft stop* command, used without parameters, shuts down Transfer
CFT by sending the SHUT FAST=YEScommand. It then waits until the
various Transfer CFT processes are stopped.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>% cft stop<br/>Waiting for CFTLOG .... stopped<br/>Waiting for CFTTCPS ... stopped<br/>Waiting for CFTTPRO ... stopped<br/>Waiting for CFTTCOM ... stopped<br/>Waiting for CFTTFIL ... stopped<br/>Waiting for CFTMAIN ....stopped<br/>CFT stopped correctly.<br/>%         </td>
      </tr>
   </tbody>
</table>

If *cft stop* detects abnormal behavior during the shutdown phase,
it displays the following message:

% cft stop  
Invalid state of Transfer CFT.

Use Cft force-stop to force Transfer CFT to shut down.

**Advanced use**

In the event of a problem, the program recommends that you shut down
Transfer CFT using theCft force-stopcommand.

This command then forces a Transfer CFT shutdown. It is normally successful,
but depending on the state of the system, more serious malfunctions may
be encountered.

If a serious malfunction occurs at Transfer CFT level, an alarm message
is displayed before continuing with the housekeeping procedure, to inform
you about the possible consequences of the next command.

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>% cft stop<br/>Invalid state of CFT.<br/>Use<span>Cft force-stop</span> to force shutdown of  <span>Transfer CFT</span><br/>% cft stop -kill</p>
            <p>Stopping Transfer CFT...</p>
            <p>Transfer CFT stopped correctly.</p>
         </td>
      </tr>
   </tbody>
</table>

## <span id="cftupdate"></span>cftupdate

The cftupdate utility is used to update the configuration.

**Syntax**

cftupdate &lt;filename> \[&lt;filename> ...\]

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">          </td>
      </tr>
</table>

-   You can only update
    the CFTPART, CFTxxx (for the networks), CFTSEND cards, and so on.
-   This command should
    be considered to be an alias of CFTUTIL #&lt;filename> for each file
    name passed as a parameter in the command line.
