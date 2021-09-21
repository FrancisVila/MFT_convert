{
    "title": "Transfer queue settings",
    "linkTitle": "Transfer queue settings",
    "weight": "130"
}You can manage the ST Web Client upload settings using the `transferQueue` property.

The following code snippet shows the upload defaults:

<table cellspacing="0">
   <col/>
   <tbody>
      <tr>
         <td><pre>{</pre><pre xml:space="preserve">  ...</pre><pre xml:space="preserve">  "transferQueue": {</pre><pre xml:space="preserve">    "failedLastXHours": 24, </pre><pre xml:space="preserve">    "transferOptions": {</pre><pre xml:space="preserve">	"uploadChunkSize": 104857600,</pre><pre xml:space="preserve">	"readChunkSize": 262144, </pre><pre xml:space="preserve">	"maxRetryCount": 3,</pre><pre xml:space="preserve">	"maxChunkRetryCount": 3, </pre><pre xml:space="preserve">	"timeoutBeforeRetry": 10000, </pre><pre xml:space="preserve">	"maxSimultaneousJob": 3 </pre><pre xml:space="preserve">  },</pre><pre xml:space="preserve">  "transferHistoryLimit": 100 </pre><pre xml:space="preserve"> },</pre><pre xml:space="preserve">  ...</pre><pre>}</pre>
         </td>
      </tr>
   </tbody>
</table>

To override a default setting, in the custom configuration file, add a `"transferQueue"` section and set a different value.

Listed below are all the accepted properties and what they affect.

<table cellspacing="0">
   <col/>
   <col/>
   <thead>
      <tr>
         <th>
            <p>Property</p>
            <p><em>(type)</em>
</p>
</th>
         <th>
            <p>Description</p>
            <p> </p>
</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><strong>failedLastXHours</strong>
            <p><em>(integer)</em>
</p>
         </td>
         <td>
            <p>The number of hours a failed transfer is counted in the failed transfers notification. </p>
            <p>Default value: <code>24</code>, which means that any transfer that failed more than 24 hours ago will not be counted in the failed transfers notification.</p>
         </td>
      </tr>
      <tr>
         <td><strong>transferOptions</strong>
            <p><em>(object)</em>
</p>
         </td>
         <td>
            <p>Controls chunk upload</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><strong>uploadChunkSize</strong>
            <p><em>(integer)</em>
</p>
               </li>
            </ul>
         </td>
         <td>
            <p>The size of the upload chunk, in bytes.</p>
            <p>Default value: <code>104857600</code>  (100 MB). </p>
            <p>Higher values may increase the upload speed but will make the upload progress less responsive and may cause high CPU load.</p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>readChunkSize</b>
<br/><em>(integer)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>The size of the read chunk, in bytes. </p>
            <p>default value: <code>262144</code> (0.25 MB)</p>
            <p>Higher values may increase the upload speed but more CPU will be consumed because of the incremental MD5. We recommend  a  value less than 1 MB. </p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>maxRetryCount</b>
<br/><em>(integer)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>The number of maximum retry attempts for the transfer job. </p>
            <p>Default value: <code>3</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>maxChunkRetryCount</b>
<br/><em>(integer)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>The maximum number of retry attempts for the current upload chunk after which the chunk will fail and the job will be restarted (see <b>maxRetryCount</b>) </p>
            <p>Default value: <code>3</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>timeoutBeforeRetry</b>
<br/><em>(integer)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>The period before retrying the current upload chunk in case of error, in milliseconds. </p>
            <p>Default value: <code>10000</code></p>
         </td>
      </tr>
      <tr>
         <td>
            <ul>
               <li><b>maxSimultaneousJob</b>
<br/><em>(integer)</em>
               </li>
            </ul>
         </td>
         <td>
            <p>The number of simultaneous upload jobs.</p>
            <p>Default value: <code>3</code></p>
            <p>If you select more than three (files for upload), the first three will start and the rest will wait. For Chrome, Firefox, and Microsoft Chromium-based Edge, the value can be up to 20. For  Internet Explorer, we recommend a  value less than 10.</p>
         </td>
      </tr>
      <tr>
         <td><b>transferHistoryLimit</b>
            <p><em>(integer)</em>
</p>
         </td>
         <td>
            <p>The number  of transfers to get from the transfers API on application load (if the <b>Allow this account to submit transfers using the Transfers RESTful API</b> option is enabled for the user). </p>
            <p>Default value: <code>100</code></p>
            <p>Higher values increase the number of history entries in the Uploads Monitor but take more time to load.</p>
         </td>
      </tr>
   </tbody>
</table>
