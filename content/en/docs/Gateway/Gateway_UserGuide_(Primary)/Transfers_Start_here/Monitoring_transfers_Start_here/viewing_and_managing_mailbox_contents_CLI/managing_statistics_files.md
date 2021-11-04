{
    "title": "Managing Statistics files (command line)",
    "linkTitle": "Managing Statistics files",
    "weight": "250"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

[About Statistics files](#About_Statistics_Files)

[Managing Statistics files](#Managing%20Statistics%20Files)

[pelctl archive\_stat](#pelctl_archive_stat)

[pelctl suspend\_stat](#pelctl_suspend_stat)

[pelctl resume\_stat](#pelctl_resume_stat)

[pelctl archive\_conn\_stat](#pelctl_archive_conn_stat)

[pelctl suspend\_conn\_stat](#pelctl_suspend)

[pelctl resume\_conn\_stat](#pelctl2_pelctl_resume)

[pelctl archive\_conn\_user\_stat](#pelctl_archive_conn_user_stat)

[pelctl suspend\_conn\_user\_stat](#pelctl_suspend_conn_user_stat)

[pelctl resume\_conn\_user\_stat](#pelctl_resume_conn_user_stat)

<span id="About_Statistics_Files"></span>

## About Statistics files

A <span style="font-weight: bold;">Statistics file</span> (or STAT file) is a formatted text file that contains records of terminated transfers.

The STAT file, named <span class="code" style="font-weight: bold;">stat.dat</span>, is located in:

&lt;Gateway installation directory>/run\_time/data/

Two other Statistics files were added, primarily for debugging use: <span class="code">conn\_stat.dat</span> and <span class="code">conn\_user\_stat.dat</span>. These files store information about connections and connected users, each time a transfer ends.

### Prerequisites for Statistics file generation

#### Statistics activation

To enable Gateway to generate STAT file records, activate the <span style="font-weight: bold;">[Statistics option](../../../../configuration_start_here/config_gateway_paras#statistics_option)</span> in the configuration menu. When this option is activated, Gateway generates a record in the STAT file each time a transfer is terminated.

To enable Connection and Connected User Statistics, run:

peluconf set –s monitor conn\_statistics\_option yes

#### Statistics data dictionary file

The format of the records deposited to the Statistics file is determined by the contents of the <span style="font-weight: bold;">Statistics data dictionary file</span>. The Statistics data dictionary file is a formatted text file located in <span class="code">&lt;Gateway installation directory>/run\_time/data/</span>. The name of the file is <span class="code">statdict.dat</span>. This file contains a list of items separated by a comma. Each item is delimited by quotation marks.

The first item of a line must be the <span style="font-weight: bold;">STAT record format number</span>. It is possible to create a <span class="code">statdict.dat</span> file with two or more lines, each beginning with a unique STAT record format number and followed by a set of attribute identifiers. You can then configure the Internal user exit <span class="code">exituser/exitstat.c</span> to return a format number according to your own criteria. For example, for MSG type transfers you may choose to apply a specific STAT record format by programming <span class="code">exitstat</span> to return a specific STAT record format number on MSG transfers. Note that format numbers 3 and 4 are used to format connections and connected user statistics. You can change these format numbers from <span class="code">exituser/existat.c</span> (<span class="code">ExitConnStatMessage</span> and <span class="code">ExitCousStatMessage</span>). Refer to [Internal user exits](../../../../customizing_gw_about/user_exits_about/user_exits_internal).

The other items in each line are the identifiers of transfer attributes for which Gateway generates statistics at the end of each transfer.

The default Statistics data dictionary record file comprises a single line. It resembles the following:


    "1", "x_direction", "x_mode", "x_create_date", "x_state", "x_last_end_reason", "x_x_bytes", "x_protocol", "x_originator", "x_destination", "x_dir_path", "x_file_component"

where:

-   "<span class="code">1</span>" is the STAT record format number
-   "<span class="code">x\_direction</span>" is the identifier of the end-of-transfer <span style="font-style: italic;">direction</span> attribute whose actual values are stored in the generated statistics record
-   "<span class="code">x\_mode</span>" is the identifier of the end-of-transfer <span style="font-style: italic;">transfer mode</span> attribute whose actual values are stored in the generated statistics record
-   and so on, for each successive identifier

#### Customizing the Statistics data dictionary file

You can configure the <span class="code">statdict.dat</span> file so that it is useful for the examination of your transfer operations. To configure this file, open the file with a text editor and add or remove transfer attribute identifiers. On installation, this file contains a certain number of attribute identifiers as displayed above.

You can add any valid attribute that is generated during a transfer. For a list of possible attributes to use in the <span class="code">statdict.dat</span> file, use the <span class="code" style="font-weight: bold;">peldsp display\_trans</span> command to list the attributes of a typical transfer.

Additionally, you can add lines to the file, each line beginning with a unique STAT record format number and containing a set of attribute identifiers that together describe a statistics record format.

### Statistics file generation

For each terminated transfer, Gateway:

-   Replaces the record format parameters, defined in the Statistics data dictionary (<span class="code">statdict.dat</span>), with their actual values
-   Writes the record in the STAT file (<span class="code">stat.dat</span>)

A resulting default statistics data file record in <span class="code">stat.dat</span> may look something like this:

"1", "S", "I", "970430 100520", "E", "0", "12345", "FTP", "SITE\_ORG", "SITE\_DEST","/directory", "file"

<span id="Managing Statistics Files"></span>

## Managing Statistics files

Use the following <span class="code" style="font-weight: bold;">pelctl</span> commands to perform Statistics file management operations.

<span id="pelctl_archive_stat"></span>

### pelctl archive\_stat: Archive the Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl archive_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command copies the content of the STAT (statistics) file into an archive file, and then deletes the current STAT file. After the operation, log inputs are recorded in a new empty STAT file.</p>
<p>The archive storage directory and file name are platform-dependent. For example, on UNIX platforms, the archive file name is the original file name with the suffix containing the timestamp of the archive request. (The archived log will have the format: <span class="code">stat.dat_YYYYMMDD_HHMMSS</span>).</p>
<p>In the Gateway configuration menu, you can specify the duration and/or the number of Kbytes whose threshold automatically triggers STAT file archiving.</p>
<p><span style="font-weight: bold;">Recommendation:</span> Archive the STAT file regularly to avoid the file becoming too large.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>For UNIX platforms:</p>
<p>Following an archive command, <span class="code" style="font-weight: bold;">pelctl archive_stat</span> executed on February 12, 2014 at 15 h 33 min. 22 sec, the archive is created, with file name:</p>
<p><span class="code">&lt;Gateway installation directory&gt;</span>&lt;Gateway installation directory&gt;/run_time/data/stat.dat_20140212_153322</p>
<p>The STAT file is a text file that you can view using a text editor. The lines of message text written to the log file record event occurrences.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_suspend_stat"></span>

### pelctl suspend\_stat: Suspend Statistics recording

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl suspend_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command suspends Statistics recording.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p>pelctl suspend_stat</p>
<p>Gateway suspends the writing of records to the Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_resume_stat"></span>

### pelctl resume\_stat: Resume recording in the Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl resume_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command resumes Statistics recording suspended by a <span class="code" style="font-weight: bold;">pelctl suspend_stat</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p>pelctl resume_stat</p>
<p>Gateway resumes the writing of records to the Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_archive_conn_stat"></span>

### pelctl archive\_conn\_stat: Archive the Connection Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl archive_conn_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command copies the content of the Connection statistics file into an archive file, and then deletes the current Connection statistics file. After the operation, log inputs are recorded in a new empty connection statistics file.</p>
<p>The archive storage directory and filename are platform-dependent. For example, on UNIX platforms, the archive filename is the original filename with the suffix containing the timestamp of the archive request. (The archived log will have the format: <span class="code">conn_stat.dat_YYYYMMDD_HHMMSS</span>).</p>
<p>In the Gateway configuration menu, you can specify the duration and/or the number of Kbytes whose threshold automatically triggers STAT file archiving.</p>
<p><strong>Recommendation:</strong> Archive the Connection Statistics file regularly to avoid the file becoming too large.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>For UNIX platforms:</p>
<p>Following an archive command, <span class="code">pelctl archive_conn_stat</span> executed on February 12, 2014 at 15 h 33 min. 22 sec, the archive is created, with the filename:</p>
<p><span class="code">&lt;Gateway installation directory&gt;&lt;Gateway installation directory&gt;/run_time/data/conn_stat.dat_20140212_153322</span></p>
<p>The Connection Statistics file is a text file that you can view using a text editor. The lines of message text written to the log file record event occurrences.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_suspend"></span>

### pelctl suspend\_conn\_stat: Suspend Connection Statistics recording

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl suspend_conn_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command suspends Connection Statistics recording.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p><span class="code">pelctl suspend_conn_stat</span></p>
<p>Gateway suspends the writing of records to the Connection Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl2_pelctl_resume"></span>

### pelctl resume\_conn\_stat: Resume recording in the Connection Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl resume_conn_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command resumes Statistics recording suspended by a <span class="code">pelctl suspend_conn_stat</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p><span class="code">pelctl resume_conn_stat</span></p>
<p>Gateway resumes the writing of records to the Connection Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_archive_conn_user_stat"></span>

### pelctl archive\_conn\_user\_stat: Archive the Connected User Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl archive_conn_user_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command copies the content of the Connected User statistics file into an archive file, and then deletes the current Connected User statistics file. After the operation, log inputs are recorded in a new empty connected user statistics file.</p>
<p>The archive storage directory and file name are platform-dependent. For example, on UNIX platforms, the archive file name is the original file name with the suffix containing the timestamp of the archive request.</p>
<p>(The archived log will have the format: <span class="code">conn_user_stat.dat_YYYYMMDD_HHMMSS</span>).</p>
<p>In the Gateway configuration menu, you can specify the duration and/or the number of Kbytes whose threshold automatically triggers STAT file archiving.</p>
<p><strong>Recommendation:</strong> Archive the Connected User Statistics file regularly to avoid the file becoming too large.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>For UNIX platforms:</p>
<p>Following an archive command, <span class="code">pelctl archive_conn_user_stat</span> executed on February 12, 2014 at 15 h 33 min. 22 sec, the archive is created, with the filename:</p>
<p><span class="code">&lt;Gateway installation directory&gt;&lt;Gateway installation directory&gt;/run_time/data/conn_user_stat.dat_20140212_153322</span></p>
<p>The Connected User Statistics file is a text file that you can view using a text editor. The lines of message text written to the log file record event occurrences.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_suspend_conn_user_stat"></span>

### pelctl suspend\_conn\_user\_stat: Suspend Connection Statistics recording

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl suspend_conn_user_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command suspends Connection Statistics recording</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p>pelctl suspend_conn_user_stat</p>
<p>Gateway suspends the writing of records to the Connected User Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_resume_conn_user_stat"></span>

### pelctl resume\_conn\_user\_stat: Resume recording in the Connection Statistics file

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p>pelctl resume_conn_user_stat</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command resumes Statistics recording suspended by a <span class="code">pelctl suspend_conn_user_stat</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Enter:</p>
<p>pelctl resume_conn_user_stat</p>
<p>Gateway resumes the writing of records to the Connected User Statistics file.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
