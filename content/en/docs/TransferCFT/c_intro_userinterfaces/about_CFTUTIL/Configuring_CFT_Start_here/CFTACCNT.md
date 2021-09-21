{
    "title": "CFTACCNT - Accounting records transfer",
    "linkTitle": "CFTACCNT - Accounting records transfer",
    "weight": "300"
}# <span id="kanchor46"></span><span id="CFTACCNT"></span>Accounting records - CFTACCNT

<span id="About_CFTACCNT"></span>This page describes the <span id="kanchor47"></span>CFTACCNT command.

Use this command to define the recording mode of the statistical data
concerning correctly terminated transfers (T or X state).

Two recording modes are available:

-   Recording data
    in Transfer CFT files. When the primary file is full, Transfer CFT
    switches to an alternate file. This mode is available on all operating
    systems.
-   Recording data
    in the files of the operating system accounting utility.

To activate
the statistical mode, you must also configure the [CFTPARM](../../../web_copilot_ui/conf_intro/cftparm)
object.

Related
topics

-   Object concepts
    [How to define transfer
    accounting records](../../../../admin_intro/admin_config_commands/cftaccnt_concepts)

## Parameter descriptions

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
      </tr>
   </thead>
      <tr>
         <td>
            <p>ID </p>
         </td>
         <td>
            <p>Identifier of the CFTACCNT command.</p>
         </td>
      </tr>
      <tr>
         <td>MODE         </td>
         <td>
            <p>Select to perform one of the following:</p>
            <ul>
               <li>CREATE               </li>
               <li>REPLACE               </li>
               <li>DELETE               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/type">TYPE</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Defines the accounting type.</p>
            <ul>
               <li>FILE: 
 statistical data is recorded in the Transfer CFT files described by the 
 FNAME and AFNAME parameters.               </li>
               <li>SYST: 
 statistical data is recorded in a "system" file, through an 
 interface with the system accounting utility. If TYPE=SYST then you must define ACCID.               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/accid">ACCID</a> 
    </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Only used if TYPE=SYST 
 Accounting system file identifier records. </p>
         </td>
      </tr>
      <tr>
         <td>COMMENT         </td>
         <td>          </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p>LANGUAGE </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Programming language of the application using the statistical 
 data recorded.</p>
            <ul>
               <li>COBOL               </li>
               <li>C               </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/fname">FNAME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the statistical file.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/afname">AFNAME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the alternate statistical file.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/maxrec">MAXREC</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Statistical file maximum number of records.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/exec">EXEC</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the procedure to be executed when Transfer CFT 
 switches to the other statistical file</p>
            <p>(SWITCH).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/switch">SWITCH</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Time at which Transfer CFT automatically switches 
 to the alternate statistical file.</p>
            <p>When this parameter is not defined, Transfer CFT switches 
 statistical files daily at midnight.</p>
         </td>
      </tr>
</table>

## Examples

TYPE = FILE

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTACCNT</p>
            <p> ID = ACCNT,</p>
            <p> LANGUAGE = C,</p>
            <p> FNAME = &lt;filename1&gt;,</p>
            <p> AFNAME = &lt;filename2&gt;,</p>
            <p> MAXREC = 1000,</p>
            <p> EXEC = &lt;filename3&gt;</p>
         </td>
      </tr>
   </tbody>
</table>

This command defines the recording of statistical data concerning transfers
in files specific to Transfer CFT. It designates the statistical and alternate
statistical files (FNAME and AFNAME parameters). Data is recorded in these
files for use by an application program written in C language.

File switching takes place manually (SWITCH command) or when the number
of statistical records equals 1000. The procedure initiated at the time
switching occurs is located in the file designated by the EXEC parameter.

TYPE = SYST

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTACCNT</p>
            <p>ID = ACCNT,</p>
            <p>TYPE = SYST,</p>
            <p>ACCID = n       z/OS</p>
         </td>
      </tr>
   </tbody>
</table>

This command defines the recording of statistical data
concerning transfers in operating system accounting utility files, using
an identifier indicated by the ACCID parameter, for the systems designated.