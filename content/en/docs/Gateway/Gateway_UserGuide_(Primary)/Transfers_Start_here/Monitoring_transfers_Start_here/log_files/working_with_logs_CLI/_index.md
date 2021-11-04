{
    "title": "Working with Logs (command line)",
    "linkTitle": "Command line operations",
    "weight": "240"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Managing Transfers

<span class="code" style="font-weight: bold;">[pelctl archive\_log](#pelctl_archive_log)</span>

<span class="code" style="font-weight: bold;">[pelctl suspend\_log](#pelctl_suspend_log)</span>

<span class="code" style="font-weight: bold;">[pelctl resume\_log](#pelctl_resume_log)</span>

<span id="pelctl_archive_log"></span>

## pelctl archive\_log: Archive the Log

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelctl archive_log</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command copies the content of the Log file into an archive file, and then deletes the current log file. After the operation, the log inputs are recorded in a new empty log file.</p>
<p>The archive storage directory and filename are platform-dependent. For example, on UNIX platforms, the archive filename is the original filename with the suffix containing the timestamp of the archive request. (The archived log will have the format: <span class="code">log.dat_YYYYMMDD_HHMMSS</span>).</p>
<p>When configuring Gateway, you can specify the duration and/or the number of Kbytes whose threshold automatically triggers Log file archiving.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Example</strong></p>         </td>
         <td><p>Example archive filename on UNIX:</p>
<p><span class="code">&lt;Gateway installation directory&gt;/run_time/data/ log.dat_20040212_153322”</span></p>
<p>The Log file is a text file that you can view using a text editor. The lines of message text in the log file are based on event occurrences.</p>
<p><span style="font-weight: bold;">Recommendation:</span> Archive the log file regularly to avoid the file becoming too large.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_suspend_log"></span>

## pelctl suspend\_log: Suspend message recording to the Log

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelctl suspend_log</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command suspends Log recording.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_resume_log"></span>

## pelctl resume\_log: Resume message recording to the Log

<table>
         
         
         
   
   <tbody>
      <tr>
         <td><p><strong>Syntax</strong></p>         </td>
         <td><p><span class="code" style="font-weight: bold;">pelctl resume_log</span></p>         </td>
      </tr>
      <tr>
         <td><p><strong>Description</strong></p>         </td>
         <td><p>This command resumes Log recording suspended by a previous <span class="code" style="font-weight: bold;">pelctl suspend_log</span> command.</p>         </td>
      </tr>
      <tr>
         <td><p><strong>Parameters</strong></p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](#) -- [User](#) -- [Unix Configuration](#) -- [Upgrade](#) -- [Interoperability](#) -- [Security](#), requires login -- [Release Notes](#)
