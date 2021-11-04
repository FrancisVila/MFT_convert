{
    "title": "Configuring  the environment",
    "linkTitle": "Configuring the environment",
    "weight": "360"
}This topic describes how to configure the environment for an end-of-transfer
type exit. Before you submit this EXIT, you must customize the following
<span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> objects:

-   [Defining
    the CFTEXIT object](#Defining_the_CFTEXIT_object): to describe the EXIT environment and how this
    EXIT is activated

<!-- -->

-   [Defining
    the CFTPARM object](#Defining_the_CFTPARM_object): to indicate the CFTEXIT object identifier

Each CFTEXIT object corresponds to an EXIT task. The number of EXIT
tasks of all types simultaneously active is limited to a number depending
on the operating system.

An end-of -tansfer EXIT task is activated in memory before the EXECxx
submission call is deactivated, following a time-out or <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> shutdown.

<span id="Defining_the_CFTEXIT_object"></span>

## Defining the CFTEXIT object

<span class="bold_in_para">Syntax</span>

CFTEXITID = identifier,  
TYPE = EXEC,  
\[FORMAT = { V23
| V24 }\]  
\[LANGUAGE = {COBOL | C},\]  
\[MODE = {REPLACE | CREATE | DELETE},\]  
\[PARM = string,\]  
\[PROG = {CFTEXIT | string},\]  
\[RESERV = string \]  
\[WAITTASK = {1441 | n}\]

<table>
   <th>
      <tr>
<th><p>Parameter</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a> </p>
<p>(Mandatory)</p>         </td>
         <td><p>Command identifier (32 +1). The value of this identifier
corresponds to the identifier defined in the EXITEOT parameter of the
related CFTPARM object.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/format">FORMAT</a></p>         </td>
         <td><p>Indicates the format for the communication area.</p>
<ul>
<li>V23 (Default
value): The communication area between <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> and user’s exits remains
the same.</li>
<li>V24:
The communication area takes into account the length of the new identifier.</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/language">LANGUAGE</a></p>         </td>
         <td><p>Language in which the user program is written.</p>
<p>The possible values are COBOL and C language.</p>
<p><span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> uses this attribute to exchange data with
the program using the EXIT via the structure best suited to the language
in which it is implemented.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/parm">PARM</a> </p>         </td>
         <td><p>Free user field (64 +1).</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/prog">PROG</a>  </p>         </td>
         <td><p>Name of the executable module associated with the EXIT
task (512 +1). This module is built from the interface provided with Transfer
CFT linked to the program written by the user. In order to facilitate
identification of the associated module, it is advised to name it CFTEXIE.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/reserv">RESERV</a>  </p>         </td>
         <td><p>Size of the working area reserved for the user.</p>
<p>This area is not used by the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> interface. You
can use it to save data required for the processing of the program that
you have written. This area is de-allocated when the <span class="mc-variable axway_variables.Component_Short_Name variable">Transfer CFT</span> interface
de-selects the file.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/type">TYPE</a> </p>
<p>(Mandatory)</p>         </td>
         <td><p>EXEC</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/waittask">WAITTASK</a>  </p>         </td>
         <td><p>Time during which a file access task is inactive (in minutes)
before being shut down</p>         </td>
      </tr>
   </tbody>
</table>

<span id="Defining_the_CFTPARM_object"></span>

## Defining the CFTPARM object

Syntax

CFTPARM  
ID = identifier,  
\[EXITEOT = identifier,\]  
....

<table>
   <th>
      <tr>
<th><p>Parameter</p>         </th>
<th><p>Definition</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/id">ID</a></p>
<p>(Mandatory)</p>         </td>
         <td><p>CFTPARM object identifier.</p>         </td>
      </tr>
      <tr>
         <td><p><a href="../../../../c_intro_userinterfaces/command_summary/parameter_intro/exiteot">EXITEOT</a> </p>         </td>
         <td><p>EXIT identifier. To activate an end-of-transfer EXIT, you
must specify an identifier that points to a CFTEXIT object.</p>         </td>
      </tr>
   </tbody>
</table>

 
