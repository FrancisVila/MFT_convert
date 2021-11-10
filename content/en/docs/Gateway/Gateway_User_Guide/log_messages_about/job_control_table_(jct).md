{
    "title": "Job Control Table (JCT)",
    "linkTitle": "Job Control Table (JCT)",
    "weight": "270"
}<span class="mc-variable axway_variables.Component_Long_Name variable">Axway Gateway</span>: Messages and codes

In the following messages, the parameter <span style="font-weight: bold;">%1</span> is the internal job name (JOBNAME). This parameter enables you to locate information that is associated with the process, and to find other log messages concerning the job process. You can use this information to better understand a message and diagnose an error, for example, by displaying the exit file, <span class="code">$p\_home\_dir/run\_time/tmp/JOBNAME-&lt;timestamp>-&lt;pid>.out</span>, that is associated with the job.

## Dynamic processes

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT001E"></span>001</p>         </td>
         <td><p>JCT E FORKFAIL [%1] Process creation failure: %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Error occurred during process creation. The local file system error is returned in parameter %1.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation for information on the local file system error.</p>
<p>If the system error message does not help resolve the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span style="font-weight: bold;"><span id="JCT002W"></span>002</span></p>         </td>
         <td><p><span style="font-weight: bold;">JCT I JOBQUEUED [%1] Job [%2] queued</span></p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A user job (user command executed in background) cannot be processed immediately, since the maximum number of running jobs has been reached (max_job configuration parameter).</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None: The job is queued and will be automatically scheduled when the number of running jobs decreases.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT003I"></span>003</p>         </td>
         <td><p>JCT I JOBTERML [%1] Job [%2] pid %3 terminated</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The process executing the job has completed and exited.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT004I"></span>004</p>         </td>
         <td><p>JCT I JOBSUBM [%1] Job [%2] submitted with pid %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The job process was submitted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Trace</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT010W"></span>010</p>         </td>
         <td><p>JCT W JOBSIG [%1] Job [%2] pid %3 terminated on signal %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning (UNIX only)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The job terminated abnormally on the indicated signal.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>User command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Signal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the message for job type and signal.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT011W"></span>011</p>         </td>
         <td><p>JCT W JOBSTOP [%1] Job [%2] pid %3 stopped on signal %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning (UNIX only)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The job stopped abnormally on the indicated signal.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Signal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the message for job type and signal.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT012W"></span>012</p>         </td>
         <td><p>JCT W JOBEXIT [%1] Job [%2] pid %3 exited with status %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning (UNIX only)</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The program stopped. When a job stops with the status displayed, you can use the status to diagnose the error.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT013W"></span>013</p>         </td>
         <td><p>JCT W JOBMESS [%1] Job [%2] pid %3 messed up with wait status %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Job has stopped with no available information to diagnose the situation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Job command associated with the job (the command may be shorted, with only the beginning of the command displayed)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

## User processes

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT051E"></span>051</p>         </td>
         <td><p>JCT E FORKFAIL [%1] Process creation failure : %2</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Error</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>An error occurred during batch creation.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Refer to your platform documentation for more information. If the system error messages does not help resolve the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT052I"></span>052</p>         </td>
         <td><p>JCT I CMDQUEUED [%1] Batch command [%2] queued</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>A batch command cannot be processed immediately because the maximum number of running batches has been reached.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>System error message</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT053I"></span>053</p>         </td>
         <td><p>JCT I CMDTERML [%1] Batch command [%2] pid %3 completed (exited with status 0)</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The process executing the batch command has finished and exited.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT054I"></span>054</p>         </td>
         <td><p>JCT I CMDSUBM [%1] Batch command [%2] submitted with pid %3</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Information</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The batch command was submitted.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (command may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>None</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT060W"></span>060</p>         </td>
         <td><p>JCT W CMDSIG [%1] Batch command [%2] pid %3 terminated on signal %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The batch has terminated abnormally on the indicated signal.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (command may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Signal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the message for job type and signal.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT061W"></span>061</p>         </td>
         <td><p>JCT W CMDSTOP [%1] Batch command [%2] pid %3 stopped on signal %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>The batch stopped abnormally on the indicated signal.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (command may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Signal</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Analyze the message for job type and signal. If the system error messages does not help resolve the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT062W"></span>062</p>         </td>
         <td><p>JCT W CMDEXIT [%1] Batch command [%2] pid %3 exited with status %4 -- %5</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (command may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>5</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>The final two lines of the Standard Error file output are displayed as Status %4-%5. If this error message does not help resolve the problem, contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

<table>
         
         
         
         
   
   <tbody>
      <tr>
         <td><p><span id="JCT063W"></span>063</p>         </td>
         <td><p>063 JCT W CMDMESS [%1] Batch command [%2] pid %3 messed up with wait status %4</p>         </td>
      </tr>
      <tr>
         <td><p>Type</p>         </td>
         <td><p>Warning</p>         </td>
      </tr>
      <tr>
         <td><p>Meaning</p>         </td>
         <td><p>Job process defaulted and no diagnostic information is available.</p>         </td>
      </tr>
      <tr>
         <td><p>Parameters</p>         </td>
         <td><p>1</p>         </td>
         <td><p>Job name</p>         </td>
      </tr>
      <tr>
         <td><p>2</p>         </td>
         <td><p>Batch command associated with the job process (command may be truncated)</p>         </td>
      </tr>
      <tr>
         <td><p>3</p>         </td>
         <td><p>System process identifier</p>         </td>
      </tr>
      <tr>
         <td><p>4</p>         </td>
         <td><p>Status</p>         </td>
      </tr>
      <tr>
         <td><p>Action</p>         </td>
         <td><p>Contact Axway Support.</p>         </td>
      </tr>
   </tbody>
</table>

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
