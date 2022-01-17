{
    "title": "User  interface options",
    "linkTitle": "User interface options",
    "weight": "160"
}Select the appropriate user interface according to tasks you want to perform.

### Configuration, monitoring, and flow management

#### Central Governance

Flow Manager{{< TransferCFT/flowmanager  >}} and Central Governance are Axway{{< TransferCFT/companyname  >}} user interfaces that provides a complete set of services to govern Transfer CFT{{< TransferCFT/componentshortname  >}}. For more information, see [Governance services](../c_cg_concepts).

- For details on creating your first Transfer CFT{{< TransferCFT/componentlongname >}} flows using Central Governance{{< TransferCFT/centralgovernancename >}}, see [Getting started](../../gettingstarted_intro).
- For details on integrating Central Governance{{< TransferCFT/centralgovernancename >}} with Transfer CFT{{< TransferCFT/componentlongname >}}, see [Integration overview](../../governance_services_intro/governance_overview).
- Refer to the OS specific installation guide for instructions on how to activate Central Governance{{< TransferCFT/centralgovernancename >}} connectivity and register your Transfer CFT.

### Runtime activities

#### Browser based user interface

Transfer CFT{{< TransferCFT/transfercftname  >}} features a web browser user interface that you can use to create, track and manage transfers, manage security, and mange the Transfer CFT log.

<span id="CFTUTIL_interface"></span>

#### CFTUTIL interface

The CFTUTIL interface provides a batch or interactive line-mode interface
to execute Transfer CFT{{< TransferCFT/componentshortname  >}} operating commands.

The CFTUTIL commands that are described in this documentation are collectively listed
in the topic [Command index](../../c_intro_userinterfaces/command_summary). You can use this as a quick reference
to find command syntax and parameters.

<span id="Web_services_interface"></span>

#### 

#### Application Programming Interface and REST API

An Application Programming Interface, or API, is a way to interface your application with Transfer CFT{{< TransferCFT/componentlongname  >}}. In Transfer CFT, APIs operate as a set of functions
that use a service.

In Transfer CFT you can use:

- C, COBOL, and JPI APIs to create customized and automated transfer and monitoring services for a more tightly knit application integration.
- REST APIs to create and monitor transfers, and to configure Transfer CFT{{< TransferCFT/transfercftname >}}. Each supported Transfer CFT REST API command provides a description, which includes possible parameters.

#### Web services interface

You can use the Web services option to open a Transfer CFT{{< TransferCFT/componentshortname  >}} session.
Using Transfer CFT{{< TransferCFT/componentshortname  >}} Web Services, you can access all main functions for
managing Transfer CFT{{< TransferCFT/componentshortname  >}}. These functions include:

- Monitoring Transfer
    CFT: consult the log, the catalog, and transfer statistics
- Creating transfers:
    create a new file transfer, a message, or transfer reply

The Web Services requests sent by the client are processed on the Transfer CFT{{< TransferCFT/componentshortname  >}} UI server listening port.
