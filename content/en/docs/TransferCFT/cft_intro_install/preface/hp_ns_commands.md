{
    "title": "Transfer CFT commands",
    "linkTitle": "Command usage",
    "weight": "200"
}This chapter describes how to use Transfer CFT commands in a Tandem/Guardian environment.

## About the commands

Transfer CFT offers a set of commands which can be used interactively or within procedures in your Guardian environment.

### Prerequisites

Prior to executing Transfer CFT commands, you must install them. If you have not already done so, perform the task as described in [Install the Guardian specific files](#).

You cannot use Transfer CFT Guardian 2.3.2 CFTUTIL commands with Transfer CFT 3.9.

### Available commands

Three types of commands are available in the installed volume.&lt;subvolume>IX:

-   CFT: management commands to control the Transfer CFT product
-   CFTUTIL: the command line interface for Transfer CFT
-   CFTUTLX: the command line interface for Transfer CFT with INLINE parameters
-   PKIUTIL: the command line interface to manage the local PKI
-   PROFILE: customized file for accessing the other commands

A description of these commands is provided in *Transfer CFT 3.9 Users Guide.*

### Launch PROFILE

The PROFILE file updates the PMSEARCHLIST so that it can call Transfer CFT commands from anywhere. It also contains PARAM and DEFINE entries, which are mandatory before using certain Transfer CFT commands such as CFTUTLX.

Before creating a NETBATCH attachment-set, you must call the PROFILE.

### Access CFTUTIL

From the native command window enter the following to start, for example, CFTUTIL:

Example

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>$ YOURCO HOME &gt; volume $DATA14.CFT32AIX</p>
            <p>$DATA14 CFT32AIX 1&gt; <strong>CFTUTIL</strong></p>         </td>
      </tr>
   </tbody>
</table>

### Command structure

Transfer CFT Guardian commands, other than CFTUTLX, are comprised of TACL macros (Tandem Advanced Command Language), which call their OSS counterparts. By doing so, these commands offer the same level of functionality in both OSS and Guardian environments.

CFTUTLX is a Guardian binary that handles the INLINE mode and calls the OSS CFTUTIL. To do so, it creates one or two temporary files in the TACL DEFAULTS. Please ensure that the DEFAULTS point to a location where CFTUTLX can create and delete its temporary files.

## Using commands

### Run a command

Executing a command is done by simply typing its name at the command prompt or calling it in a procedure.

**Example**

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>$SAS51 FORD36IX 5&gt; CFTUTIL about</p>
            <p>CFTU20I</p>
            <p>CFTU20I CFT/V3/UHPNONSTOP H06</p>
            <p>CFTU20I Version 3.6 SP0 P0 20200330</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2020</p>
            <p>CFTU20I ====&gt; Starting Session on 2020/04/08 Time is 06:48:40</p>
            <p>CFTU20I Parameters file :/home/axway/farid/Dev/CFT36/runtime/data/cftparm</p>
            <p>CFTU20I Partners file :/home/axway/farid/Dev/CFT36/runtime/data/cftpart</p>
            <p>CFTU20I Catalog file :/home/axway/farid/Dev/CFT36/runtime/data/cftcata</p>
            <p>CFTU20I</p>
            <p>Product information :</p>
            <p>* product = AMPLIFY Transfer CFT</p>
            <p>* version = 3.6</p>
            <p>* level =</p>
            <p>* upgrade = 12795000</p>
            <p>* target = hp_nonstop_oss-ia64-32</p>
            <p>Host information :</p>
            <p>* hostname = NSBLDE4</p>
            <p>* sysname = NONSTOP_KERNEL</p>
            <p>* version = 23</p>
            <p>* release = J06</p>
            <p>* model = B</p>
            <p>* cpuid = XXXXXXXXXXX</p>
            <p>License key information :</p>
            <p>* idparm = IDPARM0</p>
            <p>[…]</p>
            <p>CFTU20I Ending Session on 2020/04/08 Time is 06:48:40</p>
            <p>CFTU20I Session active for 0:00:00</p>         </td>
      </tr>
   </tbody>
</table>

### Redirect the command output

There are two ways to redirect Transfer CFT Guardian command output.

#### Redirect output to an OSS file

This is done by using the standard Unix redirection symbol “>”.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>$DATA14 CFT36B 16&gt; CFTUTIL about &gt; /home/axway/user1/cftout.txt         </td>
      </tr>
   </tbody>
</table>

This generates a type 180 OSS unstructured file.

#### Redirect output to a Guardian EDIT file

You must define a TACL variable before running the command. This variable contains the name of the file used to receive the output of the command. Additionally, the variable name depends on the command.

The following table gives the correspondences between the commands and the variables to use:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Command</th>
         <th>Variable</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>CFT         </td>
         <td>CFT^OUT         </td>
      </tr>
      <tr class="even">
         <td>CFTUTIL         </td>
         <td>CFT^UTLOUT         </td>
      </tr>
      <tr class="odd">
         <td>PKIUTIL         </td>
         <td>PKI^UTLOUT         </td>
      </tr>
   </tbody>
</table>

This generates a type 101 Guardian unstructured file.

**Example**

-   In the following example, the variable “CFT^UTLOUT” is set before using CFTUTIL.
-   The command is launched.
-   The content of the file is then listed, and the variable is unset.

<table data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td>            <p>$SAS51 FORD36IX 3&gt; push CFT^UTLOUT</p>
            <p>$SAS51 FORD36IX 4&gt; set variable CFT^UTLOUT $SAS51.FORD36UD.CFTUTL</p>
            <p>$SAS51 FORD36IX 5&gt; CFTUTIL about</p>
            <p>BACKUP PROCESS CREATED IN CPU 3</p>
            <p>$SAS51 FORD36IX 7&gt; fileinfo $SAS51.FORD36UD.*</p>
            <p>$SAS51.FORD36UD</p>
            <p>CODE EOF LAST MODIFIED OWNER RWEP PExt SExt</p>
            <p>CFTUTL 101 2048 08APR2020 7:19 168,13 NONO 14 42</p>
            <p>$SAS51 FORD36IX 8&gt; fup copy FORD36UD.CFTUTL</p>
            <p>CFTU20I</p>
            <p>CFTU20I CFT/V3/UHPNONSTOP H06</p>
            <p>CFTU20I Version 3.6 SP0 P0 20200330</p>
            <p>CFTU20I (C) Copyright AXWAY 1989-2020</p>
            <p>CFTU20I ====&gt; Starting Session on 2020/04/08 Time is 07:19:10</p>
            <p>[…]</p>
            <p>* type = DATE</p>
            <p>* expire = 2025/06/10</p>
            <p>* cpuid =</p>
            <p>* hostname = NSBLDE4</p>
            <p>* sysname = hp_nonstop_oss-ia64-32</p>
            <p>* Nb Transfers = Max</p>
            <p>* Nb CPU = Max</p>
            <p>* Nb Partners = Max</p>
            <p>* In/Out Bandwidth = Unlimited</p>
            <p>* In/Out Transfer activation = Unlimited</p>
            <p>* Edition = Advanced</p>
            <p>* Options = ODT WBS SSL XTF FIP ACC BWP CLU SNL CLP</p>
            <p>* XSR</p>
            <p>CFTU00I ABOUT _ Correct ()</p>
            <p>CFTU20I Number of Command(s) 1</p>
            <p>CFTU20I Number of error(s) 0</p>
            <p>CFTU20I Ending Session on 2020/04/08 Time is 07:19:10</p>
            <p>CFTU20I Session active for 0:00:00</p>
            <p>49 RECORDS TRANSFERRED</p>
            <p>$SAS51 FORD36IX 9&gt; pop CFT^UTLOUT</p>         </td>
      </tr>
   </tbody>
</table>

### Tracing command execution

To gather command details, Axway support may ask you to set the CFTUTLX^TRACE^LEVEL parameter for a CFTUTLX command trace.

The CFTUTLX^TRACE^LEVEL values are:

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>Value</th>
         <th>Description</th>
         <th>Temporary CFTUTLX files are deleted</th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd">
         <td>1         </td>
         <td>Generates traces and redirects them to a temporary file.         </td>
         <td>No         </td>
      </tr>
      <tr class="even">
         <td>2         </td>
         <td>Generates traces and redirects them to the standard output.         </td>
         <td>No         </td>
      </tr>
      <tr class="odd">
         <td>3         </td>
         <td>Both 1 and 2 occur.         </td>
         <td>No         </td>
      </tr>
      <tr class="even">
         <td>Any other value or not set         </td>
         <td>Does not generate traces.         </td>
         <td>Yes         </td>
      </tr>
   </tbody>
</table>

Temporary files are generated in the Guardian DEFAULTS location with file names ranging from CTMP0000 to CTMP9999. You must manually purge these files after sending a copy to Axway support.
