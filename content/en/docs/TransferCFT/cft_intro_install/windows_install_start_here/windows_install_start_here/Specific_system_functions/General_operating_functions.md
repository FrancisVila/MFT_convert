{
    "title": "General  operating functions",
    "linkTitle": "General operating functions",
    "weight": "270"
}-   [Logical
    file names](#Logical_file_names)
-   [Using
    a definition file](#Using%20a%20definition%20file)

## <span id="Logical_file_names"></span>Logical file names

Transfer CFT can use logical file names in order to designate the physical
files and, if necessary, to state the characteristics of these files.
There are two methods of doing this:

-   Using the operating
    system environment
-   Using a file to
    describe the logical names

Users can choose one or other of these two methods. For the same Transfer
CFT, certain logical names can be described in the operating system and
other in the logical names description file. A certain number of logical
names are defined as standard in Transfer CFT. This is the case for Transfer
CFT working files.

Note: The standard definition of
the logical name for a Transfer CFT working file means that regarding
this logical name, there is no prior operation to perform before operating
Transfer CFT.

If not, one of the following three operations needs to be performed
before operating Transfer CFT:

-   The CONFIG command
    of CFTUTIL
-   Sufficient screen
    parameter setting in the Copilot interface
-   Transfer CFT API
    COM command

## Logical working files

Environment variables

The following table lists the logical names of files, and
defines the role.

<table data-cellspacing="0">
   <thead>
      <tr class="header">
         <th>            <p>Working file </p></th>
         <th>            <p>Logical name </p></th>
         <th>            <p>Comment </p></th>
      </tr>
   </thead>
   <tbody>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Parameter </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTPARM </p>         </td>
         <td data-valign="top" width="46%">            <p>Parameter file </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Partner </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTPART </p>         </td>
         <td data-valign="top" width="46%">            <p>Partner file </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Catalogue </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTCATA </p>         </td>
         <td data-valign="top" width="46%">            <p>Catalogue file </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Communication </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTCOM </p>         </td>
         <td data-valign="top" width="46%">            <p>Communication file </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Log </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTLOG</p>         </td>
         <td data-valign="top" width="46%">            <p>Log file </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Log </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTALOG</p>         </td>
         <td data-valign="top" width="46%">            <p>Alternate log file </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Account </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTACCN </p>         </td>
         <td data-valign="top" width="46%">            <p>Statistics file </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Account </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTAACCN </p>         </td>
         <td data-valign="top" width="46%">            <p>Alternate statistics file </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Suffixes (1) </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTSUFX </p>         </td>
         <td data-valign="top" width="46%">            <p>Suffixes file </p>         </td>
      </tr>
      <tr class="even" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Parameter </p>         </td>
         <td data-valign="top" width="26%">            <p>SEC.INI </p>         </td>
         <td data-valign="top" width="46%">            <p>System enabling file </p>         </td>
      </tr>
      <tr class="odd" data-valign="middle">
         <td data-valign="top" width="28%">            <p>Logical names </p>         </td>
         <td data-valign="top" width="26%">            <p>CFTNMLOG </p>         </td>
         <td data-valign="top" width="46%">            <p>Redefinition files </p>         </td>
      </tr>
   </tbody>
</table>

(1): see [Recognizing file types](File_management_functions.htm)

By default of definition for these logical names, the physical names
correspond to the logical names.

Users who do not want to use the physical names of files by default,
must redefine them in the operating environment where CFTMAIN, CFTUTIL,
Transfer CFT Navigator (Copilot) and the Transfer CFT APIs execute. This operation must be performed
BEFORE any Transfer CFT parameters are set.

When settings parameters for Transfer CFT, a user wanting to invoke
a logical file name, must systematically prefix the character string for
the logical name with the "$" symbol.

Example of a logical name statement: fname = $CFTCOM

Using operating system environment variables

Because it is simple and flexible, this is the preferred method and
is used whenever a straightforward correspondence of logical name to physical
name is sufficient.

When making re-definitions of this sort, users can use the environment
variables provided by the various operating systems. Quite clearly, the
redefined names must be legal for the file system used (FAT, NTFS, FAT32).

Examples of the using operating system environment variables:

SET CFTPARM=D:\\MY\_REP1\\PARAMET  
SET CFTPART=D:\\MY\_REP2\\PARTENAI  
SET CFTCATA=D:\\MY\_REP3\\CATALOG  
SET CFTCOM=D:\\MY\_REP4\\COM.CFT  
SET CFTLOG=D:\\MY\_REP5\\LOG.JNL  
SET CFTALOG=D:\\MY\_REP6\\ALOG.JNL  
SET CFTACCNT=D:\\MY\_REP7\\ACCOUNT  
SET CFTAACCN=D:\\MY\_REP8\\AACCOUNT  
SET CFTSUFX=D:\\MY\_REP9\\SUFFIXE  
SET CFTNMLOG=D:\\MY\_REP\_10\\NOMSLOG.SYS

Do not use suffixes for the physical
parameter and partner file names, except in the case where Transfer CFT
is operating in Client/Server with a UNIX Transfer CFT.

<table data-cellpadding="0" data-cellspacing="0">
   <tbody>
      <tr class="odd">
         <td data-valign="top">         </td>
         <td data-valign="top"><span><strong>Note</strong></span>         </td>
         <td data-mc-autonum="&lt;b&gt;Note&lt;/b&gt;" data-valign="top">The CFTFILE command in CFTUTIL does not take into account any
environment variables set and corresponding to the Transfer CFT logical
file names. You can overcome this problem in a batch file by using
certain operating system functions.         </td>
      </tr>
   </tbody>
</table>

Example

The following command sets the CFTPARM environment variable
to the value of TEST:

SET CFTPARM=TEST

The command file to be submitted contains the following line:

CFTUTIL CFTFILE type = param, fname = %CFTPARM%

When this command file is submitted, the operating system substitutes
the string %CFTPARM% with the string TEST. The command submitted
to CFTUTIL is as follows:

CFTFILE type = PARAM, fname = TEST

## <span id="Using a definition file"></span>Using a definition file

Use this method when you want to associate a logical name
with a physical name and file attributes. Since the content of
these definitions is complex, refer to the samples
supplied with the product.

The logical name of the file containing these definitions is CFTNMLOG.

For Transfer CFT Windows the only case where the use of
a logical name definition file is necessary is when you use the extraction
tool for standard traces (ATM tool).

Example

The following line provides an example of the content of a line in the definition
file.

TRCATM=CFTTRACE.BIN O=C,F=F,R=1024,T=B

In this example, the logical name TRCATM is given as the exit
file in parameter to the Transfer CFT trace extraction tool. The physical
name CFTTRACE.BIN corresponds to the logical name TRCATM and the following
characteristics: contiguous file organization (O=C), fixed format (F=F),
record length 1024 characters (R=1024) and file is binary type (T+B).

### Change of name or path of definition file

Environment variable

#### CFTNMLOG

By default the definition file is CFTNMLOG and it is located
in the working directory.

To change the name and/or path of the definition file
use the CFTNMLOG environment variable.
