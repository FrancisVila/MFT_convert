{
    "title": "Log file - CFTLOG",
    "linkTitle": "Log file - CFTLOG",
    "weight": "200"
}Use this command to defines the log file declarations. Transfer CFT
records any significant events that occur during a transfer.

Log parameters are defined in detail in the Parameter index. Click on
a specific parameter for more information.

Related
topics

-   Command syntax
    [CFTLOG](../../../command_summary)
-   Object concepts
    [Log parameters](log_parameter_concepts.htm)

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
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/afname">AFNAME</a> </p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name 
 of the alternate log file.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/content">CONTENT</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>The messages written in the active LOG file are filtered. 
 The possible values are:</p>
            <ul>
               <li>FULL: all the messages 
 are printed out               </li>
               <li>BRIEF: the following 
 messages no longer appear in the LOG                </li>
            </ul>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/exec">EXEC</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the procedure to be executed when switching to 
 the other log file. By default this is rotate.cmd/bat.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/fname">FNAME</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Name of the log file.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/id">ID</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Identifier of the CFTLOG command.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/length">LENGTH</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Size of log file records.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/maxrec">MAXREC</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Number of records written in the log file, from which automatic 
 switching will be performed.</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/mode">MODE</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Action to do in the parameter or partner base. This parameter 
 applies to all commands that affect Transfer CFT bases. </p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/notify">NOTIFY</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Defines the destination 
 of the operator messages selected according to the value of the OPERMSG 
 parameter</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/opermsg">OPERMSG</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Defines the transfer information message categories intended 
 for the operator (all the messages also being written in the log file).</p>
         </td>
      </tr>
      <tr>
         <td colspan="1" rowspan="1">
            <p><a href="../../../command_summary/parameter_intro/switch">SWITCH</a>
</p>
         </td>
         <td colspan="1" rowspan="1">
            <p>Time at which the Transfer CFT performs an automatic 
 switch. When this parameter is not defined, log files are switched daily 
 at midnight.</p>
         </td>
      </tr>
</table>

Example

This command defines the log file names:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td>
            <p>CFTLOG    ID = IDLOG,</p>
            <p>          FNAME = filename1,</p>
            <p>          AFNAME = filename2,</p>
            <p>          SWITCH = 2030,</p>
            <p>          EXEC = procfname,</p>
            <p>          OPERMSG = 240</p>
         </td>
      </tr>
   </tbody>
</table>

Automatic switching is scheduled for 20:30. The procedure initiated
at the time of switching is located in the file named by the EXEC parameter.

The record size is the default value of 133 characters.

The value of the OPERMSG parameter allows only error messages to be
sent to the operator (240 = 128+64+32+16).