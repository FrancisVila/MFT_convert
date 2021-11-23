{
    "title": "Executing server traces",
    "linkTitle": "Executing server traces",
    "weight": "200"
}{{< Gateway/componentlongname  >}}: Managing the Server

The following online commands enable you to create trace files of Gateway activities without stopping and restarting the server:

-   `pelctl trace_entity`
-   `pelctl trace_process`

<span id="pelctl_trace_entity"></span>

## pelctl trace\_entity

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p><code>pelctl trace_entity {-entity_name} {-trace_level}</code></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>This command generates traces of a specified entity and records them to a file in<code> &lt;Gateway installation directory&gt;/run_time/tmp</code>.</p>
<p>This command initiates tracing dynamically. You do not need to restart the server for tracing to start.</p>
<p>The name that Gateway attributes to the resulting file has the format:</p>
<p><code>   process_name-yyyyddmm-hhmmss-process_pid].out</code></p>
<p>where <code>process_name</code> is the name of the Process that contains the entity in structure of the configuration file <code>conffile</code> located in<code> &lt;Gateway installation directory&gt;/run_time/etc</code>.</p>         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td><p>(<em>mandatory</em>)</p>
<p><code>-entity_name (-ename)</code>: Enter the name of the Gateway entity you want to trace.</p>
<p>The entities that you can trace are listed in the configuration file <code>conffile</code> located in<code> &lt;Gateway installation directory&gt;/run_time/etc</code>.</p>         </td>
      </tr>
      <tr>
         <td><p>(<em>mandatory</em>)</p>
<p><code>-trace_level (-l)</code>: Enter one of the following values:</p>
<ul>
<li><strong>0</strong>: no trace</li>
<li><span style="font-weight: bold;">1</span></li>
<li><span style="font-weight: bold;">2</span></li>
<li><span style="font-weight: bold;">3</span></li>
<li><span style="font-weight: bold;">4</span>: maximum detail</li>
</ul>         </td>
      </tr>
      <tr>
         <td>Example         </td>
         <td><p>Enter the command:</p>
<p><span class="code">   pelctl trace_entity  -ename NDSP  -l 4</span></p>
<p>Gateway creates the trace file <span class="code">sup-&lt;timestamp&gt;-&lt;pid&gt;.out</span> in the Gateway <span class="code">/tmp</span> directory and records maximum trace detail of NDSP entity activities.</p>         </td>
      </tr>
   </tbody>
</table>

<span id="pelctl_trace_process"></span>

## pelctl trace\_process

<table>
         
         
         
   
   <tbody>
      <tr>
         <td>Syntax         </td>
         <td><p><span class="code"><strong>pelctl trace_process</strong> (-process_name} {-trace_level} [-all]</span></p>         </td>
      </tr>
      <tr>
         <td>Description         </td>
         <td><p>This command generates traces of a specified Gateway process and records them to a file in<span class="code"> &lt;Gateway installation directory&gt;/run_time/tmp</span>.</p>
<p>This command initiates tracing dynamically. You do not need to restart the server for tracing to start.</p>
<p>The name that Gateway attributes to the resulting file has the format:</p>
<p><span class="code">   [process_name-yyyymmdd-hhmmss-process_pid].out</span></p>         </td>
      </tr>
      <tr>
         <td>Parameters         </td>
         <td><p>(<span style="font-style: italic;">mandatory</span>)</p>
<p><span class="code">-process_name (-pname)</span>: Enter the name of the Gateway process you want to trace (for example, PEL, SUP, TCPPEL, ...).</p>
<p>The processes that you can trace are listed in the configuration file <span class="code" style="font-weight: bold;">conffile</span> located in<span class="code"> &lt;Gateway installation directory&gt;/run_time/etc</span>.</p>         </td>
      </tr>
      <tr>
         <td><p>(<span style="font-style: italic;">mandatory</span>)</p>
<p><span class="code">-trace_level (-l)</span>: Enter one of the following values:</p>
<ul>
<li><span style="font-weight: bold;">0</span>: no trace</li>
<li><span style="font-weight: bold;">1</span></li>
<li><span style="font-weight: bold;">2</span></li>
<li><span style="font-weight: bold;">3</span></li>
<li><span style="font-weight: bold;">4</span>: maximum detail</li>
</ul>         </td>
      </tr>
      <tr>
         <td><p>(<span style="font-style: italic;">optional</span>)</p>
<p><span class="code">-all</span>: Enter this parameter to trace the process specified in the <span class="code">-process_name</span> parameter and all entities that are associated with that process.</p>         </td>
      </tr>
      <tr>
         <td>Example         </td>
         <td><p>Enter the command:</p>
<p><span class="code">   pelctl trace_process  -pname SUP  -l 4</span></p>
<p>Gateway creates the trace file <span class="code">sup-&lt;timestamp&gt;-&lt;pid&gt;.out</span> in<span class="code"> &lt;Gateway installation directory&gt;/run_time/tmp</span> and records maximum trace details of SUP process activities.</p>         </td>
      </tr>
   </tbody>
</table>

Related topics

[Managing rotation and archiving of trace files](../trace_rotate)

 

Links to documentation set for Axway Gateway <span class="mc-variable axway_variables.Release_Number variable">6.17.3</span>:

-   [Installation](/bundle/Gateway_6173_InstallationGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [User](/bundle/Gateway_6173_UsersGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Unix Configuration](/bundle/Gateway_6173_ConfigurationGuide_UNIX_en_HTML5/page/Content/start_page.htm) -- [Upgrade](/bundle/Gateway_6173_UpgradeGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Interoperability](/bundle/Gateway_6173_InteroperabilityGuide_allOS_en_HTML5/page/Content/start_page.htm) -- [Security](/bundle/Gateway_6173_SecurityGuide_allOS_en_HTML5/page/Content/start_page.htm), requires login -- [Release Notes](/bundle/Gateway_6173_ReleaseNotes_allOS_en_HTML5/page/Content/Gateway_ReleaseNotes_allOS_en.htm)
