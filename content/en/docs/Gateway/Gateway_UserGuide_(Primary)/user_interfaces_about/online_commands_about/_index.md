{
    "title": "Online commands",
    "linkTitle": "Online commands",
    "weight": "70"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: User Interfaces

[Overview](#Overview)

[Before using the Command Line Interface](#Before)

[Online commands and utilities](#commands)

[Syntax and conventions](#Syntax)

[Return values and error reporting](#Return_msgs)

<span id="Overview"></span>

## Overview

The Command Line Interface is a computer interface in which you enter commands in the form of a string of text characters.

You can manage virtually all <span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span> functions via the set of commands provided for the Command Line Interface.

You can use these commands:

-   In interactive mode from the system prompt of Windows or UNIX systems
-   Via batch mode procedures

You can use online commands to:

-   Start and stop Gateway
-   Manage the following Gateway objects:
    -   Sites
    -   Applications
    -   Models
    -   Diffusion Lists
    -   CGates and CGateGroups
    -   Connections
    -   Connected Users
    -   Transfer Requests
    -   Statistics
    -   Log files
    -   Decision Rules
    -   Rule Tables
    -   Proxies
    -   Virtual File Directories
    -   Network profiles
    -   Security profiles
    -   Certificates
    -   Keys

<span id="Before"></span>

## Before using the Command Line Interface

Before running online commands, set the Gateway environment variables.

Gateway provides a batch file that you can use to set all Gateway variables for your supporting OS:

-   In UNIX environments, execute the <span class="code" style="font-weight: bold;">profile</span> batch file located in the <span class="code">&lt;Gateway installation directory>/run\_time/etc</span> directory.
-   In Windows environments, execute the <span class="code" style="font-weight: bold;">profile.bat</span> batch file located in the <span class="code">&lt;Gateway installation directory>\\run\_time\\etc</span> directory.  
    In Windows environments, when you select <span style="font-weight: bold;">Start > Programs > Axway Software > Axway \[ProjectName\] > Gateway > Command Prompt</span> to open the command console, the environment variables are automatically taken into account.

<span id="commands"></span>

## Online commands and utilities

### Commands

For a complete list of Gateway online commands, refer to [Catalog of online commands](online_commands_catalog).

To locate a command or subcommand from an alphabetical index, refer to [Index of online commands](online_commands_index).

To locate a command or subcommand from a list of command tasks, refer to [Index of tasks](online_commands_task_index).

### Utilities

In addition to commands, Gateway provides the following utilities that you can run from the Command Line Interface.

<table>
         
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Utility</p>         </th>
<th class="HeadE-Column1-Header1"><p>Description</p>         </th>
<th class="HeadD-Column1-Header1"><p>Refer to</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>trncc</p>         </td>
         <td><p>Builds character conversion tables used by Gateway code conversion modules</p>         </td>
         <td><p><a href="../../customizing_gw_about/code_conversion_utilities">Code conversion and file formatting</a></p>         </td>
      </tr>
      <tr>
         <td><p>trnxcode</p>         </td>
         <td><p>Converts the contents of a file into a defined data code</p>         </td>
         <td><p><a href="../../customizing_gw_about/code_conversion_utilities">Code conversion and file formatting</a></p>         </td>
      </tr>
      <tr>
         <td><p>kfmcp</p>         </td>
         <td><p>Maintains and optimizes the Mailbox file via the following actions:</p>
<ul>
<li>Copies Mailbox records from input to output files</li>
<li>Sets or resets the primary and secondary allocation space for the Mailbox file</li>
</ul>         </td>
         <td><p><a href="../../transfers_start_here/monitoring_transfers_start_here/viewing_and_managing_mailbox_contents_cli/maintaining_mailbox">Maintaining the Mailbox (kfmcp command)</a></p>         </td>
      </tr>
      <tr>
         <td><p>pelencpass</p>         </td>
         <td><p>Encrypt a password using the AES 256 algorithm (for example, for PassPort AM/PM, SecureRelay, SWIFTNet HA Database).</p>
<p>Generate an AES 256 encryption key (for example, for exporting/importing Gateway objects).</p>         </td>
         <td><p>See <em>Security guide</em> &gt; <a href="#">Secure Password Management</a> for more information (requires login)</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Syntax"></span>

## Syntax and conventions

### Syntax

The syntax you use to enter commands and utilities varies according to the command or utility concerned. The following table summarizes syntax use.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Command or utility</p>         </th>
<th class="HeadD-Column1-Header1"><p>Syntax</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>peladm</p>
<p>pelbase</p>
<p>pelctl</p>
<p>pelmon</p>
<p>peldsp</p>
<p>secadm</p>
<p>secdsp</p>
<p>vfdadm</p>
<p>vfddsp</p>         </td>
         <td><p>command  subcommand  Parameter list</p>         </td>
      </tr>
      <tr>
         <td><p>pelpur</p>         </td>
         <td><p>command [subcommand] Parameter list</p>         </td>
      </tr>
      <tr>
         <td><p>peltrans</p>         </td>
         <td><p>command  Parameter list</p>         </td>
      </tr>
      <tr>
         <td><p>pelencpass</p>         </td>
         <td><p>command  Parameter list</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">trncc</span> (utility)</p>         </td>
         <td><p>trncc  &lt;infile&gt;</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">trnxcode</span> (utility)</p>         </td>
         <td><p>trnxcode  &lt;codein.codeout&gt;  &lt;infile&gt;  &lt;outfile&gt;</p>         </td>
      </tr>
      <tr>
         <td><p><span class="code" style="font-weight: bold;">kfmcp</span> (utility)</p>         </td>
         <td><p>kfmcp  [infiles]  outfile</p>         </td>
      </tr>
   </tbody>
</table>

### Conventions for entering parameters

A parameters list can be empty, or it can contain one or several items.

Each parameter is identified by a keyword preceded by the minus ("–") character. Typically, a parameter is followed by a value. Certain optional parameters are restricted to the keyword only.

This section explains the syntactic conventions used throughout this documentation for command descriptions and examples.

The same syntax is used for the parameters list and values.

-   Mandatory parameters are enclosed in curly brackets: {  }
-   Optional parameters are enclosed in square brackets: <span class="code">\[  \]</span>
-   Parameter abbreviations appear between parentheses: <span class="code">-param (-p)</span>

#### Parameters without values

Certain parameters take no values. You use these parameters to enable a particular functionality. Parameters without values are always optional.

Example:

\[-trace\_mode (-tm)\]

This parameter, abbreviated to <span class="code" style="font-weight: bold;">–tm</span>, enables protocol trace mode for the specified Site.

Typical command example:

To start a Site with trace mode enabled, enter the following command:

pelctl start\_site  -alias SITEA  -trace\_mode

Alternatively, use the abbreviated parameter notation:

pelctl start\_site  -a SITEA  -tm

#### Parameters with explicit labels

Certain parameters are followed by an explicit label that is a numeric or alphanumeric string. This type of parameter can be mandatory or optional. The label is always mandatory when the parameter keyword is mentioned.

Example:

\[-name (-n)\] Application name

Typical command example:

To delete an Application, enter the following command:

peladm delete\_appli  -name APPLI

Alternatively, use the abbreviated parameter notation:

peladm delete\_appli  -n APPLI

#### Parameters with enumerated values

Enumerated values are a predefined set of values available for a parameter.

A parameter with enumerated values can be mandatory or optional. Any default values are indicated in parentheses.

<span style="font-weight: bold;">Note:</span> Curly brackets enclosed in curly or square brackets indicate that a value is mandatory when the corresponding parameter is explicitly mentioned.

Example:

\[-protocol (-pr) { PEL | ODETTE | PHSE | PHSD | FTP | SMTP | POP3 | SFTP }\]

Typical command example:

To select Remote Sites defined with the PEL protocol, enter the following command:

peldsp select\_site  -pr PEL

IMTPLX01

UXTPLX01

This command selects two Remote Sites.

#### Parameters with a range of numeric values

A parameter with a range of numeric values can be mandatory or optional. The upper and lower limits of the range are separated by dots.

Some of these parameters have default values that are enclosed in parentheses.

Example:

\[-retry\_count\_max (-rc\_max) { 0..(10)..999 }\]

This command specifies the maximum number of retries allowed on a transfer. The optional parameter takes a numeric value from 0 to 999, where the default = 10.

Typical command example:

To update a Site, enter the following command (using the abbreviated parameter notation):

peladm update\_site  -a SITE  -rc\_max 5

<span id="Return_msgs"></span>

## Return values and error reporting

When you enter a command in the Command Line Interface, Gateway can return a message that indicates either the execution result or that an error has occurred. If a response is expected, the command displays the Gateway response in the system output.

A command exit code is provided in an environment variable. This command exit code can have one of the following values:

-   <span style="font-weight: bold;">0</span> - command executed successfully
-   <span style="font-weight: bold;">1</span> - execution error occurred
-   <span style="font-weight: bold;">2</span> - syntax error occurred

This environment variable is platform-dependent. Refer to the platform-specific documentation for more information.

 

The error messages can be one of two types:

-   Execution errors that occurred during command processing
-   Errors resulting from command syntax errors

### Execution errors

Execution errors are displayed in the format:

&lt;command\_name> &lt;subcommand> : &lt;error\_message>

where:

<span class="code">&lt;command\_name></span> indicates the command procedure where the error occurred (for example: <span class="code" style="font-weight: bold;">peladm</span>)

<span class="code">&lt;subcommand></span> indicates the name of the subcommand (for example: <span class="code">create\_site</span>)

<span class="code">&lt;error\_message></span> is the corresponding error text. All possible messages are listed in the file <span class="code">itperr.msg</span>.

#### Example:

peladm update\_site: Record not found.

### Syntax errors

If you make an error in the use of syntax, a message is displayed in the following format:

&lt;Error: description of error>

&lt;Usage: command ? to display help>

where:

<span class="code">Error</span>: description of the error

<span class="code">Usage</span>: displays the syntax to use to display help for the command in question

#### Example:

If you enter the command:

peladm create\_user uuuuuu

the following syntax error message is displayed:

Error: Invalid parameter uuuuuu

Usage: peladm  create\_user ?  to obtain help on command parameters.

The following table contains the possible error messages that you may receive on entering a command.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="HeadE-Column1-Header1"><p>Error type</p>         </th>
<th class="HeadD-Column1-Header1"><p>Text format of displayed message</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>Syntax error messages</p>         </td>
         <td><ul>
<li>Error: Missing value for parameter %s</li>
<li>Error: Invalid parameter %s</li>
<li>Error: Parameter %s too long (char), size must be %d</li>
<li>Error: Parameter %s is mandatory</li>
<li>Error: Parameter %s requires a numeric value</li>
<li>Error: Parameter %s must be greater than or equal to %d</li>
<li>Error: Parameter %s must be less than or equal to %d</li>
<li>Error: Incorrect value for parameter %s</li>
<li>Error: Invalid subcommand %s</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Warning messages</p>         </td>
         <td><ul>
<li>Warning: Parameter %s must be greater than or equal to %d</li>
<li>Warning: Parameter %s must be less than or equal to %d</li>
<li>Warning: Incorrect value for parameter %s</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>Help messages</p>         </td>
         <td><ul>
<li>Usage: [command name] ?  to obtain basic help, ?? for detailed help</li>
<li>Usage: [command name] ?  to obtain help on command parameters</li>
<li>Usage: [command name]</li>
</ul>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Index of online commands](online_commands_index)

[Index of tasks](online_commands_task_index)

[Catalog of online commands](online_commands_catalog)

<a href="displaying_online_help" class="MCXref xref">Displaying online help</a>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
