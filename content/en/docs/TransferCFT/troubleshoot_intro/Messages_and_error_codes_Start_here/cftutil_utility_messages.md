{
    "title": "CFTUTIL  utility output messages: CFTunnx",
    "linkTitle": "CFTUTIL utility messages",
    "weight": "410"
}<span id="Messages_from_the_CFTUTIL_utility"></span>You can find the utility output in either the standard output or the redirection file.

```
Error
<span id="CFTU00I"></span>CFTU00I: &Cmd _
Correct (&str)
Information
The &Cmd command is executed correctly. The &str
string represents the parameters passed with this command (up to 50 characters).
```

 

```
Error
<span id="CFTU01E"></span>CFTU01E: storage allocation
error
Explanation
The communication utility could not acquire the memory
required to run.
Consequence
Immediate shutdown of the communication utility.
Action
Inform Product Support.
```

 

```
Error
<span id="CFTU02E"></span>CFTU02E: unable to allocate
file &Fname
Explanation
Problem allocating the file containing the parameter setting
commands.
Consequence
Immediate shutdown of the communication utility.
Action
Check the existence and state of the file, correct the
error and then restart the communication utility.
```

 

```
Error
<span id="CFTU03E"></span>CFTU03E: unable to open
file &Fname
Explanation
Problem opening the file containing the parameter setting
commands.
Consequence
Immediate shutdown of the communication utility.
Action
Check the characteristics of the file to be opened and
inform Product Support if necessary.
```

 

```
Error
<span id="CFTU04E"></span>CFTU04E: error reading
input file &Fname
Explanation
Problem reading the file containing the parameter setting
commands.
Consequence
Immediate shutdown of the communication utility.
Action
Check the characteristics of the file to be opened and
inform Product Support if necessary.
```

 

```
Error
<span id="CFTU05E"></span>CFTU05E: &Cmd Failed
_ Unexpected end of file (command)
Explanation
The end of the file was reached before the end of the command
(the last character of the command line may be a comma).
Consequence
Immediate shutdown of the communication utility.
Action
Review the command syntax, correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU06E"></span>CFTU06E: unexpected
end of file before new command
Explanation
The end of the file was reached before the start of a new
command (a comment in the file read may not be closed).
Consequence
Immediate shutdown of the communication utility.
Action
Add an end of comment marker (\*/) to the file and then
restart the communication utility.
```

 

```
Error
<span id="CFTU07E"></span>CFTU07E: &Cmd Failed
_ unexpected end of file (comments)
Explanation
The end of the file was reached before the end of the command
(a comment inside the command may not be closed).
Consequence
Immediate shutdown of the communication utility.
Action
Add an end of comment marker (\*/) in the command and then
restart the communication utility.
```

 

```
Error
<span id="CFTU08E"></span>CFTU08E: &Cmd Failed
_ missing parenthesis
Explanation
An opening or closing parenthesis is missing in the command
syntax.
Consequence
Immediate shutdown of the communication utility.
Action
Review the command syntax, correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU09E"></span>CFTU09E: &Cmd Failed
_ command size too large
Explanation
The length of the command name is greater than 8.
Consequence
Immediate shutdown of the communication utility.
Action
Check the command syntax, correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU10E"></span>CFTU10E: &Cmd Failed
_ unknown command
Explanation
The command is unknown.
Consequence
Immediate shutdown of the communication utility.
Action
Check the [command syntax](../../../c_intro_userinterfaces/command_summary) in the {{< TransferCFT/componentshortname >}} Online documentation.
Correct the error and restart the communication utility.
Check the command syntax in the {{< TransferCFT/componentshortname >}} Online documentation.
Correct the error and restart the communication utility.
```

 

```
Error
<span id="CFTU11E"></span>CFTU11E: &Cmd Failed
_ keyword &Keyw too large
Explanation
The length of the &Keyw keyword is greater than 8.
Consequence
Immediate shutdown of the communication utility.
Action
Check the description of this parameter in the Transfer
CFT [parameter index](../../../c_intro_userinterfaces/command_summary/parameter_intro), correct the error and then restart the communication
utility.
Check the description of this parameter in the Transfer
CFT parameter index, correct the error and then restart the communication
utility.
```

 

```
Error
<span id="CFTU12E"></span>CFTU12E: &Cmd Failed
_ illegal separator for keyword &Keyw
Explanation
A parameter separator in the &Cmd command is invalid.
Consequence
Immediate shutdown of the communication utility.
Action
Check the [command syntax](../../../c_intro_userinterfaces/command_summary) being sure that the separator is a comma. Correct the error and then restart the communication utility.
Check the command syntax being sure that the separator is a comma. Correct the error and then restart the communication utility.
```

 

```
Error
<span id="CFTU13E"></span>CFTU13E: &Cmd Failed_missing
quote
Explanation
A closing quote (') is missing in the value assigned to
a command parameter.
Consequence
Immediate shutdown of the communication utility.
Action
Check the invalid parameter; correct the error and then
restart the communication utility.
```

 

```
Error
<span id="CFTU14E"></span>CFTU14E: &Cmd Failed
_ too many keywords
Explanation
There are too many keywords for this command.
Consequence
Immediate shutdown of the communication utility.
Action
Check the [command syntax](../../../c_intro_userinterfaces/command_summary). Correct the error and then restart
the communication utility.
Check the command syntax. Correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU15E"></span>CFTU15E: &Cmd Failed
_ keyword &Keyw unknown or duplicate
Explanation
The &Keyw keyword is unknown or appears twice in the
command.
Consequence
Immediate shutdown of the communication utility.
Action
Check the [command syntax](../../../c_intro_userinterfaces/command_summary). Correct the error and then restart
the communication utility.
Check the command syntax. Correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU16E"></span>CFTU16E: &Cmd Failed
_ keyword &Keyw missing
Explanation
The &Keyw keyword, which is mandatory for the command,
is missing.
Consequence
Immediate shutdown of the communication utility.
Action
Check the command syntax, correct the error and then restart
the communication utility.
```

 

```
Error
<span id="CFTU17E"></span>CFTU17E: &Cmd Failed
_ keyword &Keyw value out of bounds
Explanation
The &Keyw keyword of the &Cmd command is numeric
and its value has exceeded the authorized limits.
Consequence
Immediate shutdown of the communication utility.
Action
Check the possible values for this parameter, correct the
error and then restart the communication utility.
```

 

```
Error
<span id="CFTU18E"></span>CFTU18E: &Cmd Failed
_ invalid value for keyword &Keyw
Explanation
The value of the &Keyw keyword of the &Cmd command
is not authorized (numeric value for an alphabetic parameter for example).
Consequence
Immediate shutdown of the communication utility.
Action
Check the possible values for this [parameter](../../../c_intro_userinterfaces/command_summary/parameter_intro). Correct the
error and then restart the communication utility.
Check the possible values for this parameter. Correct the
error and then restart the communication utility.
```

 

```
Error
<span id="CFTU19E"></span>CFTU19E: CFTDEST Failed
_ keywords FNAME and &str are mutually exclusive
Explanation
If &str=PART
The components of a broadcast list can either be described
within the command (PART = parameter) or in an external file (FNAME =
parameter). These two parameters are mutually exclusive.
If &str=IDF
The IDENTIFIERS authorized in the CFTAUTH command can either
be described within the command (IDF = parameter) or in an external file
(FNAME = parameter). These two parameters are mutually exclusive.
```

 

```
Error
<span id="CFTU20I"></span>CFTU20I: &str
Explanation
CFTUTIL command interpreter information messages.
The &str is self-explanatory and can be of several
types:

-   Execution header: Information messages indicating the product,
    release, copyright and execution start date and time
-   Execution report: Information messages indicating the number
    of commands interpreted, the number of errors detected and the execution
    end date and time
-   Dynamic modification of a {{< TransferCFT/componentshortname >}} partner state: Part
    = &part : &str1

The ACT or INACT command has been executed correctly (&str1
indicates the change of state for the &part partner: initial state
-> final state). There are four possible states for
a partner:

-   ACTIVEBOTH: Partner
    active in both modes (requester and server)
-   NOACTIVE:
    Partner inactive in both modes
-   ACTIVEREQ:
    Partner active in the requester mode
-   ACTIVESERV:
    Partner active in the server mode

```

 

```
Error
<span id="CFTU24W"></span>CFTU24W : &Cmd _
Warning (&str)
Explanation
A CFTUTIL command was correctly interpreted but no information
was given; the &str field specifies the reason.
Example: a CFTUTIL LISTCAT command on an empty Transfer
CFT catalog causes the following message to be displayed:
<span id="CFTU24W1"></span>CFTU24W : LISTCAT Warning (no record
found). 
```

 

```
Error
<span id="CFTU26E"></span>CFTU26E : &Cmd _
Error (&str)
Explanation
When executing the command, an error was detected. The
&str field can be set to one of the following values. Note that the
following list is not exhaustive, as the &str field is relatively self-explanatory:

-   Parameter file opening error: Execution of the &Cmd command
    (LISTPARM for example) resulted in an error when opening the parameter
    file.
-   Partners file opening error: Execution of the &Cmd command
    (LISTPART for example) resulted in an error when opening the partner file.
-   Catalog file opening error: Execution of the &Cmd command
    (LISTCAT for example) resulted in an error when opening the catalog file.
-   Media communication file opening error: Execution of the &Cmd
    command (LISTCOM for example) resulted in an error when opening the communication
    file.
-   File creation error: An error was detected when creating and
    formatting the {{< TransferCFT/componentshortname >}} internal datafile  (CFTUTIL CFTFILE TYPE=CAT/LOG/PARM/PART/
    command).
-   File delete error: An error was detected when executing a request
    to delete a {{< TransferCFT/componentshortname >}} internal datafile (CFTUTIL CFTFILE TYPE= ,MODE=DELETE
    command).
-   Output file creating error cs=&scs: Execution of the &Cmd
    command (COPYFILE for example) resulted in an error when creating the
    output file.
-   Input file opening error cs=&scs: Execution of the &Cmd
    command (COPYFILE for example) resulted in an error when opening the input
    file.
-   &id: Partner record already exists: Command execution, e.g. writing information to the {{< TransferCFT/componentshortname >}} partner file, resulted in
    an attempt to add a record that already existed in the file (the &Cmd
    command requested is designated by &Id).
-   &id: Partner record &str error (&str=writing/reading/selecting):
    Command execution resulted in a write/read/article selection error
    in the file (the &Cmd command requested is designated by &Id).
-   &id: Parameter record already exists: Command
    execution, writing information to the {{< TransferCFT/componentshortname >}} parameter file, resulted in
    an attempt to add a record that already existed in the file (&Id being
    the command identifier).
-   &id: Invalid value for NRPART paramete:r Executing the CFTPART
    command, writing information to the {{< TransferCFT/componentshortname >}} partner file, resulted
    in an attempt to add a record that already existed in the file (&Id
    being the CFTPART command identifier). In this case, the NRPART parameter
    is already assigned to an existing CFTPART command.
-   &id: Non bijective table: The conversion table specified
    in the file referenced by the CFTXLATE DIRECT=BOTH command is not bijective
    (&Id being the command identifier). Check that the conversion table
    specified is bijective or create one command for each transfer direction
    (DIRECT=SEND or DIRECT=RECV).
-   No partner found: A partner activation or deactivation command
    (ACT or INACT) resulted in an error. The identifier indicated (ACT ID=&Part)
    does not correspond to an existing partner identifier (CFTPART ID=&Part).
-   Media communication is full: A transfer command (SEND or RECV)
    could not be written to the {{< TransferCFT/componentshortname >}} communication file. The maximum
    number of requests in the communication file that have not yet been processed
    by the {{< TransferCFT/componentshortname >}} has been reached ([RECNB](../../../c_intro_userinterfaces/command_summary/parameter_intro/recnb) parameter in the CFTFILE
    TYPE=COM command).
-   Incompatible compression parameters: Execution of the COPYFILE
    command resulted in an error when checking the attributes (record length
    or format, compression code or state). <a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
    - Copy files off-line</a>
-   Compression error: Executing the COPYFILE command resulted
    in an error during the compression process. <a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
    - Copy files off-line</a>
-   Decompression error: Executing the [COPYFILE](../../../admin_intro/admin_commands_intro/copyfile_command) command resulted
    in an error during the decompression process. Executing the COPYFILE command resulted
    in an error during the decompression process. <a href="../../../admin_intro/admin_commands_intro/copyfile_command" class="MCXref xref">COPYFILE
    - Copy files off-line</a>
-   &id: command not authorized: The command specified by the
    user is not authorized by the {{< TransferCFT/componentshortname >}} security system (&id being
    the command identifier)
-   Habilitation opening error: An error was detected when initializing
    the {{< TransferCFT/componentshortname >}} security system; a file required by the system could
    not be opened correctly. Check that the initialization file exists and
    is valid (contains the operating rules and indirections pointing to the
    object and action dictionaries) and ensure that the security system dictionary
    files exist.
-   Create channel failed: An error was detected when creating the {{< TransferCFT/componentshortname >}} synchronous communication media. Check that you have enough memory.
-   Open channel failed: An error was detected when opening the {{< TransferCFT/componentshortname >}} synchronous communication media. Check that the synchronous communication process is launched.
-   Channel read error: An error was detected when reading the {{< TransferCFT/componentshortname >}} synchronous communication media. Check that the synchronous communication process is launched.
-   Channel write error: An error was detected when writing in the {{< TransferCFT/componentshortname >}} synchronous communication media. Check that the synchronous communication process is launched.
-   Close channel failed: An error was detected when closing the {{< TransferCFT/componentshortname >}} synchronous communication media. Check that the communication media is not already closed.

Consequence
The command is ignored.
Action
Check the parameter settings, analyze the &scs code
if it is set and, if necessary, inform Product Support.
```

 

```
Error
<span id="CFTU30E"></span>CFTU30E : &Cmd Failed
_ Unable to create file &Fname
Explanation
Execution of the &Cmd command resulted in an error
during the file create process.
Example: redirection of CFTUTIL information messages to
an invalid report file (CONFIG TYPE=OUTPUT,FNAME=&Fname command).
Consequence
The command is ignored.
Action
Check the validity of the file name and, if necessary,
inform Product Support.
```
