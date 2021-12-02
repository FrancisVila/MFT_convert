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
