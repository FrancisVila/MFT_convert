{
    "title": "User  interface options",
    "linkTitle": "User interface options",
    "weight": "160"
}Select the appropriate user interface according to tasks you want to perform.

### Configuration, monitoring, and flow management

#### <span class="mc-variable Primary.CG or_UM variable">Central Governance</span>

<span class="mc-variable suite_variables.FlowManager variable">Flow Manager</span> and Central Governance are <span class="mc-variable axway_variables.Company_Name variable">Axway</span> user interfaces that provides a complete set of services to govern <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. For more information, see [Governance services](../c_cg_concepts).

-   For details on creating your first <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> flows using <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span>, see [Getting started](../../gettingstarted_intro).
-   For details on integrating <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> with <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>, see [Integration overview](../../governance_services_intro/governance_overview).
-   Refer to the OS specific installation guide for instructions on how to activate <span class="mc-variable suite_variables.Central_GovernanceName variable">Central Governance</span> connectivity and register your Transfer CFT.

### Runtime activities

#### Browser based user interface

<span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span> features a web browser user interface that you can use to create, track and manage transfers, manage security, and mange the Transfer CFT log.

<span id="CFTUTIL_interface"></span>

#### CFTUTIL interface

The CFTUTIL interface provides a batch or interactive line-mode interface
to execute <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> operating commands.

The CFTUTIL commands that are described in this documentation are collectively listed
in the topic [Command index](../../c_intro_userinterfaces/command_summary). You can use this as a quick reference
to find command syntax and parameters.

<span id="Web_services_interface"></span>

#### 

#### Application Programming Interface and REST API

An Application Programming Interface, or API, is a way to interface your application with <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>. In Transfer CFT, APIs operate as a set of functions
that use a service.

In Transfer CFT you can use:

-   C, COBOL, and JPI APIs to create customized and automated transfer and monitoring services for a more tightly knit application integration.
-   REST APIs to create and monitor transfers, and to configure <span class="mc-variable suite_variables.TransferCFTName variable">Transfer CFT</span>. Each supported Transfer CFT REST API command provides a description, which includes possible parameters.

#### Web services interface

You can use the Web services option to open a <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> session.
Using <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> Web Services, you can access all main functions for
managing <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span>. These functions include:

-   Monitoring Transfer
    CFT: consult the log, the catalog, and transfer statistics
-   Creating transfers:
    create a new file transfer, a message, or transfer reply

The Web Services requests sent by the client are processed on the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> UI server listening port.
