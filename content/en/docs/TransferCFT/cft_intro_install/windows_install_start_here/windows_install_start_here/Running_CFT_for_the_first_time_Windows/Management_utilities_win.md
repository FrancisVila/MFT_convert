{
    "title": "Management  utilities",
    "linkTitle": "Management utilities",
    "weight": "270"
}This topic describes the following management utilities:

- [cftinit](#cftinit)
- [cft start](#cftstart)
- [cft stop](#cftstop)
- [cftupdate](#cftupdate)

## Management utilities descriptions

<span id="cftinit"></span>

## cftinit

*cftinit* is a general Transfer CFT{{< TransferCFT/componentshortname  >}}
initialization utility. Prior to running cftinit, you must stop both the Copilot and Transfer CFT server.

**Syntax**

`cftinit [<filename> [<filename>...]]`

**Standard use**

*cftinit* is normally used with a single
parameter, which is the name of the Transfer CFT{{< TransferCFT/componentshortname  >}} configuration file.

cftinit my\_config.cft

**Advanced use**

Several file names can be included in the command line. Normally, all
Transfer CFT{{< TransferCFT/componentshortname  >}} parameters are declared in a single file. However, for organizational
reasons, you may wish to separate the configuration into several files
(for example, a file describing the CFTPART cards and another file containing
the CFTPARM, CFTLOG cards, and so on).

cftinit partners.cft the\_rest.cft

> **Note**
>
>  

- If no file name
    is passed as a parameter, the program requests one or more file names
- If no name is supplied,
    the program stops
- When you run cftinit, it creates the catalog and communication files. You can modify the default sizes of these files to suit your requirements by updating the uconf values for cft.cftcat.default\_size and cft.cftcom.default\_size (these values are expressed as a number of records).

<span id="cftstart"></span>

## cft start

The *cft start* utility performs a controlled start of Transfer
CFT and its additional elements.

**Syntax**

`cft start `

**Standard use**

*cft start* is normally used without
parameters. It checks the Transfer CFT{{< TransferCFT/componentshortname  >}} environment to ensure that Transfer
CFT starts up correctly. It then runs Transfer CFT{{< TransferCFT/componentshortname  >}}, waits for the processes
to start up and displays an information message with the process identifier
(PID) of the CFTMAIN process.

```
% cft start
Starting CFT with IDPARM "IDPARM0"
Starting CFTMAIN ... started
Starting CFTTCOM .... started
Starting CFTTPRO ... started
Starting CFTLOG ... started
CFT started correctly.
CFTMAIN process ID is 23564.
%
```
<span id="cftstop"></span>

## cft stop

The *cft stop* utility performs a controlled shutdown of Transfer
CFT.

**Syntax**

`cft stop [-kill]`

**Standard use**

The *cft stop* command, used without parameters, shuts down Transfer
CFT by sending the SHUT FAST=YEScommand. It then waits until the
various Transfer CFT{{< TransferCFT/componentshortname  >}} processes are stopped.

```
% cft stop
Waiting for CFTLOG .... stopped
Waiting for CFTTCPS ... stopped
Waiting for CFTTPRO ... stopped
Waiting for CFTTCOM ... stopped
Waiting for CFTTFIL ... stopped
Waiting for CFTMAIN ....stopped
CFT stopped correctly.
%
```

If *cft stop* detects abnormal behavior during the shutdown phase,
it displays the following message:

`% cft stopInvalid state of  Transfer CFT{{< TransferCFT/componentshortname >}}.`

Use Cft force-stop to force Transfer CFT{{< TransferCFT/componentshortname  >}} to shut down.

**Advanced use**

In the event of a problem, the program recommends that you shut down
Transfer CFT{{< TransferCFT/componentshortname  >}} using theCft force-stopcommand.

This command then forces a Transfer CFT{{< TransferCFT/componentshortname  >}} shutdown. It is normally successful,
but depending on the state of the system, more serious malfunctions may
be encountered.

If a serious malfunction occurs at Transfer CFT{{< TransferCFT/componentshortname  >}} level, an alarm message
is displayed before continuing with the housekeeping procedure, to inform
you about the possible consequences of the next command.

```
% cft stop
Invalid state of CFT.
UseCft force-stop to force shutdown of Transfer CFT{{< TransferCFT/componentshortname >}}
% cft stop -kill
Stopping Transfer CFT...
Transfer CFT stopped correctly.
```
<span id="cftupdate"></span>

## cftupdate

The cftupdate utility is used to update the configuration.

**Syntax**

`cftupdate <filename> [<filename> ...]`

> **Note**
>
>  

- You can only update
    the CFTPART, CFTxxx (for the networks), CFTSEND cards, and so on.
- This command should
    be considered to be an alias of CFTUTIL #&lt;filename> for each file
    name passed as a parameter in the command line.
