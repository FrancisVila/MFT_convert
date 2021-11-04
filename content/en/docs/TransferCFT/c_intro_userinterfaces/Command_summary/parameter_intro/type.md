{
    "title": "type",
    "linkTitle": "type",
    "weight": "3630"
}<span id="type"></span>

### type

#### ABOUT

\[ TYPE
= { <span style="text-decoration: underline;">ALL</span>
| HOST | CFT } \]

Displays
the Transfer CFT product, host, and key information.

<span id="ACT__INACT"></span>

#### ACT

\[TYPE = PART | TRK | CRON | FOLDER 
\]

Type of object to be deactivated.

-   PART
    = Partner
-   TRK
    = Select to restart Sentinel notification
-   CRON
    = Enables the cronjob CRON=ID

#### INACT

\[TYPE = PART | TRK | CRON | FOLDER
\]

Type of object to be deactivated.

-   PART
    = Partner
-   TRK
    = Select to stop dynamic Sentinel notification. All further
    messages are lost.
-   CRON
    = Disables the cronjob CRON=ID

<span id="type_CFTCOM"></span>

#### CFTCOM

TYPE = { FILE
| TCPIP}

Type of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication medium.

This parameter can take the following values:

-   FILE:
    communication is accomplished through a file
-   TCPIP:
    communication is performed through the synchronous communication medium

<span id="type_CFTNET"></span>

#### CFTNET

\[TYPE = { TCP } \] 

Defines the type of network resource. This parameter can take the following
values, according to the system:

-   TCP: TCP/IP
    network access resource

#### CFTIDF

TYPE = { RECV | SEND}

The transfer direction for which this correspondence is valid. Select
either:

-   SEND:
    for send transfers
-   RECV:
    for receive transfer

<span id="type_CFTEXIT"></span>

#### CFTEXIT

\[TYPE = {FILE
| ACCESS | EXEC | BOT }\] 

The type of exit program, as follows:

-   FILE (default value): Data is recorded
    in the monitor files
-   ACCESS: To use a directory type EXIT
-   EXEC: To use an end-of-transfer type EXIT
-   BOT: To use a beginning-of-transfer type EXIT

<span id="type_CFTACCNT"></span>

#### CFTACCNT

\[TYPE = {FILE
| SYST }\] 

This defines the accounting type. CFTACCNT TYPE parameters are:

-   FILE (default value): Data is recorded
    in the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> files defined in the fname
    and afname fields.
-   SYST: Data is recorded in the files
    of the operating system accounting utility. Available
    only on z/OS (MVS).

<span id="type_CFTPROT"></span>

#### CFTPROT

\[TYPE = {PeSIT | ODETTE  }\]

Type
of transfer protocol.

-   PeSIT:
    PeSIT protocol
-   ODETTE:
    OFTP (ODETTE) protocol
-   SFTP: SFTP protocol

#### LISTPART

TYPE ={ALL | DEST | PART | TCP}

<span id="Type_table1"></span>

#### Type table

<table>
   <tbody>
      <tr>
         <td><p>Value </p>         </td>
         <td><p>Meaning </p>         </td>
      </tr>
      <tr>
         <td><p>ALL </p>         </td>
         <td><p>Used to query the general and network characteristics of
partners<br />
Parameters of the PARTNER file</p>         </td>
      </tr>
      <tr>
         <td><p>DEST </p>         </td>
         <td><p>Used to query the parameters configured in the CFTDEST
command: concern the broadcasting lists </p>         </td>
      </tr>
      <tr>
         <td><p>PART </p>         </td>
         <td><p>Used to query the parameters configured in the CFTPART
command: description of the general data relative to partners </p>         </td>
      </tr>
      <tr>
         <td><p>TCP</p>         </td>
         <td><p>Used to query the parameters configured in the CFTTCP command:
TCP/IP network parameters associated with each partner supporting TCP/IP </p>         </td>
      </tr>
   </tbody>
</table>

<span id="type_CONFIG"></span>

#### CONFIG

TYPE = {CAT | COM | INPUT | OUTPUT
| PARM | PART}

Defines the medium concerned.

<table>
   <tbody>
      <tr>
         <td><p>Value </p>         </td>
         <td><p>Medium concerned </p>         </td>
      </tr>
      <tr>
         <td><p>CAT </p>         </td>
         <td><p>Catalog file </p>         </td>
      </tr>
      <tr>
         <td><p>COM </p>         </td>
         <td><p>Communication medium </p>         </td>
      </tr>
      <tr>
         <td><p>INPUT </p>         </td>
         <td><p>Command input file </p>         </td>
      </tr>
      <tr>
         <td><p>OUTPUT </p>         </td>
         <td><p>Report output file </p>         </td>
      </tr>
      <tr>
         <td><p>PARM </p>         </td>
         <td><p>Parameter file </p>         </td>
      </tr>
      <tr>
         <td><p>PART </p>         </td>
         <td><p>Partner file </p>         </td>
      </tr>
   </tbody>
</table>

<span id="type_SWITCH"></span>

#### SWITCH

\[TYPE = {LOG | ACCNT}\]

Defines the switch action for CFTLOG or CFTACCNT. File types are:

-   LOG:
    The SWITCH command stops message writing on the current log file, switches
    to the alternate log file, and then executes the procedure specified in
    the EXEC parameter of the CFTLOG
    object.

<!-- -->

-   ACCNT:
    The SWITCH command stops statistics from being written on the current
    statistical file, switches the writing to the alternate statistical file,
    and then executes the procedure specified in the EXEC
    parameter of the [CFTACCNT](../../../web_copilot_ui/conf_intro/cftaccnt) object.

#### CFTEXT

\[TYPE = {[see Type
table below](#Type_table) }\]

Defines the parameters to extract.

<span id="Type_table"></span>

#### Type table

<table>
   <tbody>
      <tr>
         <td><p>Value </p>         </td>
         <td><p>Meaning </p>         </td>
         <td><p>Command</p>         </td>
      </tr>
      <tr>
         <td><p>ALL </p>         </td>
         <td><p>All the parameter types of the CFTPARM and CFTPART files </p>         </td>
         <td><p> </p>         </td>
      </tr>
      <tr>
         <td><p>ACCNT </p>         </td>
         <td><p>Description of the statistical files </p>         </td>
         <td><p>CFTACCNT </p>         </td>
      </tr>
      <tr>
         <td><p>AUTH </p>         </td>
         <td><p>List of authorized files </p>         </td>
         <td><p>CFTAUTH </p>         </td>
      </tr>
      <tr>
         <td><p>CAT </p>         </td>
         <td><p>Catalog definition </p>         </td>
         <td><p>CFTCAT </p>         </td>
      </tr>
      <tr>
         <td><p>COM </p>         </td>
         <td><p>Description of <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> communication methods
 </p>         </td>
         <td><p>CFTCOM </p>         </td>
      </tr>
      <tr>
         <td><p>IDF </p>         </td>
         <td><p>File "network" identifier </p>         </td>
         <td><p>CFTIDF </p>         </td>
      </tr>
      <tr>
         <td><p>LOG </p>         </td>
         <td><p>Log file description </p>         </td>
         <td><p>CFTLOG </p>         </td>
      </tr>
      <tr>
         <td><p>NET </p>         </td>
         <td><p>Network description </p>         </td>
         <td><p>CFTNET </p>         </td>
      </tr>
      <tr>
         <td><p>PARM </p>         </td>
         <td><p>General parameters </p>         </td>
         <td><p>CFTPARM </p>         </td>
      </tr>
      <tr>
         <td><p>PART </p>         </td>
         <td><p>Partner definition  </p>         </td>
         <td><p>CFTPART and <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> network </p>         </td>
      </tr>
      <tr>
         <td><p>PROT </p>         </td>
         <td><p>Protocol definition </p>         </td>
         <td><p>CFTPROT </p>         </td>
      </tr>
      <tr>
         <td><p>RECV </p>         </td>
         <td><p>Description of the files to be received </p>         </td>
         <td><p>CFTRECV </p>         </td>
      </tr>
      <tr>
         <td><p>SEND </p>         </td>
         <td><p>Description of the files to be sent </p>         </td>
         <td><p>CFTSEND </p>         </td>
      </tr>
      <tr>
         <td><p>XLATE </p>         </td>
         <td><p>Translation table definition </p>         </td>
         <td><p>CFTXLATE </p>         </td>
      </tr>
      <tr>
         <td><p>TCP </p>         </td>
         <td><p>TCP/IP partner definition </p>         </td>
         <td><p>CFTTCP </p>         </td>
      </tr>
      <tr>
         <td>UCONF         </td>
         <td>Unified configuration         </td>
         <td>CFTEXT         </td>
      </tr>
   </tbody>
</table>

<span id="type_LISTPARM"></span>

#### LISTPARM

TYPE = {ACCNT |
ALL | AUTH | CAT | COM | ETB | IDF | LOG | NET |PARM | PROT | RECV | SEND
| XLATE }

Defines the type of parameters to
list from the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> parameter file.

TYPE can take the predefined values indicated in the Type table below.

#### Type table

<table>
   <tbody>
      <tr>
         <td><p>Value </p>         </td>
         <td><p>Definition </p>         </td>
      </tr>
      <tr>
         <td><p>ACCNT </p>         </td>
         <td><p>Used to query statistical file parameters<br />
These parameters are submitted when CFTACCNT commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>ALL </p>         </td>
         <td><p>Used to query all the parameters indicated in the PARAMETER
file </p>         </td>
      </tr>
      <tr>
         <td><p>AUTH </p>         </td>
         <td><p>Used to query file authorization lists<br />
These lists are customized by the CFTAUTH commands </p>         </td>
      </tr>
      <tr>
         <td><p>CAT </p>         </td>
         <td><p>Used to query catalog parameters<br />
These parameters are submitted when CFTCAT commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>COM </p>         </td>
         <td><p>Used to query communication media parameters<br />
These parameters are submitted when CFTCOM commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>IDF </p>         </td>
         <td><p>Used to query file "network" identifiers<br />
Identifiers are customized by the CFTIDF commands </p>         </td>
      </tr>
      <tr>
         <td><p>LOG </p>         </td>
         <td><p>Used to query log file parameters<br />
These parameters are submitted when CFTLOG commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>NET </p>         </td>
         <td><p>Used to query network characteristic parameters<br />
These parameters are submitted when CFTNET commands are entered and differ
according to the type of network configured </p>         </td>
      </tr>
      <tr>
         <td><p>PARM </p>         </td>
         <td><p>Used to query general parameters<br />
These parameters are submitted when CFTPARM commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>PROT </p>         </td>
         <td><p>Used to query protocol parameters<br />
These parameters are submitted when CFTPROT commands are entered and differ
according to the protocol configured </p>         </td>
      </tr>
      <tr>
         <td><p>RECV </p>         </td>
         <td><p>Used to query the parameters of the files to be received<br />
These parameters are submitted when CFTRECV commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>SEND </p>         </td>
         <td><p>Used to query the parameters of the files to be sent<br />
These parameters are submitted when CFTSEND commands are entered </p>         </td>
      </tr>
      <tr>
         <td><p>XLATE </p>         </td>
         <td><p>Used to query translation tables<br />
Translation tables are customized by the CFTXLATE object</p>         </td>
      </tr>
      <tr>
         <td><p>CFTFILE</p>         </td>
         <td><p>Used to create, empty, or delete <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> files</p>         </td>
      </tr>
      <tr>
         <td><p>LISTCAT</p>         </td>
         <td><p>Used to query the information associated with the selected
transfers, recorded in the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> catalog</p>         </td>
      </tr>
      <tr>
         <td><p>DISPLAY</p>         </td>
         <td><p>Used to query the information as with the LISTCAT command.
It uses an external XML file that lists and describes customized models.
These models are used to format the output</p>         </td>
      </tr>
      <tr>
         <td><p>ABOUT</p>         </td>
         <td><p>Used to display the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> computer characteristics</p>         </td>
      </tr>
   </tbody>
</table>

#### RECONFIG

TYPE = { CRON | UCONF | CAT | FOLDER | PARMCACHE | AM}

-   CAT: Resize the catalog while the Transfer CFT is running (hot catalog resizing)
-   CRON: Reload the CFTCRON objects
-   FOLDER: Reload the CFTFOLDER objects
-   UCONF: Reload the dynamic UCONF parameters
-   PARMCACHE: Clear the parameter cache
-   AM: Reload roles and privileges

#### CFTUIPREF

TYPE = string

Enter a name for the object.

 

[Return to Command index](../../)
