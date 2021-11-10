{
    "title": "CFTTELL - Retrieve system information",
    "linkTitle": "CFTTELL - Retrieve system information",
    "weight": "260"
}{
"title": "Manually create internal data files",
"linkTitle": "CFTFILE - Create database files",
"weight": "250"
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
- PARAMETER - containing
the Transfer CFT general parameters where TYPE = PARM (or PARAM)
- PARTNER - containing
the descriptions of the characteristics of partners where TYPE = PART
- CATALOG - containing
the control information associated with transfers where TYPE = CAT
- STATISTICS - containing
the information relative to terminated transfers where TYPE = ACCNT
- LOG - used to record
messages associated with the execution of transfers and CFT operations
where TYPE = LOG
- COMMUNICATION -
used to enter transfer requests and Transfer CFT management comm where
TYPE = COM
To delete a Transfer CFT file, MODE = DELETE, you must declare the parameters
FNAME, the name of the file
to be deleted, and TYPE, the
type of the file to be deleted.

<table>
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">OS         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p>IBM i</p>         </td>
         <td><p>The CFTFILE command is incorporated in Transfer CFT IBM i
Manager. It can, however, be activated directly in the log file switching
procedures. See the example supplied in the B_EXECLOG member.</p>         </td>
      </tr>
   </tbody>
</table>

You can use the \[CFTCATAL\](../../../cft\_intro\_install/unix\_install\_start\_here/run\_first\_time\_ux/use\_cft\_utilities) utility to resize the catalog. In a multi-node environment, this action resizes all nodes.
Use the CFTFILE command to create (MODE = CREATE) empty or delete (MODE
= DELETE) Transfer CFT files.

<table>
         
         
         
   
   <thead>
      <tr>
<th class="TableStyle-SynchTableStyle_interop-HeadE-Column1-Header1">Parameter         </th>
<th class="TableStyle-SynchTableStyle_interop-HeadD-Column1-Header1">Description         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="">FBLKSIZE</a></p>
<p><a href="">see table</a></p>         </td>
         <td><p>Defines the block size of the file to be created (in bytes).</p>
<p>Depends on the TYPE/OS</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">FNAME</a> </p>         </td>
         <td><p>Name of the file the command applies to.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">FSPACE</a></p>
<p><a href="">see
table</a></p>         </td>
         <td><p>Primary allocation of the file to be created, expressed
in K bytes (1024).</p>
<p>Depends on the TYPE/OS</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">FSPACEX</a></p>
<p><a href="">see table</a></p>         </td>
         <td><p>Secondary allocation of the file to be created, expressed
in K bytes (1024).</p>
<p> </p>         </td>
      </tr>
      <tr>
         <td><p><a href="">HABFNAME</a></p>         </td>
         <td><p>Name of the security system initialization file.</p>         </td>
      </tr>
      <tr>
         <td><p>LOCK</p>
<p><a href="">TYPE</a>
= COM</p>         </td>
         <td><p>Name of the lock file created in parallel with the communication
file and used to manage file access conflicts.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">MODE</a></p>         </td>
         <td><p>Action requested on the file.</p>         </td>
      </tr>
      <tr>
         <td><p>NODE</p>         </td>
         <td><p>Node identifier.</p>
<p>Available when TYPE=CAT</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">RECNB</a> </p>
<p>TYPE = {COM | CAT}</p>         </td>
         <td><p>Number of records in the file.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="">TYPE</a> =
{ACCNT | CAT | COM | LOG | PARM (PARMA) | PART}</p>         </td>
         <td><p>Type of file concerned by the command.</p>
<p>When TYPE = CAT, COM, PARM or PART, you can use the HABFNAME
parameter for security.</p>         </td>
      </tr>
   </tbody>
</table>

\*\*Syntax\*\*
#### CFTFILE { PARM | PARAM | PART }
\[TYPE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/type)
= { PARM | PARAM | PART }
\[FNAME\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fname)
= filename  
\\\[ \[HABFNAME\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/habfname)
= filename \\\]
\\\[ \[FBLKSIZE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
|n } \\\]
\\\[ \[FSPACE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspace)
= n \\\]
\\\[ \[FSPACEX\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspacex)
= n \\\]
\\\[ \[MODE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE | ERASE } \\\]
 
#### CFTFILE { CAT | COM }
\[TYPE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/type)
= {  CAT
| COM }
\[FNAME\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fname)
= filename
\\\[ \[RECNB\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/recnb)
= n \\\]
\\\[ \[FBLKSIZE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fblksize)
= { <span style="text-decoration: underline;">0</span>
|n } \\\]
\\\[ \[FSPACE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspace)
= { <span style="text-decoration: underline;">0</span>
| n } \\\]
\\\[ \[FSPACEX\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspacex)
=  { <span style="text-decoration: underline;">0</span>
| n } \\\]
\\\[ \[HABFNAME\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/habfname)
= filename \\\]
\\\[ \[MODE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE | ERASE} \\\]
\\\[ NODE = { n | <u>0</u>...16} \\\] available only when TYPE=CAT
 
#### CFTFILE { ACCNT | LOG }
\[TYPE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/type)
= { ACCNT | LOG }
\[FNAME\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fname)
= filename
\\\[ \[FBLKSIZE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fblksize)
= <span style="text-decoration: underline;">0</span>
| n \\\]
\\\[ \[FSPACE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspace)
= <span style="text-decoration: underline;">0</span>
|n \\\]
\\\[ \[FSPACEX\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/fspacex)
= <span style="text-decoration: underline;">0</span>
|n \\\]
\\\[ \[MODE\](../../../c\_intro\_userinterfaces/command\_summary/parameter\_intro/mode)
= { <span style="text-decoration: underline;">CREATE</span>
| REPLACE | DELETE | ERASE } \\\]
Example
The following command creates a parameter file.
CFTFILE    TYPE
= PARM,
MODE = CREATE,
FNAME = filename
