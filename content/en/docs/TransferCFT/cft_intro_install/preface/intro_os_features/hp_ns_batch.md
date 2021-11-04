{
    "title": "Transfer CFT batch procedures",
    "linkTitle": "Batch procedures",
    "weight": "220"
}Transfer CFT supports batch procedure from both native and OSS environments. This section describes the rules that determine the type of batch procedure and how it is executed.

## How it works

In the absence of TACL indicators in the first line of the batch procedure, the procedure is executed as a script in the OSS environment. If TACL indicators are present, certain characters and rules determines what happens next in the native environment (either Direct TACL processing or NetBatch processing).

The **Decision rules** section explains which characters indicate that it is a TACL procedure, and the exact type of processing that is used.

A batch procedure can contain a reference to Transfer CFT variables. The character used to indicate a variable is:

-   &
    -   OSS script
    -   Example: &FNAME
-   ^
    -   The same character as in the previous Tandem version
    -   TACL procedure
    -   Example: ^FNAME

Refer to *Transfer CFT User Guide* for a complete list of Transfer CFT variables.

<img src="/Images/TransferCFT/temp_batch_processing.png" class="mediumWidth" />

### Decision rules

If the first line of the skeleton procedure begins with one of the following characters, it is a TACL procedure.

-   ==
-   ?
-   #FRAME
-   #PUSH

The characters following the initial " == " either set certain information for the TACL procedure or determine if the procedure is sent to the NetBatch interface for processing.

-   == CFT^BT^FORCE^TACL ==
    -   A direct TACL procedure execution
    -   This execution type performed by default
    -   This parameter is kept to ensure compatibility with existing batch procedures
-   <span id="CFT^BT^FORCE^ZBAT"></span>== CFT^BT^FORCE^ZBAT<span style="color: #b22222;"> == </span>
    -   Use NetBatch Interface
    -   To specify a given environment, you can declare it in the first line of the actual procedure. Add the following optional values in the first line of the skeleton procedure, in the order listed. If no values are declared, the [UCONF](#UCONF) default values are used.
        -   NetBatch process
        -   Job name
        -   Attachment-set
    -   For each field add a delimiter such as a colon (:), comma (,), or equal sign (=) followed by the parameter's value

**Example**

== CFT^BT^FORCE^ZBAT : $ZBA1 , JOBNAME , SETNAME ==

-   NetBatch Process = $ZBA1
-   Job name = JOBNAME
-   Attachment Set = SETNAME

### Processing

Regardless of if the procedure is OSS or native, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> creates a temporary file with the following locations and naming conventions:

-   OSS: The same as on <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> Unix: /tmp/CFTxxxx  
-   Native: On the <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> default [subvolume](##subvolumeUD): CTMPnnnn

2> filenames $DATA14.CFT32BUD.\*

          $DATA14.CFT32BUD

CTMP0001 CTMP0002 CTMP0003 CTMP0004

<span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span> copies the skeleton in the temporary file, replacing variables with their real values (transfer information, file names, etc.).

Depending on the type of procedure, <span class="mc-variable axway_variables.Component_Long_Name variable">Transfer CFT</span>:

-   Starts the script (OSS)
-   Starts the TACL direct processing
-   Puts the temporary file in NetBatch for execution

### Delete temporary files

The started procedure MUST delete the temporary files, regardless of the environment.

-   OSS
    -   rm $0
    -   rm $0.err
-   NATIVE
    -   #PURGE \[#IN\]
    -   The same BTPURGE procedure as in the previous version is delivered and can be executed:

<span id="UCONF"></span>

### UCONF parameters

The following unified configuration parameters are specific to HP Nonstop.

<table>
   <th>
      <tr>
<th><p>Parameter</p>         </th>
<th><p>Default</p>         </th>
<th><p>Description</p>         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><p><span id="cft.guardian.cftwrk"></span>cft.guardian.cftwrk</p>         </td>
         <td>         </td>
         <td><p>The default working directory for the TACL and NETBATCH scripts.</p>
<p>The parameter is set with the default value of “<span class="code">&lt;</span><span class="code" data-xmlns="http://www.w3.org/TR/REC-html40">subvolume</span><span class="code">&gt;UD</span>”
(see <a href="##Guardian" class="MCXref xref">Guardian files</a>) during the Guardian
files installation.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.process_name_prefix"></span>cft.guardian.process_name_prefix</p>         </td>
         <td><p>LA</p>         </td>
         <td><p>The first two letters of the Guardian process names.</p>
<p>Each Transfer CFT process is assigned a name using this prefix and a
suffix, which depends on the executable name.</p>
<p>For instance, using the default setting, CFTLOG is run with the
name $LALOG with the Guardian convention (or /G/LALOG with the OSS
convention).</p>
<p>If empty, no Guardian process name is given.</p>
<p>If you plan to run several instances of Transfer CFT at the same time on
the same machine, you should assign each instance a unique value.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.processor"></span>cft.guardian.processor</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>Processor on which Transfer CFT is started.</p>
<ul>
<li> 
-1 indicates that Transfer CFT is started on the processor
from which the start-up command is executed</li>
<li>Processor number</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.backup_processor"></span>cft.guardian.backup_processor</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>Backup processor on which Transfer CFT is started.</p>
<ul>
<li>-1 indicates that no processor number is assigned</li>
<li>Backup processor number</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.priority"></span>cft.guardian.priority</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>Guardian execution priority of the CFT processes.</p>
<ul>
<li>-1 means that CFT is started with the
execution priority of the parent process.</li>
<li>Process priority</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.hometerm"></span>cft.guardian.hometerm</p>         </td>
         <td>         </td>
         <td><p>The Guardian home terminal for Transfer CFT processes.</p>
<ul>
<li>An empty value means that CFT is started with
the OSS shell’s home terminal</li>
<li>The value should be either set using the
Guardian form ($ZTNT.#PTY4, $TTY), or the OSS form
(/G/ZTNT/#PTY, /G/TTY)</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tcpip_resolver_name</p>         </td>
         <td>         </td>
         <td><p>The TCPIP resolver name for Transfer CFT processes. Equivalent to the Guardian
DEFINE TCPIP^RESOLVER^NAME.</p>
If set, the value should be a Unix pathname pointing to an existing resolver file.         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.processor</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>Processor on which TACL is started.</p>
<ul>
<li>-1 means that TACL is started on same
processor where Transfer CFT is running</li>
<li>Processor number</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.backup_processor</p>         </td>
         <td><p>-1</p>         </td>
         <td><p>Backup processor on which TACL is started. Valid only if
different from -1 and from the cft.guardian.tacl.value.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.priority</p>         </td>
         <td><p>90</p>         </td>
         <td><p>Priority of a started TACL.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.output</p>         </td>
         <td><p>'$S.#ABTT'</p>         </td>
         <td><p>Output destination of the started TACL.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.tacl.home_terminal</p>         </td>
         <td><p>'$ZHOME'</p>         </td>
         <td><p>TACL home terminal.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.process</p>         </td>
         <td><p>'$ZBAT'</p>         </td>
         <td><p>NetBatch process with which you send a request.</p>
<p>You can override this value in the <a href="#CFT%5EBT%5EFORCE%5EZBAT">first line of a TACL procedure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.jobname_prefix</p>         </td>
         <td><p>'ZBBT'</p>         </td>
         <td><p>A jobname prefix used to build a jobname having 8 characters, and
comprised of:</p>
<ul>
<li>This prefix</li>
<li>A suffix that is composed of the last
characters of the temporary file name</li>
</ul>
<p>You can override this value in the <a href="#CFT%5EBT%5EFORCE%5EZBAT">first line of a TACL procedure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p><span id="cft.guardian.netbatch.attachment_set"></span>cft.guardian.netbatch.attachment_set</p>         </td>
         <td><p>'NBASCFTLI'</p>         </td>
         <td><p>NetBatch attachment-set name.</p>
<p>You can override this value in the <a href="#CFT%5EBT%5EFORCE%5EZBAT">first line of a TACL procedure</a>.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.priority</p>         </td>
         <td><p>90</p>         </td>
         <td><p>Priority of TACL run started.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.selpri</p>         </td>
         <td><p>4</p>         </td>
         <td><p>JOB selection priority.</p>         </td>
      </tr>
      <tr>
         <td><p>cft.guardian.netbatch.output</p>         </td>
         <td><p>'$S.#ABTZ'</p>         </td>
         <td><p>Output destination of the started TACL.</p>         </td>
      </tr>
   </tbody>
</table>
