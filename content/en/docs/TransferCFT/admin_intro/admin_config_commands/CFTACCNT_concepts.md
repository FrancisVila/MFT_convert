{
    "title": "Recording  mode for statistical data",
    "linkTitle": "CFTACCNT - Recording mode for statistical data ",
    "weight": "230"
}The CFTACCNT object defines the recording mode for statistical data
of correctly terminated transfers. See also the parameter list
[CFTACCNT.](../../../c_intro_userinterfaces/web_copilot_ui/conf_intro/cftaccnt)

<span id="About_the_CFTACCNT_object"></span>

## About the CFTACCNT object

Two recording modes are available:

-   Recording data
    in {{< TransferCFT/componentshortname >}} files. When the primary file is full, {{< TransferCFT/componentshortname >}}
    switches to an alternate file. This mode is available on all operating
    systems.
-   Recording data
    in the files of the operating system accounting utility.

The CFTACCNT object can be permanently deleted from the configuration.
Once the CFTACCNT is deactivated, it appears gray in the left pane object
manager. For more information refer to Deleting
the CFTACCNT (UI) object.

In addition to defining the CFTACCNT object, for the statistical mode
to operate, you must define the CFT ACCNT parameter in the CFTPARM object.

CFTACCNT is used to define the recording mode of the statistical data
for correctly terminated transfers, that is transfers that are in the
T or X state. This command is taken into account when the ACCNT parameter
of the CFTPARM command is defined.

{{< TransferCFT/componentshortname  >}} authorizes only one identifier of the CFTACCNT type.

Two recording modes can be used, depending on the system:

-   Recording of data
    in {{< TransferCFT/componentshortname >}} files. In this case, the CFTACCNT command defines the names of the files receiving
    the data and their management (parameter setting TYPE = FILE). This mode
    is available on ALL SYSTEMS.

<!-- -->

-   Recording of data
    in the files of the accounting utility of the operating system in question
    parameter setting TYPE = SYST. This
    mode is only available on z/OS (MVS) systems.

For more information on the TYPE parameter in the statistical recording
mode, see [Recording mode TYPE](#Recordin). For each terminated transfer, {{< TransferCFT/componentshortname  >}} records the information
contained in the following table.

CFTACCNT list of headings

<table>
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Heading         </th>
<th class="HeadE-Column1-Header1"><p>Offset</p>
<p>V24</p>         </th>
<th class="HeadD-Column1-Header1"><p>Offset</p>
<p>V23</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Transfer mode (server or requester) </p>         </td>
         <td>0         </td>
         <td>0         </td>
      </tr>
      <tr>
         <td><p>Transfer direction </p>         </td>
         <td>1         </td>
         <td>1         </td>
      </tr>
      <tr>
         <td><p>Transfer type (File, Message or Reply message)  </p>         </td>
         <td>2         </td>
         <td>2         </td>
      </tr>
      <tr>
         <td><p>Immediate partner identifier (PART) </p>         </td>
         <td>3         </td>
         <td>3         </td>
      </tr>
      <tr>
         <td><p>Sender identifier (SPART) </p>         </td>
         <td>68         </td>
         <td>12         </td>
      </tr>
      <tr>
         <td><p>Receiver identifier (RPART) </p>         </td>
         <td>133         </td>
         <td>21         </td>
      </tr>
      <tr>
         <td><p>Identifier of the sending user application (SUSER) </p>         </td>
         <td>198         </td>
         <td>30         </td>
      </tr>
      <tr>
         <td><p>Identifier of the receiving user application (RUSER) </p>         </td>
         <td>231         </td>
         <td>46         </td>
      </tr>
      <tr>
         <td><p>Model file identifier (IDF) </p>         </td>
         <td>264         </td>
         <td>62         </td>
      </tr>
      <tr>
         <td><p>Local application identifier (IDA) </p>         </td>
         <td>297         </td>
         <td>71         </td>
      </tr>
      <tr>
         <td><p>Transfer identifier (IDT) </p>         </td>
         <td>330         </td>
         <td>80         </td>
      </tr>
      <tr>
         <td><p>Number of records sent </p>         </td>
         <td>339         </td>
         <td>89         </td>
      </tr>
      <tr>
         <td><p>Number of characters in the file (FBYTE)</p>         </td>
         <td>350         </td>
         <td>100         </td>
      </tr>
      <tr>
         <td><p>Number of characters sent over the line (NBYTE)</p>         </td>
         <td>361         </td>
         <td>111         </td>
      </tr>
      <tr>
         <td><p>Date and time of command entry in the catalog </p>         </td>
         <td>372         </td>
         <td>122         </td>
      </tr>
      <tr>
         <td><p>Date and time of start of transfer </p>         </td>
         <td>390         </td>
         <td>140         </td>
      </tr>
      <tr>
         <td><p>Date and time of end of transfer </p>         </td>
         <td>408         </td>
         <td>158         </td>
      </tr>
      <tr>
         <td><p>Transfer duration (in seconds) </p>         </td>
         <td>426         </td>
         <td>176         </td>
      </tr>
      <tr>
         <td><p>Broadcasting list indicator </p>         </td>
         <td>433         </td>
         <td>183         </td>
      </tr>
      <tr>
         <td><p>Application protocol identifier </p>         </td>
         <td>434         </td>
         <td>184         </td>
      </tr>
      <tr>
         <td><p>Transfer owner identifier (USERID) </p>         </td>
         <td>467         </td>
         <td>193         </td>
      </tr>
      <tr>
         <td><p>Group identifier (GROUPID) </p>         </td>
         <td>500         </td>
         <td>209         </td>
      </tr>
      <tr>
         <td><p>On line data compression rate </p>         </td>
         <td>533         </td>
         <td>225         </td>
      </tr>
      <tr>
         <td><p>File record maximum size (FLRECL) </p>         </td>
         <td>536         </td>
         <td>228         </td>
      </tr>
      <tr>
         <td><p>File (FRECFM) </p>         </td>
         <td>542         </td>
         <td>234         </td>
      </tr>
      <tr>
         <td><p>Protocol compression code (NCOMP) </p>         </td>
         <td>543         </td>
         <td>235         </td>
      </tr>
      <tr>
         <td><p>Name of the file sent (FNAME) </p>         </td>
         <td>546         </td>
         <td>238         </td>
      </tr>
      <tr>
         <td><p>{{< TransferCFT/componentshortname  >}} private parameter (PARM) </p>         </td>
         <td>1059         </td>
         <td>303         </td>
      </tr>
      <tr>
         <td><p>Sender application identifier (SAPPL) </p>         </td>
         <td>1572         </td>
         <td>384         </td>
      </tr>
      <tr>
         <td><p>Receiver application identifier (RAPPL) </p>         </td>
         <td>1621         </td>
         <td>433         </td>
      </tr>
      <tr>
         <td><p>Partner group (GROUP) </p>         </td>
         <td>1670         </td>
         <td>482 (*)         </td>
      </tr>
      <tr>
         <td>Number of characters in the file (FBYTE_EXTENDED)         </td>
         <td>1703         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Number of characters sent over the line (NBYTE_EXTENDED)         </td>
         <td>1719         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Logic file network identifier (NIDF)         </td>
         <td>1735         </td>
         <td>          </td>
      </tr>
      <tr>
         <td>Unused         </td>
         <td>1768         </td>
         <td>          </td>
      </tr>
      <tr>
         <td><p>Total</p>         </td>
         <td>2048         </td>
         <td><p>491</p>
<p>z/OS: 482</p>         </td>
      </tr>
   </tbody>
</table>

(\*) z/OS: For format V23 the partner group is not included in account structure. The total length is 482.

To use the account file in an application, you must refer to the header file that is delivered in the Transfer CFT runtime directory as either a cftcnt.h (C language for all platforms) or cftcnt.cop (COBOL on z/OS and IBM i) file.

<span id="Recordin"></span>

## Recording mode TYPE

This section describes the parameters to define the type of recording
mode. You can select from either the saving the recorded information in
a file, or in the system. Declaring where to save transfer information
is defined in the TYPE parameter.

<span id="Setting_TYPE_to_FILE"></span>

### Setting TYPE to FILE

When you
define the Type parameter to File
in the CFTACCNT object, you must define the following parameters as well.

-   afname
-   exec
-   fname
-   maxrec
-   switch

The {{< TransferCFT/componentshortname  >}} statistical
file is full when the maximum number of records, the MAXREC parameter,
is reached. When this happens, the {{< TransferCFT/componentshortname  >}} switches to an alternate
file and executes the procedure defined by the EXEC parameter.

The SWITCH operating command also allows the operator to manually switch
the statistical file on request.

{{< TransferCFT/componentshortname  >}} requires at least 1 empty statistical file at the time
it is activated. If the first file designated by FNAME is not empty, Transfer
CFT switches to the second file labeled AFNAME. The procedure associated
with the switching can regenerate an empty file.

The statistical files must be created before the {{< TransferCFT/componentshortname  >}} is activated.
This operation is performed in the command CFTFILE TYPE = ACCNT.

When you shut down {{< TransferCFT/componentshortname  >}}, using the SHUT command, {{< TransferCFT/componentshortname  >}}
executes the switching procedure to empty the last statistical file in
process.

<span id="Setting_TYPE_to_SYST"></span>

### Setting TYPE to SYST

When you
define the Type parameter as SYST
in the CFTACCNT object, you must define the ACCID
parameter as well.

The CFTACCNT command references
the {{< TransferCFT/componentshortname  >}} application via the utility.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1">Protocol         </th>
<th class="HeadD-Column1-Header1">Details         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>z/OS (MVS)</p>         </td>
         <td><p>The ACCID parameter identifying the {{< TransferCFT/componentshortname  >}} application
must be defined.</p>         </td>
      </tr>
   </tbody>
</table>

Syntax

CFTACCNT TYPE = FILE

[TYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= FILE

[FNAME](../../../c_intro_userinterfaces/command_summary/parameter_intro/fname)
= filename

[ID](../../../c_intro_userinterfaces/command_summary/parameter_intro/id)
= identifier

\[ [AFNAME](../../../c_intro_userinterfaces/command_summary/parameter_intro/afname)
= filename \]

\[ [COMMENT](../../../c_intro_userinterfaces/command_summary/parameter_intro/comment)
= string \]

\[ [EXEC](../../../c_intro_userinterfaces/command_summary/parameter_intro/exec)
= filename \]

\[ [LANGUAGE](../../../c_intro_userinterfaces/command_summary/parameter_intro/language)
= {
| C } \]

\[ [MAXREC](../../../c_intro_userinterfaces/command_summary/parameter_intro/maxrec)
= {
| n } \]

\[ [MODE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mode)
= {
| CREATE | DELETE } \]

\[ [SWITCH](../../../c_intro_userinterfaces/command_summary/parameter_intro/switch)
= {
| time } \]

\[ [FORMAT](../../../c_intro_userinterfaces/command_summary/parameter_intro/format)
= {
| 23 | V24 | 24} \]

 

CFTACCNT TYPE = SYST

[TYPE](../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= SYST

[ACCID](../../../c_intro_userinterfaces/command_summary/parameter_intro/accid)
= n

[ID](../../../c_intro_userinterfaces/command_summary/parameter_intro/id)
= identifier

\[ [COMMENT](../../../c_intro_userinterfaces/command_summary/parameter_intro/comment)
= string \]

\[ [FORMAT](../../../c_intro_userinterfaces/command_summary/parameter_intro/format)
= {
| 23 | V24 | 24} \]

\[ [LANGUAGE](../../../c_intro_userinterfaces/command_summary/parameter_intro/language)
= {
| C } \]

\[ [MODE](../../../c_intro_userinterfaces/command_summary/parameter_intro/mode)
= {
| CREATE | DELETE } \]
