{
    "title": "Transfer CFT commands",
    "linkTitle": "Command usage",
    "weight": "200"
}This chapter describes how to use Transfer CFT commands in a Tandem/Guardian environment.

## About the commands

Transfer CFT offers a set of commands which can be used interactively or within procedures in your Guardian environment.

### Prerequisites

Prior to executing Transfer CFT commands, you must install them. If you have not already done so, perform the task as described in <a href="#Install" class="MCXref xref">Install the Guardian specific files</a>.

You cannot use Transfer CFT Guardian 2.3.2 CFTUTIL commands with Transfer CFT .

### Available commands

Three types of commands are available in the installed volume.&lt;subvolume>IX:

-   CFT: management commands to control the Transfer CFT product
-   CFTUTIL: the command line interface for Transfer CFT
-   CFTUTLX: the command line interface for Transfer CFT with INLINE parameters
-   PKIUTIL: the command line interface to manage the local PKI
-   PROFILE: customized file for accessing the other commands

A description of these commands is provided in *Transfer CFT Users Guide.*

### Launch PROFILE

The PROFILE file updates the PMSEARCHLIST so that it can call Transfer CFT commands from anywhere. It also contains PARAM and DEFINE entries, which are mandatory before using certain Transfer CFT commands such as CFTUTLX.

Before creating a NETBATCH attachment-set, you must call the PROFILE.

### Access CFTUTIL

From the native command window enter the following to start, for example, CFTUTIL:

Example

### Command structure

Transfer CFT Guardian commands, other than CFTUTLX, are comprised of TACL macros (Tandem Advanced Command Language), which call their OSS counterparts. By doing so, these commands offer the same level of functionality in both OSS and Guardian environments.

CFTUTLX is a Guardian binary that handles the INLINE mode and calls the OSS CFTUTIL. To do so, it creates one or two temporary files in the TACL DEFAULTS. Please ensure that the DEFAULTS point to a location where CFTUTLX can create and delete its temporary files.

## Using commands

### Run a command

Executing a command is done by simply typing its name at the command prompt or calling it in a procedure.

**Example**

### Redirect the command output

There are two ways to redirect Transfer CFT Guardian command output.

#### Redirect output to an OSS file

This is done by using the standard Unix redirection symbol “>”.

This generates a type 180 OSS unstructured file.

#### Redirect output to a Guardian EDIT file

You must define a TACL variable before running the command. This variable contains the name of the file used to receive the output of the command. Additionally, the variable name depends on the command.

The following table gives the correspondences between the commands and the variables to use:


| Command  | Variable  |
| --- | --- |
| CFT  | CFT^OUT  |
| CFTUTIL  | CFT^UTLOUT  |
| PKIUTIL  | PKI^UTLOUT  |


This generates a type 101 Guardian unstructured file.

**Example**

-   In the following example, the variable “CFT^UTLOUT” is set before using CFTUTIL.
-   The command is launched.
-   The content of the file is then listed, and the variable is unset.

### Tracing command execution

To gather command details, Axway support may ask you to set the `CFTUTLX^TRACE^LEVEL` parameter for a `CFTUTLX `command trace.

The `CFTUTLX^TRACE^LEVEL` values are:


| Value  | Description  | Temporary CFTUTLX files are deleted  |
| --- | --- | --- |
| 1  | Generates traces and redirects them to a temporary file.  | No  |
| 2  | Generates traces and redirects them to the standard output.  | No  |
| 3  | Both 1 and 2 occur.  | No  |
| Any other value or not set  | Does not generate traces.  | Yes  |


Temporary files are generated in the Guardian DEFAULTS location with file names ranging from CTMP0000 to CTMP9999. You must manually purge these files after sending a copy to Axway support.
