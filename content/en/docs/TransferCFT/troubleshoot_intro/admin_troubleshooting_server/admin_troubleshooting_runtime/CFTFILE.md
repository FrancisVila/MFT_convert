{
    "title": "Manually create internal data files",
    "linkTitle": "Manually create internal data files",
    "weight": "410"
}The CFTFILE command is used to create, replace, or delete Transfer CFT
files. These initial files define the most basic parameters for the Transfer
CFT. You can further define the Transfer CFT settings after the initial
start, but Transfer CFT must have this CFTFILE as a minimum
configuration.

You can only create the initial environment in the CFTUTIL command line
interface. You must create all files that are handled by the Transfer
CFT. After creating a basic CFTFILE, you can execute the profile
file, and continue either in command line or use the old Transfer CFT UI Configuration
Wizard.

## About the CFTFILE command

The CFTFILE command affects the following files:

-   PARAMETER - containing
    the Transfer CFT general parameters where TYPE = PARM (or PARAM)
-   PARTNER - containing
    the descriptions of the characteristics of partners where TYPE = PART
-   CATALOG - containing
    the control information associated with transfers where TYPE = CAT
-   STATISTICS - containing
    the information relative to terminated transfers where TYPE = ACCNT
-   LOG - used to record
    messages associated with the execution of transfers and CFT operations
    where TYPE = LOG
-   COMMUNICATION -
    used to enter transfer requests and Transfer CFT management comm where
    TYPE = COM

To delete a Transfer CFT file, MODE = DELETE, you must declare the parameters
FNAME, the name of the file
to be deleted, and TYPE, the
type of the file to be deleted.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>OS</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IBM i</p></td>
<td><p>The CFTFILE command is incorporated in Transfer CFT IBM i
Manager. It can, however, be activated directly in the log file switching
procedures. See the example supplied in the B_EXECLOG member.</p></td>
</tr>
</tbody>
</table>

You can use the [CFTCATAL](../../../../cft_intro_install/unix_install_start_here/run_first_time_ux/use_cft_utilities) utility to resize the catalog. In a multi-node environment, this action resizes all nodes.

Use the CFTFILE command to create (MODE = CREATE) empty or delete (MODE
= DELETE) Transfer CFT files.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize">FBLKSIZE</a></p>
<p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize">see table</a></p></td>
<td><p>Defines the block size of the file to be created (in bytes).</p>
<p>Depends on the TYPE/OS</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname">FNAME</a> </p></td>
<td><p>Name of the file the command applies to.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace">FSPACE</a></p>
<p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace">see
table</a></p></td>
<td><p>Primary allocation of the file to be created, expressed
in K bytes (1024).</p>
<p>Depends on the TYPE/OS</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspacex">FSPACEX</a></p>
<p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspacex">see table</a></p></td>
<td><p>Secondary allocation of the file to be created, expressed
in K bytes (1024).</p>
<p> </p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/habfname">HABFNAME</a></p></td>
<td><p>Name of the security system initialization file.</p></td>
</tr>
<tr class="even">
<td><p><a href="lock.htm">LOCK</a></p>
<p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a>
= COM</p></td>
<td><p>Name of the lock file created in parallel with the communication
file and used to manage file access conflicts.</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode">MODE</a></p></td>
<td><p>Action requested on the file.</p></td>
</tr>
<tr class="even">
<td><p><a href="node.htm">NODE</a></p></td>
<td><p>Node identifier.</p>
<p>Available when TYPE=CAT</p></td>
</tr>
<tr class="odd">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/recnb">RECNB</a> </p>
<p>TYPE = {COM | CAT}</p></td>
<td><p>Number of records in the file.</p></td>
</tr>
<tr class="even">
<td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> =
{ACCNT | CAT | COM | LOG | PARM (PARMA) | PART}</p></td>
<td><p>Type of file concerned by the command.</p>
<p>When TYPE = CAT, COM, PARM or PART, you can use the HABFNAME
parameter for security.</p></td>
</tr>
</tbody>
</table>

**Syntax**

#### CFTFILE { PARM | PARAM | PART }

[TYPE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= { PARM | PARAM | PART }

[FNAME](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname)
= filename  

\[ [HABFNAME](../../../../c_intro_userinterfaces/command_summary/parameter_intro/habfname)
= filename \]

\[ [FBLKSIZE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize)
= { 0
|n } \]

\[ [FSPACE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace)
= n \]

\[ [FSPACEX](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspacex)
= n \]

\[ [MODE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode)
= { CREATE
| REPLACE | DELETE | ERASE } \]

 

#### CFTFILE { CAT | COM }

[TYPE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= {  CAT
| COM }

[FNAME](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname)
= filename

\[ [RECNB](../../../../c_intro_userinterfaces/command_summary/parameter_intro/recnb)
= n \]

\[ [FBLKSIZE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize)
= { 0
|n } \]

\[ [FSPACE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace)
= { 0
| n } \]

\[ [FSPACEX](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspacex)
=  { 0
| n } \]

\[ [HABFNAME](../../../../c_intro_userinterfaces/command_summary/parameter_intro/habfname)
= filename \]

\[ [MODE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode)
= { CREATE
| REPLACE | DELETE | ERASE} \]

\[ [NODE](node.htm) = { n | <u>0</u>...16} \] available only when TYPE=CAT

 

#### CFTFILE { ACCNT | LOG }

[TYPE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/type)
= { ACCNT | LOG }

[FNAME](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fname)
= filename

\[ [FBLKSIZE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fblksize)
= 0
| n \]

\[ [FSPACE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspace)
= 0
|n \]

\[ [FSPACEX](../../../../c_intro_userinterfaces/command_summary/parameter_intro/fspacex)
= 0
|n \]

\[ [MODE](../../../../c_intro_userinterfaces/command_summary/parameter_intro/mode)
= { CREATE
| REPLACE | DELETE | ERASE } \]

Example

The following command creates a parameter file.

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td>CFTFILE    TYPE
= PARM,<br />
MODE = CREATE,<br />
FNAME = filename<br />
</td>
</tr>
</tbody>
</table>
