{
    "title": "Enable Sentinel and Event Router ",
    "linkTitle": "Enable Sentinel and Event Router ",
    "weight": "260"
}Enabling the Axway Sentinel option for Transfer CFT is generally comprised of the following steps, which you must execute in the order listed:

-   Install the Event Router

<!-- -->

-   Set the Sentinel parameters in the unified configuration file

<!-- -->

-   Create a LOGGER type padding file (optional)
    -   Use the LOGGER in a SYSPLEX

<!-- -->

-   Shut down Transfer CFT

<!-- -->

-   Restart Transfer CFT

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">Universal Agent installation is necessary only for end-to-end application monitoring.         </td>
      </tr>
</table>

## Procedure

This section provides step by step instructions for installing Sentinel for Transfer CFT z/OS.

### <span id="Install the Event Router"></span>Install the Event Router

For detailed information about Event Router installation refer to the Sentinel Event Router information in the *Axway A 5 Suite Prerequisites and Installation Guide*.

-   During the installation procedure, specify the creation of the BUFFER file as the type LOGGER (under SYSPLEX).
-   During setup, a LOGGER type BUFFER file is created. Note the name of the file for use when setting values of the configuration file.

If the Event Router is not set up, you must create a LOGGER type file using the JCL: SN10CLGR.

### <span id="Set the Sentinel parameters  A00CUSTO"></span>Set the Sentinel parameters A00CUSTO

You can set the Sentinel parameters in the unified configuration. If the Sentinel parameters are already customized, skip this section. Otherwise, customization parameters are located in the parameter file A03PARM of the installation library (sntlocad, sntladd, sntlp, sntlqueue, sntlgstr).

For a description of the general parameters refer to the Event Router information in the *Sentinel* documentation.

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">If the communication mode between Transfer CFT and the Event Router is an XCF type, and the TRKSVC is equal to 0, then you must define the Transfer CFT executable library as APF authorized.         </td>
      </tr>
</table>

### <span id="Activate the unified configuration file parameters SN05CONF"></span>Activate the unified configuration file parameters SN05CONF

Before submitting the SN05CONF JCL, you can modify the command file. Enter:

Trktname parameter

-   Using a buffer file is strongly encouraged, but not mandatory. If you prefer to not use a buffer file, modify the command UCONFSET as follows:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>UCONFSET ID=sentinel.TRKTNAME,VALUE=         </td>
      </tr>
   </tbody>
</table>

-   The following message displays in the log when you restart Transfer CFT:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>CFTS31W XTRK Warning No Buffer File(LOGGER file)defined Error Code = -1         </td>
      </tr>
   </tbody>
</table>

To connect to the Event Router via XFC, manually modify the commands file to activate the appropriate communication mode and comment commands:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>/* UCONFSET ID=sentinel.TRKIPADDR,            <p>         VALUE=sntladdr                   </p>            <p>     UCONFSET ID=sentinel.TRKIPPORT,VALUE=sntlp*/</p>         </td>
      </tr>
   </tbody>
</table>

### <span id="Create_a_LOGGER_type_padding_file (optional)"></span>Create a LOGGER type padding file (optional)

If the Transfer CFT does not use the same padding file as the Event Router, you must create a padding file. This LOGGER type file should not be shared with other applications.  

The new LOGGER file is a DASD-ONLY type file. Use the JCL SN10CLGR, via the IBM IXCMIAPU utility, to create this file.

**Example**

<table cellspacing="0">
   <col/>
      <tr>
         <td>
            <p>DEFINE LOGSTREAM NAME(sntlgstr)</p>
            <p>DASDONLY(YES) </p>
            <p>LOWOFFLOAD(0) </p>
            <p>LS_SIZE(180)</p>
            <p>STG_SIZE(0) </p>
            <p>MAXBUFSIZE(64000)</p>
         </td>
      </tr>
</table>

The keywords that are displayed in bold should be substituted by the JCL A00CUSTO. For more information refer to the IBM documentation on *Setting up a Sysplex*.

#### Use the LOGGER file in a SYSPLEX  

To create an overflow file (LOGGER) that is available for all SYSPLEX partitions, in the Coupling Facility Resource Manager (CFRM) add the following structure (&userstr) to the coupling data set.

Example

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p> The following is an example of a structure definition:</p>
            <p>STRUCTURE NAME(&amp;userstr)</p>
            <p>SIZE(6000)</p>
            <p>INITSIZE(1200)</p>
            <p>REBUILDPERCENT(30)</p>
            <p>PRELIST(FACIL02,FACIL01)</p>
            <p> </p>
            <p> The following is an example of a logstream definition:</p>
            <p>DEFINE LOGSTREAM NAME(&amp;LGRID)</p>
            <p>STRUCTNAME(&amp;userstr)</p>
            <p>&amp;Userstr is the structure name</p>
            <p>&amp;LGRID is the logger file name</p>
         </td>
      </tr>
   </tbody>
</table>

<table cellpadding="0" cellspacing="0">
   <col/>
   <col/>
   <col/>
      <tr>
         <td valign="top">         </td>
         <td valign="top"><span><b>Note</b></span>
         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" valign="top">You must be a system administrator to perform these operations.         </td>
      </tr>
</table>

### <span id="Overflow file definition"></span>Overflow file definition

The following table describes the overflow file definition for the Logger file, where:

-   TRKSHAREDFILE=YES is MANDATORY when the logger file is shared between the Event Router and applications. Set this to NO if the applications are sending messages directly to the Sentinel server without going through a ER
-   The log structure is ONLY used to define a logger file shared between the partitions of the SYSPLEX, and is NOT referenced in any parameters

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th> </th>
         <th>Event Router</th>
         <th>TRKUTIL</th>
         <th>Transfer CFT 2.7 and later</th>
      </tr>
   </thead>
      <tr data-mc-conditions="">
         <th>Configuration file</th>
         <td>USEPARIN         </td>
         <td>TRKCONF         </td>
         <td>UCONF         </td>
      </tr>
      <tr data-mc-conditions="">
<th rowspan="2">Logger file</th>
         <td>
            <p>	(AGENT)</p>
            <p>api_file=</p>
         </td>
         <td>	TRKTNAME=         </td>
         <td>	UCONFSET ID=sentinel.TRKTNAME, VALUE=xxxx.xxxx.xxx         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>          </td>
         <td>TRKSHAREDFILE=YES	         </td>
         <td>UCONFSET ID=sentinel.TRKSHAREDFILE,VALUE=YES         </td>
      </tr>
</table>

###  <span id="Communication with the Event Router"></span>Communication with the Event Router

The following parameters define communication with the Event Router via XCF. In this setup:

-   The XCF definition (queue=xxxx) is the XCF member name representing the ER server
-   The XCF group is PELISCOP by default. You can modify this default by setting queue = “member group”

<table cellspacing="0">
   <col/>
   <col/>
   <col/>
   <col/>
   <thead>
      <tr>
         <th> </th>
         <th>Event Router</th>
         <th>TRKUTIL</th>
         <th>Transfer CFT 2.6.x</th>
      </tr>
   </thead>
      <tr data-mc-conditions="">
         <td>Configuration file         </td>
         <td>USEPARIN         </td>
         <td>TRKCONF         </td>
         <td>UCONF         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>SVC         </td>
         <td>
            <p>(SYSTEM) </p>
            <p>svc_nb=nnn</p>
         </td>
         <td>TRKSVC=nnn         </td>
         <td>UCONFSET ID=sentinel.TRKSVC,VALUE=nnn         </td>
      </tr>
      <tr data-mc-conditions="">
         <td rowspan="2">XCF definition         </td>
         <td rowspan="2">(AGENT)queue=         </td>
         <td>TRKQUEUE=         </td>
         <td>UCONFSET ID=sentinel.TRKQUEUE,VALUE=xxxx         </td>
      </tr>
      <tr data-mc-conditions="">
         <td>TRKTYPE=XCF         </td>
         <td>UCONFSET ID=sentinel.TRKTYPE,VALUE=XCF         </td>
      </tr>
</table>

### <span id="Modify the Transfer CFT start-up procedure"></span>Modify the Transfer CFT start-up procedure

During the start-up procedure, the task dedicated to managing messages towards Sentinel allocates a sysout (ddname=TRKOUT) for any generated error messages or traces.

### <span id="Register configuration file values"></span>Register configuration file values

For configuration file modifications to be taken into account, including updates, stop and then restart Transfer CFT.

### <span id="Set message sending mode"></span>Set message sending mode

Use the TRKTMODE parameter of the configuration file to manage the sending mode for messages emitted towards Sentinel.

Possible values:

-   TRKTMODE=I: Immediate, default value

<!-- -->

-   TRKTMODE=D: Differed, the messages are stored to the buffer file

<!-- -->

-   TRKTMODE=R: Retry, enables the management of a sending delay via a parameter TRKTCONNRETRY=nn in case of a connection problem with SENTINEL

### TCP/IP source port conflict

Sentinel notifications can get the source port from the system when the variable sentinel.trk\_min\_port is set to '0' (zero).

The system will assign one of the Ephemeral Port range (default is 1024 - 65535)

Command: uconfset id='sentinel.trk\_min\_port',value=0

### End-to-End monitoring examples

The following JCLs are available as end-to-end monitoring examples:

-   SNTLCFT: The deposit of a file transfer command via the CFTUTIL utility, with the same CycleID as generated by the TRKUTIL SENDEVENT command. This is available in the INSTALL library.

<!-- -->

-   SNTLEXEC: The end of transfer procedure, associating an acknowledgement via the CFTUTIL utility and the ‘COMPUTEIDENT’, ‘SENDEVENT’, and ‘SENDCYCLE’ TRKUTIL command. This is available in the EXEC library.

## <span id="Heartbeats zOS"></span>Implement Heartbeat functionality<span id="kanchor50"></span>

The CFTHEART JCL sets the unified configuration heartbeat values as follows:

-   sentinel.heartbeat.enable = YES
-   sentinel.heartbeat.periodicity = 300 (This recommended value has a direct correlation with the value defined in the Tracked Object.)
-   sentinel.heartbeat.script = &lt;install\_dir>/extras/sentinel/MFTheartbeat.\*
-   sentinel.trkipaddr = sentinel.server.address
-   sentinel.trkipport = Sentinel.qlt/auto.port value (default = 1305)
-   sentinel.xfb.enable = YES
